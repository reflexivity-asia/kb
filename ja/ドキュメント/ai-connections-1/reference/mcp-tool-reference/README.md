<!--
id: RX-PRODUCT-1103
type: product
language: ja
locale: ja-JP
author: Reflexivity GTM Team
kb_imported: 2026-09-29
status: published
translation_status: current
resource: Reflexivity Documentation
-->
# MCPツールリファレンス

[リファレンス](../README.md) · [ドキュメント](../../../README.md)

---

Reflexivity連携を設定する開発者、およびレスポンスを処理する開発者向けのリファレンスです。7つのツールはすべて読み取り専用です。導入方法は[接続](../../connect/README.md)を参照してください。

---

## 接続情報

| 項目 | 内容 |
| --- | --- |
| 本番エンドポイント | `https://api.reflexivity.com/external-research-mcp/mcp` |
| トランスポート | Streamable HTTP上のMCP |
| プラグインのサーバー名 | `reflexivity-research` |
| プラグイン認証 | `identity.reflexivity.com` を介したPKCE付きブラウザーOAuth。クライアント登録とトークン保存はホスト側が処理します |
| アカウント要件 | ご自身のフルReflexivityユーザーアカウント |
| 対象範囲 | 公開済みリサーチとKnowledge Graphデータの読み取り、および権限のある保存済みリストの利用 |

