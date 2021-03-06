# finicity-postman
[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/logo.png)](https://www.finicity.com/#gh-light-mode-only)
[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/logo-dark.png)](https://www.finicity.com/#gh-dark-mode-only)

## Overview

The [Postman](https://www.postman.com/) collection for Finicity APIs (๐บ๐ธ) tested using [Newman](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/) and the [Finicity Test Drive](https://signup.finicity.com/).

## Workflows

The following workflow runs the collection and ensures it can be used to consume and test the Finicity APIs:

[![](https://github.com/Finicity-Mastercard/finicity-postman/actions/workflows/newman.yml/badge.svg)](https://github.com/Finicity-Mastercard/finicity-postman/actions/workflows/newman.yml)

## Collection
[JSON โค](./finicity.postman_collection.json)

## Run the Collection
### Things to Know :point_down:

* A [free Finicity account](https://signup.finicity.com/) is required to obtain your **Partner ID**, **Partner Secret** and **Finicity App Key**:

[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/dashboard.png)](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/dashboard.png?raw=true#gh-light-mode-only)
[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/dashboard-dark.png)](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/dashboard.png?raw=true#gh-dark-mode-only)

* Before running the collection, you need a **Customer ID**. For that, run [setup.sh](https://github.com/Finicity-Mastercard/finicity-openapi/blob/main/bin/setup.sh) and use the output of the script in the next sections. This script will call:
  * `addTestingCustomer`
  * `generateConnectUrl` ([Finicity Connect](https://docs.finicity.com/)). Simply open the URL and add to your test customer all accounts from [`profile_09`](https://docs.finicity.com/test-the-apis/#test-the-apis-3).
  * `refreshCustomerAccounts`

[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/connect-for-tests.png)](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/connect-for-tests.png?raw=true#gh-light-mode-only)
[![](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/connect-for-tests-dark.png)](https://raw.githubusercontent.com/Finicity-Mastercard/finicity-openapi/main/res/connect-for-tests.png?raw=true#gh-dark-mode-only)

### Import or Fork the Collection

1. Click: [![](https://run.pstmn.io/button.svg)](https://god.gw.postman.com/run-collection/20642888-6feb9f8f-b885-4473-96ad-4228b01f3460?action=collection%2Ffork&collection-url=entityId%3D20642888-6feb9f8f-b885-4473-96ad-4228b01f3460%26entityType%3Dcollection%26workspaceId%3D21a43e78-b01c-4909-83ca-d465d8e0a7bc#?env%5BTest%20Drive%5D=W3sia2V5IjoicGFydG5lcklkIiwidmFsdWUiOiJ7Y2hhbmdlbWV9IiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImRlZmF1bHQiLCJzZXNzaW9uVmFsdWUiOiJ7Y2hhbmdlbWV9Iiwic2Vzc2lvbkluZGV4IjowfSx7ImtleSI6InBhcnRuZXJTZWNyZXQiLCJ2YWx1ZSI6IntjaGFuZ2VtZX0iLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoic2VjcmV0Iiwic2Vzc2lvblZhbHVlIjoie2NoYW5nZW1lfSIsInNlc3Npb25JbmRleCI6MX0seyJrZXkiOiJhcHBLZXkiLCJ2YWx1ZSI6IntjaGFuZ2VtZX0iLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoic2VjcmV0Iiwic2Vzc2lvblZhbHVlIjoie2NoYW5nZW1lfSIsInNlc3Npb25JbmRleCI6Mn0seyJrZXkiOiJjdXN0b21lcklkIiwidmFsdWUiOiJ7Y2hhbmdlbWV9IiwiZW5hYmxlZCI6dHJ1ZSwic2Vzc2lvblZhbHVlIjoie2NoYW5nZW1lfSIsInNlc3Npb25JbmRleCI6M31d)
2. Select the _Test Drive_ environment (top right) and update `partnerId`, `partnerSecret`, `appKey` and `customerId` variables
3. Click _Send_ on individual requests, or _Run collection_
4. Explore the _Pre-request Script_ and _Tests_ tabs, and update the collection as you wish

### Run the Collection on the Command Line

1. Clone this repository
2. Run `npx newman run finicity.postman_collection.json --env-var partnerId=*** --env-var partnerSecret=*** --env-var appKey=*** --env-var customerId=***`
3. Expected result:

```
โโโโโโโโโโโโโโโโโโโโโโโโโโโฌโโโโโโโโโโโโโโโโโโโโโฌโโโโโโโโโโโโโโโโโโโโโ
โ                         โ           executed โ             failed โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโค
โ              iterations โ                  1 โ                  0 โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโค
โ                requests โ                 93 โ                  0 โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโค
โ            test-scripts โ                189 โ                  0 โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโค
โ      prerequest-scripts โ                129 โ                  0 โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโผโโโโโโโโโโโโโโโโโโโโโค
โ              assertions โ                 75 โ                  0 โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโดโโโโโโโโโโโโโโโโโโโโโดโโโโโโโโโโโโโโโโโโโโโค
โ total run duration: 51.7s                                         โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโค
โ total data received: 241.85kB (approx)                            โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโค
โ average response time: 478ms [min: 200ms, max: 3.9s, s.d.: 458ms] โ
โโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโโ
```

### Run the Collection in GitHub

1. [Fork this repository](https://github.com/Finicity-Mastercard/finicity-openapi/fork)
2. Go to _Settings_ > _Secrets_ > _Actions_
3. Create new repository secrets: `PARTNER_ID`, `PARTNER_SECRET`, `APP_KEY` and `CUSTOMER_ID`
4. Enable workflows in the _Actions_ tab
5. Click _Run workflow_ under _Newman_. Expected result: :heavy_check_mark:

## What's Next?

* Postman allows you to generate [code snippets](https://learning.postman.com/docs/sending-requests/generate-code-snippets/) you can use into your application
* You may also be interested in generating an API client from the [Finicity API specification](https://github.com/Finicity-Mastercard/finicity-openapi)

## Guidelines

The Finicity Postman Collection was created from the [Finicity API specification](https://github.com/Finicity-Mastercard/finicity-openapi) and must be maintained accordingly.
