<!--
id: RX-PRODUCT-1001
type: product
language: en
locale: en
author: Reflexivity GTM Team
source_id: 6a1963a45bab9fa46f233528
resource: Reflexivity Documentation
kb_imported: 2026-09-29
status: published
translation_status: canonical
source_route: overview
-->
# Overview

---

## Introduction

Welcome to the Reflexivity developer portal. These guides explain how to connect Reflexivity’s research tools to an AI application or integrate directly with the REST APIs.

---

## Choose your starting point

### Connect an AI application

Start with [AI Connections](../ai-connections-1/README.md), then select your application in [Application Guides](../ai-connections-1/application-guides/README.md).

Each guide explains the connection method, account requirements, sign-in steps, and how to check that your connection works.

### Build with the REST APIs

Use the REST APIs to integrate Reflexivity into your own application or workflow.

Follow the authentication instructions below, then select the endpoint you need from the navigation. Each endpoint’s documentation describes its request parameters and response format.

The account ID and secret described on this page are for REST API integrations. For AI application connections, follow your application’s sign-in guide.

## REST API overview

Reflexivity’s REST APIs return JSON responses. Requests require a bearer token obtained using your API account credentials.

The endpoint documentation covers services such as company relationships, research insights, price history, and Alfred conversations. Available services depend on your account’s access.

---

## REST API service addresses

### Production

Use these addresses for your production integration.

Authentication: [https://auth.reflexivity.com](https://auth.reflexivity.com/)

API: [https://api.reflexivity.com](https://api.reflexivity.com/)

IP address: 34.110.222.251/32

### Staging

Use these addresses for testing with staging credentials.

Authentication: [https://auth.staging.rflx.co.uk](https://auth.staging.rflx.co.uk/)

API: [https://api.staging.rflx.co.uk](https://api.staging.rflx.co.uk/)

IP address: 35.190.21.243/32

Use credentials and service addresses for the same environment.

---

## REST API authentication

### Obtain your API credentials

Contact the Reflexivity team to obtain your API account ID and secret.

Use your account ID as client_id and your account secret as client_secret when requesting an access token.

Store these credentials securely in your server-side application or secret manager.

### Request an access token

Send a POST request to the authentication service’s /oauth/token endpoint with your credentials in a JSON body.

Production example:

`curl --request POST '`[https://auth.reflexivity.com/oauth/token](https://auth.reflexivity.com/oauth/token)`' --header 'Content-Type: application/json' --data '{"client_id":"YOUR_ACCOUNT_ID","client_secret":"YOUR_ACCOUNT_SECRET"}'`

Replace `YOUR_ACCOUNT_ID and YOUR_ACCOUNT_SECRET`with your production credentials.

For staging, use [https://auth.staging.rflx.co.uk/oauth/token](https://auth.staging.rflx.co.uk/oauth/token) with your staging credentials.

A successful response includes:

access_token: The token to use in subsequent API requests.

token_type: The token type, returned as Bearer.

expires_in: The token’s lifetime in seconds.

scope: The permissions granted to the token.

### Authenticate your API requests

Include the access token in the Authorization header of each request using this format:

Authorization: Bearer `YOUR_ACCESS_TOKEN`

For a GET endpoint, the request takes this form:

`curl --header 'Authorization: Bearer YOUR_ACCESS_TOKEN' '`[https://api.reflexivity.com/ENDPOINT](https://api.reflexivity.com/ENDPOINT)`'`

Replace `YOUR_ACCESS_TOKEN` with the token returned by the authentication service. Replace ENDPOINT with the path from the endpoint documentation.

Use the HTTP method, parameters, and request body specified for that endpoint.

### Obtain a new token when needed

Use expires_in from the authentication response to determine when your token expires. Request a new access token when required.

If a request returns an authentication error, check that your token is valid and that your credentials, authentication address, and API address belong to the same environment.

---

## Next steps

For an AI application connection, continue to [Application Guides](../ai-connections-1/application-guides/README.md).

For a REST API integration, choose an endpoint from the navigation and review its required parameters, response fields, and examples before making your first request.

---

[← Documentation](../README.md)