[プラグインリポジトリ](https://github.com/toggleglobal/reflexivity-ai-plugins)には、Claude Code、Codex、Cursor向けの接続設定がまとめられています。他のホストでは独自のOAuth登録が必要になる場合があります。プラグインの動的登録フローが、管理者が作成するMicrosoft 365接続にもそのまま適用されるとは限りません。

---

## リファレンスと入力値

テーマや関係性の識別子を独自に組み立てるのではなく、サービスが返したリファレンスを使用してください。

| 種別 | 形式 | 主な用途 |
| --- | --- | --- |
| 企業 | `entity:<ticker>_<exchange>`（小文字） | リサーチ検索、企業検索 |
| テーマ | `theme:<uuid>` | リサーチ対象、テーマ検索 |
| リサーチ | `kg:<uuid>` または `scenario:<uuid>` | リサーチ全文の取得 |
| 関係性 | `rel:<opaque>` | 関係性の根拠取得 |
| 保存済みリスト | UUIDそのもの + `watchlist` または `basket` | 検索・参照フィルター |
| その他 | `country:<ISO-2>`、`region:<name>`、`product:<id>` | 関係性の出力 |

subjectまたはsecurityオブジェクトには、`query`、`ref`、`kind`、`exchange`、`asset_class`を指定できます。`ref`は`query`より優先されます。`kind`の既定値は`entity`で、テーマ検索では`theme`を使用します。取引所ヒントには`NASD`などのコードを使用します。アセットクラスは`stock`、`equity`、`etf`、`bond`、`future`、`fx`、`commodity`、`credit`、`mutual_fund`です。入力値として受け付けられることは、そのアセットクラスのリサーチカバレッジが存在することを意味しません。

保存済みリストのフィルターには`saved_universe_id`と`saved_universe_type`を使用します。利用可能な識別子は`list_saved_universes`で取得してください。リサーチ詳細と関係性の根拠取得では、保存済みリストのフィルターではなくリファレンスを指定します。

---

## 共通レスポンスフィールド

| フィールド | 意味 |
| --- | --- |
| `schema_version` | レスポンス契約のバージョン。返された値に対応する契約としてレスポンスを解釈します。プラグインやアプリケーションのバージョンとは別です |
| `data_as_of` | レスポンスが組み立てられたUTC時刻。リサーチの公開日・対象期間、または元データがその時刻に更新されたことを示す値ではありません |
| `coverage` | `requested`、`resolved`、`authorized`、`executed`の件数。単位はツールごとに異なります |
| `source_status` | バックエンド情報源とその状態。`ok`、`skipped`、`unavailable`など。`detail`に問題の説明が含まれる場合があります |
| `interpretations` | 入力の解決結果。`input`、`status`、`selected`、曖昧な場合の`candidates`、必要に応じて`resolver_version` |
| `page` | ページング対応ツールの`requested_limit`、`effective_limit`、`has_more`、次ページがある場合の`next_cursor` |
| `window` | リサーチ検索に適用された`from`と`to` |
| `omitted_refs` | 部分取得に対応する場合、取得できなかった項目の`ref`と`reason` |

解決状態には`resolved`、`ambiguous`、`not_found`があります。クエリの解決結果には選択された企業またはテーマが示され、企業クエリではtickerやexchangeが含まれる場合があります。特にテーマ検索では、関連名にマッチすることがあるため、選択されたlabelを確認してください。

入力を解決できなくても、結果0件の通常レスポンスになる場合があります。Knowledge Graphのカバレッジ外の企業だけをスキップし、残りの企業について処理を続行する場合もあります。一部の企業が実行されていても、`source_status`に`ok`行が出ないことがあります。`interpretations`、`coverage`、結果、`source_status`を合わせて確認し、空の結果だけから原因を判断しないでください。曖昧な入力と解決済み入力を混在させた場合の動作はツールごとの確認が必要です。

ページングでは、元のフィルターを保ったまま`page.next_cursor`を変更せず渡してください。`requested_limit`が0の場合、呼び出し側がlimitを省略したことを示す場合があります。実際に適用された値は`effective_limit`で確認します。

---

## リサーチを検索する

`search_insights`は、公開日の新しい順に簡潔なリサーチサマリーを返します。

| 入力 | 既定値／上限 |
| --- | --- |
| `subjects` | 任意のsubjectオブジェクト配列。指定したいずれかの対象に関するリサーチにマッチ |
| `types` | 既定は全種別。`company_catalyst`、`market_catalyst`、`earnings_preview`、`earnings_recap`、`scenario`を指定可能 |
| `from`, `to` | `from`: `to`の30日前、`to`: 現在。RFC 3339の日時または日付 |
| `saved_universe_id`, `saved_universe_type` | 任意の保存済みリストフィルター |
| `limit` | 20、最大50 |
| `cursor` | 前回の`page.next_cursor` |
| `language` | 任意のBCP-47コード |
| `partial_ok` | `false`。`true`にすると回答可能な対象・情報源から結果を取得 |

日付だけの`from`はUTC 00:00から、日付だけの`to`はその日の終わりまでを含みます。

`{"subjects": [{"ref": "entity:nvda_nasd"}], "types": ["earnings_recap"], "limit": 5}`

結果配列は`insights`です。各項目には`ref`、`type`、`title`、`published_at`が含まれ、該当する場合は`subtitle`、`sentiment`、`subject_ref`も含まれます。Scenarioのサマリーにはsubtitleとsentimentがありません。一部のMarket Catalystにはsubjectがありません。リサーチのsentimentは`positive`、`neutral`、`negative`です。

coverageでは、明示的に指定したsubjectを各1件、保存済みリストを各1件として数えます。テーマsubjectは企業固有のScenarioには適用されず、その情報源はskippedとして報告されます。利用可能な情報源で該当リサーチが0件である状態と、情報源自体が利用不可である状態は区別してください。

### Star rating

現在文書化されている`search_insights`入力にはStar ratingのフィルターがなく、検索・詳細レスポンスにもStar ratingフィールドは定義されていません。「7 stars以上」などの依頼を未対応パラメータへ変換したり、Star ratingで絞り込んだと説明したりしないでください。別の製品APIにフィルターがあっても、このMCPインターフェースで利用できることを意味しません。

---

## リサーチ全文を読む

`get_insights`は、検索で返されたリファレンスを使って選択したリサーチを取得します。

| 入力 | 既定値／上限 |
| --- | --- |
| `refs` | 必須。最大5件の`kg:`または`scenario:`リファレンス |
| `include` | 取得対象のグループ。`summary`、`sections`、`statistics` |
| `language` | 任意のBCP-47コード |
| `partial_ok` | `false`。`true`の場合は未取得項目を`omitted_refs`で報告 |

`{"refs": ["kg:<reference-from-search>"], "include": ["summary", "sections"]}`

`insights`の各項目はサマリーフィールドに加え、`included_field_groups`を持ちます。カード形式のリサーチには`updated_at`と`sections`が追加され、section typeには`hero`、`takeaway`、`quotes`、`details_grid`、`graph`、`geo`などがあります。内容にはbadge、takeaway、theme tag、主要数値、順位付きpeer table、country cardなどが含まれることがあります。sectionの有無や件数はリサーチ種別によって異なります。すべてのsectionが存在すると仮定したり、空のsectionを権限制限だと判断したりしないでください。

Scenario項目では代わりに`scenario`が追加され、`entity_tag`、`best_horizon`、要求した場合は`date`、`median`、`low`、`high`を持つ`forecasts`が含まれます。取得例の数値は価格水準に見えますが、単位と通貨は未確認です。Scenario項目には`updated_at`がありません。全文内のsentimentには、country cardで`mixed`や`warning`が使われたり、空欄になったりする場合もあります。すべてのカードがサマリーと同じsentiment値を使うとは限りません。

coverageはリファレンス件数を数えます。ページングはないため、5件を超える場合は複数回に分けて取得します。不明なリファレンスは既定では`SUBJECT_NOT_FOUND`になります。部分取得時の理由には`not_found`や`upstream_unavailable`があります。適用外のfield groupはomission noteなしで省略される場合があり、権限制限やレスポンス容量制限時の正確な挙動は未確認です。

決算の対象期間はtitleまたは本文に記載され、独立したフィールドではありません。`published_at`や`updated_at`とは別に扱ってください。

### Scenarioの方向性とsentiment

現在文書化されているScenario詳細には、証券識別子、best horizon、利用可能な予測ポイントが含まれますが、bullish/bearish専用のdirectionフィールドは定義されていません。

sentimentは別の任意フィールドです。すべてのScenarioに存在するとは限らず、Scenarioの方向性と同義でもありません。

要求された方向性がレスポンスにない場合は、取得できないと明示してください。titleだけからbullish／bearishを推測しないでください。

Knowledge Graphの`exposure_direction`は別の概念であり、代用できません。

---

## 企業プロフィールとエクスポージャー

`get_company_relationships`は、1社以上の企業について関係性を返します。

| 入力 | 既定値／上限 |
| --- | --- |
| `securities` | 任意のsecurityオブジェクト配列。保存済みリストの代替 |
| `saved_universe_id`, `saved_universe_type` | 任意の保存済みリストフィルター |
| `relationship_types` | 既定は6種すべて: `theme`、`macro_theme`、`financial_theme`、`product`、`country`、`region` |
| `limit` | 20 edges、最大50 |
| `cursor`, `language` | 任意 |
| `partial_ok` | `false`。サーバー説明では、未解決入力は実行を止めて候補を返します |

`{"securities": [{"query": "NVIDIA", "exchange": "NASD"}], "relationship_types": ["theme"]}`

`relationships`配列には`ref`、`type`、`source`、`target`、`rank`が含まれます。sourceは企業をreference、label、ticker、exchangeで示し、targetは関連するテーマ、製品、地域情報を示します。financial themeとmacro themeには`exposure_direction`（`positive`、`negative`、`neutral`）が追加されます。

rankは企業ごと・relationship typeごとに1から始まります。結果は企業、type、rankの順で並びます。特定の関係に絞る場合はtypeフィルターを使用してください。説明や根拠は、返された`rel:`リファレンスを使って別途取得します。supplierとcustomerは、このインターフェースでは独立したrelationship typeではありません。

coverageは保存済みリストの各構成銘柄を含むsecurity件数を数えます。Knowledge Graphのカバレッジ外企業は、他の企業を止めずにskippedになる場合があります。

---

## 競合企業

`get_company_competitors`は、1社以上の企業について順位付きの競合企業を返します。

| 入力 | 既定値／上限 |
| --- | --- |
| `securities` | 任意のsecurityオブジェクト配列 |
| `saved_universe_id`, `saved_universe_type` | 任意の保存済みリストフィルター |
| `limit` | 20社、最大50 |
| `cursor` | 任意 |
| `partial_ok` | `false` |

`{"securities": [{"ref": "entity:nvda_nasd"}, {"ref": "entity:amd_nasd"}], "limit": 10}`

`competitors`配列には企業の`ref`、`label`、`ticker`、`exchange`、`rank`、`competitor_of`、`refs`が含まれます。`competitor_of`は要求対象企業をbare company tagで示します。`refs`は根拠取得に使う関係性リファレンスです。

複数企業に共通する競合は1回だけ表示されます。統合リスト上のrankが、各要求企業に対するrankと一致するとは限りません。根拠レスポンスには個別のrelationship rankが含まれます。結果には説明文やテーマ一覧は含まれません。

coverageは保存済みリスト構成銘柄を含むsecurity件数です。カバレッジ外企業はskippedになる場合があります。曖昧な入力や、明示指定のsecurityと保存済みリストを併用した場合の挙動は確認が必要です。このツールには`language`パラメータがありません。

---

## テーマに関連する企業

`find_theme_companies`は、選択したテーマに関連する企業を返します。

| 入力 | 既定値／上限 |
| --- | --- |
| `theme` | 必須のsubjectオブジェクト。テーマクエリまたは正確な`theme:`リファレンス |
| `securities` | 選択企業に絞る任意フィルター |
| `saved_universe_id`, `saved_universe_type` | 任意の保存済みリストフィルター。この経路は要検証 |
| `limit` | 20社、最大50 |
| `cursor`, `language` | 任意 |
| `partial_ok` | `false` |

`{"theme": {"query": "Artificial Intelligence", "kind": "theme"}, "limit": 20}`

`relationships`配列は上記と同じedge形式で、テーマが`source`、企業が`target`になります。選択されたテーマは`interpretations`に示されます。その`score`は内部のマッチスコアであり、エクスポージャーの大きさを示す値ではありません。

企業リストでフィルターしても、企業のrankはテーマ全体での順位を維持します。企業が正常に解決されても関係性が返らない場合があります。その欠落を「エクスポージャー0」と数値化しないでください。coverageはテーマ1件と各filter securityを数えます。financial themeでは`exposure_direction`が含まれる場合があります。

基礎となる業界手法では、「ある企業にとって重要なテーマ」と「あるテーマにおける企業の重要度」を区別しています。この手法と実際のレスポンスの対応関係は引き続き確認が必要です。[カバレッジと情報源](../../research/coverage-and-sources/README.md)を参照してください。

---

## 関係性の根拠

`get_relationship_evidence`は、企業・競合・テーマ検索で返された関係性リファレンスを展開します。

| 入力 | 既定値／上限 |
| --- | --- |
| `refs` | 必須。サービスが発行した`rel:`リファレンスを最大10件 |
| `language` | 任意 |
| `partial_ok` | `false`。サーバー説明では`true`の場合に取得できないリファレンスを報告 |

`{"refs": ["rel:<reference-from-a-lookup>"]}`

`evidence`配列はedgeの識別子、type、rank、該当する場合はexposure directionを再掲し、`description`を追加します。`source_evidence`と`document_ids`が含まれる場合もあります。競合関係では、これらの補助フィールドがなくdescriptionだけが返ることがあります。document IDは不透明な識別子で、この連携にはIDから資料名やURLへ変換するツールはありません。

coverageはリファレンス件数です。ページングはありません。10件を超える指定や、サービス発行ではないリファレンスは`INVALID_INPUT`になります。`partial_ok`を指定しても無効なリファレンスが許可されるわけではありません。古いリファレンスや上流障害時の挙動は引き続き確認が必要です。

---

## ウォッチリストとバスケット

typesを省略するとwatchlistとbasketの両方を要求します。個人のwatchlistだけを返すにはtypesを["watchlist"]、共有basketだけなら["basket"]にします。合計件数を示す場合は2つのカテゴリを分けて表示してください。

| 入力 | 既定値／上限 |
| --- | --- |
| `types` | `watchlist`と`basket`の両方。配列で制限可能 |
| `limit` | 25、最大100。0の場合は既定値 |
| `cursor` | 任意 |
| `partial_ok` | `false`。`true`なら一方の情報源が失敗しても利用可能なカテゴリを要求 |

`universes`配列には`type`、`id`、`name`、`count`が含まれます。この一覧だけでは構成銘柄は返りません。別のツールにIDとtypeを渡してリスト全体のリサーチを要求すると、その結果から調査対象企業が判明する場合があります。

coverageはリストのカテゴリ数を数え、watchlistで1、basketで1です。このツールには`language`パラメータがありません。正常レスポンスでリストが空でも、それだけでサインイン失敗とは判断できません。すべてのリストが利用可能だったと説明する前にsource statusを確認してください。

---

## エラーと部分結果

エラーは通常のレスポンスエンベロープではなく、MCP tool errorとして返ります。形式は`[CODE] message`です。確認済みのvalidation例は次のとおりです。

| コード | 原因 |
| --- | --- |
| `INVALID_INPUT` | 詳細／根拠リファレンスの指定過多、無効なrelationship reference、開始日が終了日より後の期間指定 |
| `SUBJECT_NOT_FOUND` | 部分取得を無効にした状態で不明なresearch referenceを指定 |
| `UNAUTHORIZED` / HTTP 401 | プラグインガイドではサインイン不足または期限切れとして説明 |
| `FORBIDDEN` / HTTP 403 | プラグインガイドではリサーチアクセス権がないアカウントとして説明 |

最後の2つはプラグインガイド由来で、本番アカウントでの記録済みテストがまだ必要です。rate limit、期限切れ、権限制限、レスポンス容量制限時の挙動は未確定です。実際に返っていないerror codeから、項目が欠落した理由を推測しないでください。

### 認証と接続の復旧

ブラウザー認証が成功しても、ホストがツールを検出し、tool callを実行できることまでは保証しません。ツール検出と実際の成功した呼び出しを別々に確認してください。正常な空の`list_saved_universes`レスポンスは呼び出し成功の確認に使えますが、timeoutやsource unavailableは成功確認にはなりません。

テストでは、無効化された接続、認証後にツールが表示されないケース、期限切れに関連した再接続失敗が確認されています。Cursorの診断で“refresh_token grant not yet implemented”と報告された例がありますが、原因と影響範囲はエンジニアリング側での確認が必要です。すべてのtimeoutをネットワーク障害とみなしたり、すべてのホストでtoken refreshが確実に動作すると仮定したりしないでください。

ユーザー向けの復旧手順はTroubleshootingを参照してください。障害調査時には、ホストのバージョン、インストール方法、正確なエラー、再認証でtool callが復旧するかを記録してください。

---

## 言語と上限

`language`を受け付ける5つのツールではbest effortで適用されます。翻訳がないコンテンツはfallback flagなしで英語のまま返る場合があります。対応言語とカバレッジは製品側での確認が必要です。

ページングのlimitは、常に企業数ではなく各ツールの結果オブジェクト数を数えます。詳細取得のbatching、pagination、情報源の可用性は別の問題です。rate limit、quota、token lifetime、最大レスポンスサイズは未確認です。

---

← [リファレンス](../README.md)
