---
name: Adyen
description: >-
  End-to-end payments, data, and financial management in a single solution. Meet
  the financial technology platform that helps you realize your ambitions
  faster.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/adyen.yml
created: 2023/11/13
modified: 2024/02/19
specificationVersion: '0.16'
tags: []
apis:
  - name: Adyen Accounting Notifications API
    description: >-
      Adyen sends notifications through webhooks to inform your system about
      incoming and outgoing transfers in your platform. You can use these
      webhooks to build your implementation. For example, you can use this
      information to update balances in your own dashboards or to keep track of
      incoming funds.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/classic/configure-notifications/
    baseURL: https://cal-test.adyen.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/classic/configure-notifications/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Accounting Notifications
            x-timestamp: '2023-02-10T11:25:40Z'
          x-groups:
            - General
          tags: []
          x-staticResponse: response.json
          webhooks:
            balancePlatform.transfer.created:
              post:
                tags:
                  - General
                summary: Transfer created
                description: >-
                  Adyen sends this webhook when there are fund movements on your
                  platform.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.transfer.created
                x-groupName: General
                x-sortIndex: 0
                x-methodName: transferCreated
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-transfer-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.transfer.created-balancePlatform-transfer-created
                      schema:
                        $ref: '#/components/schemas/TransferNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-transfer-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.transfer.updated:
              post:
                tags:
                  - General
                summary: Transfer updated
                description: >+
                  Adyen sends this webhook when the status of a transfer
                  changes. Use the `data.id` to track the original transfer
                  resource in the
                  [balancePlatform.transfer.created](https://docs.adyen.com/api-explorer/accounting-webhooks/1/post/balancePlatform.transfer.created)
                  webhook.


                  The `status` field indicates the event that triggered the
                  webhook. 

                x-addedInVersion: '1'
                operationId: post-balancePlatform.transfer.updated
                x-groupName: General
                x-sortIndex: 0
                x-methodName: transferUpdated
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-transfer-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.transfer.updated-balancePlatform-transfer-updated
                      schema:
                        $ref: '#/components/schemas/TransferNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-transfer-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-one-error
              message: One Tag
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/accounting-notifications-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/accounting-notifications-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-accounting-notifications-api
  - name: Adyen Account API
    description: >-
      This API is used for the classic integration. If you are just starting
      your implementation, refer to our new integration guide instead. The
      Account API provides endpoints for managing account-related entities on
      your platform. These related entities include account holders, accounts,
      bank accounts, shareholders, and verification-related documents. The
      management operations include actions such as creation, retrieval,
      updating, and deletion of them.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/Account/6/overview
    baseURL: https://cal-test.adyen.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/Account/6/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Account API
            x-timestamp: '2023-05-30T15:27:20Z'
          x-groups:
            - Account holders
            - Accounts
            - Verification
          tags:
            - name: Account holders
            - name: Verifications
            - name: Accounts
          paths:
            /checkAccountHolder:
              post:
                tags:
                  - Triggers
                  - Verification
                  - Account
                  - Holders
                summary: Trigger verification
                description: >-
                  Triggers the verification of an account holder even if the
                  checks are not yet required for the volume that they are
                  currently processing.
            /closeAccount:
              post:
                tags:
                  - Close
                  - An
                  - Account
                  - Account
                  - Holders
                summary: Close an account
                description: >-
                  Closes an account. If an account is closed, you cannot process
                  transactions, pay out its funds, or reopen it. If payments are
                  made to a closed account, the payments are sent to your liable
                  account.
            /closeAccountHolder:
              post:
                tags:
                  - Close
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                summary: Close an account holder
                description: >-
                  Changes the [status of an account
                  holder](https://docs.adyen.com/marketplaces-and-platforms/classic/account-holders-and-accounts#account-holder-statuses)
                  to **Closed**. This state is final. If an account holder is
                  closed, you can't process transactions, pay out funds, or
                  reopen it. If payments are made to an account of an account
                  holder with a **Closed**
                  [`status`](https://docs.adyen.com/api-explorer/#/Account/latest/post/getAccountHolder__resParam_verification-accountHolder-checks-status),
                  the payments are sent to your liable account.
            /closeStores:
              post:
                tags:
                  - Close
                  - Stores
                  - Account
                  - Holders
                  - Stores
                summary: Close stores
                description: Closes stores associated with an account holder.
            /createAccount:
              post:
                tags:
                  - Create
                  - An
                  - Account
                  - Account
                  - Holders
                  - Stores
                summary: Create an account
                description: >-
                  Creates an account under an account holder. An account holder
                  can have [multiple
                  accounts](https://docs.adyen.com/marketplaces-and-platforms/classic/account-holders-and-accounts#create-additional-accounts).
            /createAccountHolder:
              post:
                tags:
                  - Create
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                  - Stores
                summary: Create an account holder
                description: >-
                  Creates an account holder that [represents the sub-merchant's
                  entity](https://docs.adyen.com/marketplaces-and-platforms/classic/account-structure#your-platform)
                  in your platform. The details that you need to provide in the
                  request depend on the sub-merchant's legal entity type. For
                  more information, refer to [Account holder and
                  accounts](https://docs.adyen.com/marketplaces-and-platforms/classic/account-holders-and-accounts#legal-entity-types).
            /deleteBankAccounts:
              post:
                tags:
                  - Delete
                  - Bank
                  - Accounts
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                summary: Delete bank accounts
                description: 'Deletes bank accounts associated with an account holder. '
            /deleteLegalArrangements:
              post:
                tags:
                  - Delete
                  - Legal
                  - Arrangements
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                summary: Delete legal arrangements
                description: >-
                  Deletes legal arrangements and/or legal arrangement entities
                  associated with an account holder.
            /deletePayoutMethods:
              post:
                tags:
                  - Delete
                  - Payouts
                  - Methods
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                summary: Delete payout methods
                description: Deletes payout methods associated with an account holder.
            /deleteShareholders:
              post:
                tags:
                  - Delete
                  - Shareholders
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                summary: Delete shareholders
                description: Deletes shareholders associated with an account holder.
            /deleteSignatories:
              post:
                tags:
                  - Delete
                  - Signatories
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                summary: Delete signatories
                description: Deletes signatories associated with an account holder.
            /getAccountHolder:
              post:
                tags:
                  - Get
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                summary: Get an account holder
                description: Returns the details of an account holder.
            /getTaxForm:
              post:
                tags:
                  - Get
                  - Taxes
                  - Forms
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                summary: Get a tax form
                description: >-
                  Generates a tax form for account holders operating in the US.
                  For more information, refer to [Providing tax
                  forms](https://docs.adyen.com/marketplaces-and-platforms/classic/tax-forms).
            /getUploadedDocuments:
              post:
                tags:
                  - Get
                  - Documents
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                summary: Get documents
                description: >
                  Returns documents that were previously uploaded for an account
                  holder. Adyen uses the documents during the [verification
                  process](https://docs.adyen.com/marketplaces-and-platforms/classic/verification-process).
            /suspendAccountHolder:
              post:
                tags:
                  - Suspend
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                summary: Suspend an account holder
                description: >-
                  Changes the [status of an account
                  holder](https://docs.adyen.com/marketplaces-and-platforms/classic/account-holders-and-accounts#account-holder-statuses)
                  to **Suspended**.
            /unSuspendAccountHolder:
              post:
                tags:
                  - Unsuspend
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                  - Suspend
                summary: Unsuspend an account holder
                description: >-
                  Changes the [status of an account
                  holder](https://docs.adyen.com/marketplaces-and-platforms/classic/account-holders-and-accounts#account-holder-statuses)
                  from **Suspended** to **Inactive**. 

                  Account holders can have a **Suspended**
                  [`status`](https://docs.adyen.com/api-explorer/#/Account/latest/post/getAccountHolder__resParam_verification-accountHolder-checks-status)
                  if you suspend them through the
                  [`/suspendAccountHolder`](https://docs.adyen.com/api-explorer/#/Account/v5/post/suspendAccountHolder)
                  endpoint or if a verification deadline expires.


                  You can only unsuspend account holders if they do not have
                  verification checks with a **FAILED**
                  [`status`](https://docs.adyen.com/api-explorer/#/Account/latest/post/getAccountHolder__resParam_verification-accountHolder-checks-status).
            /updateAccount:
              post:
                tags:
                  - Update
                  - An
                  - Account
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                  - Suspend
                summary: Update an account
                description: Updates the description or payout schedule of an account.
            /updateAccountHolder:
              post:
                tags:
                  - Update
                  - An
                  - Account
                  - Holders
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                  - Suspend
                summary: Update an account holder
                description: >+
                  Updates the `accountHolderDetails` and `processingTier` of an
                  account holder, and adds bank accounts and shareholders.


                  When updating `accountHolderDetails`, parameters that are not
                  included in the request are left unchanged except for the
                  following object:


                  * `metadata`: Updating the metadata replaces the entire
                  object. This means that to update an existing key-value pair,
                  you must provide the changes, as well as other existing
                  key-value pairs.


                  When updating any field in the following objects, you must
                  submit all the fields required for validation:

                   * `address`

                  * `fullPhoneNumber`


                  * `bankAccountDetails.BankAccountDetail`


                  * `businessDetails.shareholders.ShareholderContact`

                   For example, to update the `address.postalCode`, you must also submit the `address.country`, `.city`, `.street`, `.postalCode`, and possibly `.stateOrProvince` so that the address can be validated.

                  To add a bank account or shareholder, provide the bank account
                  or shareholder details without a `bankAccountUUID` or a
                  `shareholderCode`.

            /updateAccountHolderState:
              post:
                tags:
                  - Update
                  - Payouts
                  - Or
                  - Processing
                  - States
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                  - Suspend
                  - States
                summary: Update payout or processing state
                description: >-
                  Disables or enables the processing or payout state of an
                  account holder.
            /uploadDocument:
              post:
                tags:
                  - Uploads
                  - Document
                  - Account
                  - Holders
                  - Stores
                  - Bank
                  - Accounts
                  - Legal
                  - Arrangements
                  - Payouts
                  - Methods
                  - Shareholders
                  - Signatories
                  - Taxes
                  - Forms
                  - Uploaded
                  - Documents
                  - Suspend
                  - States
                  - Document
                summary: Upload a document
                description: >-
                  Uploads a document for an account holder. Adyen uses the
                  documents during the [verification
                  process](https://docs.adyen.com/marketplaces-and-platfo
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/accounts-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/accounts-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-account-api
  - name: Adyen Authentication Webhooks API
    description: >-
      Adyen sends webhooks to inform your system about events related to
      cardholder authentication.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/development-resources/webhooks/
    baseURL: https://cal-test.adyen.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/development-resources/webhooks/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Authentication Webhooks
          tags:
            - name: General
          webhooks:
            balancePlatform.authentication.created:
              post:
                tags:
                  - General
                summary: Cardholder authenticated
                description: >-
                  Adyen sends this webhook when the process of cardholder
                  authentication is finalized, whether it is completed
                  successfully, fails, or expires.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.authentication.created
                x-sortIndex: 1
                x-methodName: cardholderAuthenticated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-authentication-created-authenticated-challenge:
                          $ref: >-
                            #/components/examples/post-balancePlatform.authentication.created-balancePlatform-authentication-created-authenticated-challenge
                        balancePlatform-authentication-created-authenticated-frictionless:
                          $ref: >-
                            #/components/examples/post-balancePlatform.authentication.created-balancePlatform-authentication-created-authenticated-frictionless
                        balancePlatform-authentication-created-rejected:
                          $ref: >-
                            #/components/examples/post-balancePlatform.authentication.created-balancePlatform-authentication-created-rejected
                      schema:
                        $ref: '#/components/schemas/AuthenticationNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-authentication-created-authenticated-challenge:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-authentication-created-authenticated-frictionless:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-authentication-created-rejected:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/authentication-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/authentication-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-authentication-webhooks-api
  - name: Adyen Balance Control API
    description: >-
      The Balance Control API lets you transfer funds between merchant accounts
      that belong to the same legal entity and are under the same company
      account.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/BalanceControl/1/overview
    baseURL: https://cal-test.adyen.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/BalanceControl/1/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Balance Control API
          x-groups:
            - General
          tags:
            - name: General
          paths:
            /balanceTransfer:
              post:
                tags:
                  - Start
                  - Balance
                  - Transfers
                  - Transfers
                summary: Start a balance transfer
                description: >
                  Starts a balance transfer request between merchant accounts.
                  The following conditions must be met before you can
                  successfully transfer balances:


                  * The source and destination merchant accounts must be under
                  the same company account and legal entity.


                  * The source merchant account must have sufficient funds.


                  * The source and destination merchant accounts must have at
                  least one common processing currency.


                  When sending multiple API requests with the same source and
                  destination merchant accounts, send the requests sequentially
                  and *not* in parallel. Some requests may not be processed if 
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/balance-control-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/balance-control-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-balance-control-api
  - name: Adyen BinLookup API
    description: >-
      The BIN Lookup API provides endpoints for retrieving information, such as
      cost estimates, and 3D Secure supported version based on a given BIN.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/BinLookup/52/overview
    baseURL: https://pal-test.adyen.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/BinLookup/52/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen BinLookup API
          tags:
            - name: General
          paths:
            /get3dsAvailability:
              post:
                tags:
                  - Checks
                  - If
                  - Secure
                  - Is
                  - Available
                  - Availability
                summary: Check if 3D Secure is available
                description: >-
                  Verifies whether 3D Secure is available for the specified BIN
                  or card brand. For 3D Secure 2, this endpoint also returns
                  device fingerprinting keys.


                  For more information, refer to [3D Secure
                  2](https://docs.adyen.com/online-payments/3d-secure/native-3ds2).
            /getCostEstimate:
              post:
                tags:
                  - Get
                  - Fees
                  - Cost
                  - Estimates
                  - Availability
                  - Cost
                  - Estimates
                summary: Get a fees cost estimate
                description: >-
                  >This API is available only for merchants operating in
                  Australia, the EU, and the UK.


                  Use the Adyen Cost Estimation API to pre-calculate interchange
                  and scheme fee costs. Knowing these costs prior actual payment
                  authorisation gives you an opportunity to charge those costs
                  to the cardholder, if necessary.


                  To retrieve this information, make the call to the
                  `/getCostEstimate` endpoint. The response to this call
                  contains the amount of the interchange and scheme fees charged
                  by the network for this transaction, and also which
                  surcharging policy is possible (based on current regulations).


                  > Since not all information is known in advance (for example,
                  if the cardholder will successfully authenticate via 3D Secure
                  or if you also plan to provide additional Level 2/3 data), the
                  returned amounts are based on a set of assumption criteria you
                  defi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/binlookup-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/binlookup-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-binlookup-api
  - name: Adyen Checkout API
    description: This is the description of your API.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/Checkout/71/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/Checkout/71/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Checkout API
          tags:
            - name: Payments
            - name: Donations
            - name: Payment links
            - name: Modifications
            - name: Recurring
            - name: Orders
            - name: Utilities
            - name: Classic Checkout SDK
          paths:
            /applePay/sessions:
              post:
                tags:
                  - Get
                  - An
                  - Apple
                  - Pay
                  - Sessions
                  - Pay
                  - Sessions
                summary: Get an Apple Pay session
                description: >-
                  You need to use this endpoint if you have an API-only
                  integration with Apple Pay which uses Adyen's Apple Pay
                  certificate.


                  The endpoint returns the Apple Pay session data which you need
                  to complete the [Apple Pay session
                  validation](https://docs.adyen.com/payment-methods/apple-pay/api-only?tab=adyen-certificate-validation_1#complete-apple-pay-session-validation).
            /cancels:
              post:
                tags:
                  - Cancel
                  - An
                  - Authorised
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                summary: Cancel an authorised payment
                description: >-
                  Cancels the authorisation on a payment that has not yet been
                  [captured](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/captures),
                  and returns a unique reference for this request. You get the
                  outcome of the request asynchronously, in a
                  [**TECHNICAL_CANCEL**
                  webhook](https://docs.adyen.com/online-payments/cancel#cancellation-webhook).


                  If you want to cancel a payment using the
                  [`pspReference`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments__resParam_pspReference),
                  use the
                  [`/payments/{paymentPspReference}/cancels`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/cancels)
                  endpoint instead.


                  If you want to cancel a payment but are not sure whether it
                  has been captured, use the
                  [`/payments/{paymentPspReference}/reversals`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/reversals)
                  endpoint instead.


                  For more information, refer to
                  [Cancel](https://docs.adyen.com/online-payments/cancel).
            /cardDetails:
              post:
                tags:
                  - Get
                  - The
                  - Lists
                  - Of
                  - Brands
                  - 'On'
                  - Cards
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                summary: Get the list of brands on the card
                description: >+
                  Send a request with at least the first 6 digits of the card
                  number to get a response with an array of brands on the card.
                  If you include [your supported
                  brands](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/cardDetails__reqParam_supportedBrands)
                  in the request, the response also tells you if you support
                  each [brand that was
                  identified](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/cardDetails__resParam_details).


                  If you have an API-only integration and collect card data, use
                  this endpoint to find out if the shopper's card is co-branded.
                  For co-branded cards, you must let the shopper choose the
                  brand to pay with  if you support both brands.

            /donations:
              post:
                tags:
                  - Start
                  - Transactions
                  - For
                  - Donations
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                summary: Start a transaction for donations
                description: >-
                  Takes in the donation token generated by the `/payments`
                  request and uses it to make the donation for the donation
                  account specified in the request.


                  For more information, see
                  [Donations](https://docs.adyen.com/online-payments/donations).
            /orders:
              post:
                tags:
                  - Create
                  - An
                  - Orders
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                summary: Create an order
                description: >-
                  Creates an order to be used for partial payments. Make a POST
                  `/orders` call before making a `/payments` call when
                  processing payments with different payment methods.
            /orders/cancel:
              post:
                tags:
                  - Cancel
                  - An
                  - Orders
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                summary: Cancel an order
                description: >-
                  Cancels an order. Cancellation of an order results in an
                  automatic rollback of all payments made in the order, either
                  by canceling or refunding the payment, depending on the type
                  of payment method.
            /originKeys:
              post:
                tags:
                  - Create
                  - Origin
                  - Keys
                  - Values
                  - For
                  - Domains
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                summary: Create originKey values for domains
                description: >-
                  This operation takes the origin domains and returns a JSON
                  object containing the corresponding origin keys for the
                  domains. 

                  > If you're still using origin key for your Web Drop-in or
                  Components integration, we recommend [switching to client
                  key](https://docs.adyen.com/development-resources/client-side-authentication/migrate-from-origin-key-to-client-key).
                  This allows you to use a single key for all origins, add or
                  remove origins without generating a new key, and detect the
                  card type from the number entered in your payment form. 
            /paymentLinks:
              post:
                tags:
                  - Create
                  - Payments
                  - Link
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                summary: Create a payment link
                description: >-
                  Creates a payment link to our hosted payment form where
                  shoppers can pay. The list of payment methods presented to the
                  shopper depends on the `currency` and `country` parameters
                  sent in the request.


                  For more information, refer to [Pay by Link
                  documentation](https://docs.adyen.com/online-payments/pay-by-link#create-payment-links-through-api).
            /paymentLinks/{linkId}:
              get:
                tags:
                  - Get
                  - Payments
                  - Link
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                summary: Get a payment link
                description: >-
                  Retrieves the payment link details using the payment link
                  `id`.
              patch:
                tags:
                  - Update
                  - The
                  - Status
                  - Of
                  - Payments
                  - Link
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                summary: Update the status of a payment link
                description: >-
                  Updates the status of a payment link. Use this endpoint to
                  [force the expiry of a payment
                  link](https://docs.adyen.com/online-payments/pay-by-link#update-payment-link-status).
            /paymentMethods:
              post:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Available
                  - Payments
                  - Methods
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                summary: Get a list of available payment methods
                description: >-
                  Queries the available payment methods for a transaction based
                  on the transaction context (like amount, country, and
                  currency). Besides giving back a list of the available payment
                  methods, the response also returns which input details you
                  need to collect from the shopper (to be submitted to
                  `/payments`).


                  Although we highly recommend using this endpoint to ensure you
                  are always offering the most up-to-date list of payment
                  methods, its usage is optional. You can, for example, also
                  cache the `/paymentMethods` response and update it once a
                  week.
            /paymentMethods/balance:
              post:
                tags:
                  - Get
                  - The
                  - Balance
                  - Of
                  - Gifts
                  - Cards
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                summary: Get the balance of a gift card
                description: >-
                  Retrieves the balance remaining on a shopper's gift card. To
                  check a gift card's balance, make a POST
                  `/paymentMethods/balance` call and include the gift card's
                  details inside a `paymentMethod` object.
            /paymentSession:
              post:
                tags:
                  - Create
                  - Payments
                  - Sessions
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                summary: Create a payment session
                description: >-
                  Provides the data object that can be used to start the
                  Checkout SDK. To set up the payment, pass its amount,
                  currency, and other required parameters. We use this to
                  optimise the payment flow and perform better risk assessment
                  of the transaction.


                  For more information, refer to [How it
                  works](https://docs.adyen.com/online-payments#howitworks).
            /payments:
              post:
                tags:
                  - Start
                  - Transactions
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                summary: Start a transaction
                description: >-
                  Sends payment parameters (like amount, country, and currency)
                  together with other required input details collected from the
                  shopper. To know more about required parameters for specific
                  payment methods, refer to our [payment method
                  guides](https://docs.adyen.com/payment-methods). 

                  The response depends on the [payment
                  flow](https://docs.adyen.com/payment-methods#payment-flow):

                  * For a direct flow, the response includes a `pspReference`
                  and a `resultCode` with the payment result, for example
                  **Authorised** or **Refused**. 

                  * For a redirect or additional action, the response contains
                  an `action` object. 
            /payments/details:
              post:
                tags:
                  - Submit
                  - Details
                  - For
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                summary: Submit details for a payment
                description: >+
                  Submits details for a payment created using `/payments`. This
                  step is only needed when no final state has been reached on
                  the `/payments` request, for example when the shopper was
                  redirected to another page to complete the payment.

            /payments/result:
              post:
                tags:
                  - Verify
                  - Payments
                  - Results
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                summary: Verify a payment result
                description: >-
                  Verifies the payment result using the payload returned from
                  the Checkout SDK.


                  For more information, refer to [How it
                  works](https://docs.adyen.com/online-payments#howitworks).
            /payments/{paymentPspReference}/amountUpdates:
              post:
                tags:
                  - Update
                  - An
                  - Authorised
                  - Amount
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                summary: Update an authorised amount
                description: >-
                  Increases or decreases the authorised payment amount and
                  returns a unique reference for this request. You get the
                  outcome of the request asynchronously, in an
                  [**AUTHORISATION_ADJUSTMENT**
                  webhook](https://docs.adyen.com/development-resources/webhooks/understand-notifications#event-codes).


                  You can only update authorised amounts that have not yet been
                  [captured](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/captures).


                  The amount you specify in the request is the updated amount,
                  which is larger or smaller than the initial authorised amount.


                  For more information, refer to [Authorisation
                  adjustment](https://docs.adyen.com/online-payments/adjust-authorisation#use-cases).
            /payments/{paymentPspReference}/cancels:
              post:
                tags:
                  - Cancel
                  - An
                  - Authorised
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                summary: Cancel an authorised payment
                description: >-
                  Cancels the authorisation on a payment that has not yet been
                  [captured](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/paymentPspReference/captures),
                  and returns a unique reference for this request. You get the
                  outcome of the request asynchronously, in a [**CANCELLATION**
                  webhook](https://docs.adyen.com/online-payments/cancel#cancellation-webhook).


                  If you want to cancel a payment but don't have the
                  [`pspReference`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments__resParam_pspReference),
                  use the
                  [`/cancels`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/cancels)
                  endpoint instead.


                  If you want to cancel a payment but are not sure whether it
                  has been captured, use the
                  [`/payments/{paymentPspReference}/reversals`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/reversals)
                  endpoint instead.


                  For more information, refer to
                  [Cancel](https://docs.adyen.com/online-payments/cancel).
            /payments/{paymentPspReference}/captures:
              post:
                tags:
                  - Capture
                  - An
                  - Authorised
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                summary: Capture an authorised payment
                description: >2-
                   Captures an authorised payment and returns a unique reference for this request. You get the outcome of the request asynchronously, in a [**CAPTURE** webhook](https://docs.adyen.com/online-payments/capture#capture-notification).

                  You can capture either the full authorised amount or a part of
                  the authorised amount. By default, any unclaimed amount after
                  a partial capture gets cancelled. This does not apply if you
                  enabled multiple partial captures on your account and the
                  payment method supports multiple partial captures. 


                  [Automatic
                  capture](https://docs.adyen.com/online-payments/capture#automatic-capture)
                  is the default setting for most payment methods. In these
                  cases, you don't need to make capture requests. However,
                  making capture requests for payments that are captured
                  automatically does not result in double charges.


                  For more information, refer to
                  [Capture](https://docs.adyen.com/online-payments/capture).
            /payments/{paymentPspReference}/refunds:
              post:
                tags:
                  - Refunds
                  - Captured
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                summary: Refund a captured payment
                description: >-
                  Refunds a payment that has been
                  [captured](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/captures),
                  and returns a unique reference for this request. You get the
                  outcome of the request asynchronously, in a [**REFUND**
                  webhook](https://docs.adyen.com/online-payments/refund#refund-webhook).


                  You can refund either the full captured amount or a part of
                  the captured amount. You can also perform multiple partial
                  refunds, as long as their sum doesn't exceed the captured
                  amount.


                  > Some payment methods do not support partial refunds. To
                  learn if a payment method supports partial refunds, refer to
                  the payment method page such as
                  [cards](https://docs.adyen.com/payment-methods/cards#supported-cards),
                  [iDEAL](https://docs.adyen.com/payment-methods/ideal), or
                  [Klarna](https://docs.adyen.com/payment-methods/klarna). 


                  If you want to refund a payment but are not sure whether it
                  has been captured, use the
                  [`/payments/{paymentPspReference}/reversals`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/reversals)
                  endpoint instead.


                  For more information, refer to
                  [Refund](https://docs.adyen.com/online-payments/refund).
            /payments/{paymentPspReference}/reversals:
              post:
                tags:
                  - Refunds
                  - Or
                  - Cancel
                  - Payments
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                  - Reversals
                summary: Refund or cancel a payment
                description: >-
                  [Refunds](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/refunds)
                  a payment if it has already been captured, and
                  [cancels](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/payments/{paymentPspReference}/cancels)
                  a payment if it has not yet been captured. Returns a unique
                  reference for this request. You get the outcome of the request
                  asynchronously, in a [**CANCEL_OR_REFUND**
                  webhook](https://docs.adyen.com/online-payments/reverse#cancel-or-refund-webhook).


                  The reversed amount is always the full payment amount.

                  > Do not use this request for payments that involve multiple
                  partial captures.


                  For more information, refer to
                  [Reversal](https://docs.adyen.com/online-payments/reversal).
            /sessions:
              post:
                tags:
                  - Create
                  - Payments
                  - Sessions
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                  - Reversals
                summary: Create a payment session
                description: >-
                  Creates a payment session for [Web
                  Drop-in](https://docs.adyen.com/online-payments/web-drop-in)
                  and [Web
                  Components](https://docs.adyen.com/online-payments/web-components)
                  integrations.


                  The response contains encrypted payment session data. The
                  front end then uses the session data to make any required
                  server-side calls for the payment flow.


                  You get the payment outcome asynchronously, in an
                  [AUTHORISATION](https://docs.adyen.com/api-explorer/#/Webhooks/latest/post/AUTHORISATION)
                  webhook.
            /sessions/{sessionId}:
              get:
                tags:
                  - Get
                  - The
                  - Results
                  - Of
                  - Payments
                  - Sessions
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                  - Reversals
                summary: Get the result of a payment session
                description: >-
                  Returns the status of the payment session with the `sessionId`
                  and `sessionResult` specified in the path.
            /storedPaymentMethods:
              get:
                tags:
                  - Get
                  - Tokens
                  - For
                  - Stored
                  - Payments
                  - Details
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                  - Reversals
                  - Payments
                summary: Get tokens for stored payment details
                description: >+
                  Lists the tokens for stored payment details for the shopper
                  identified in the path, if there are any available. The token
                  ID can be used with payment requests for the shopper's
                  payment. A summary of the stored details is included.

            /storedPaymentMethods/{storedPaymentMethodId}:
              delete:
                tags:
                  - Delete
                  - Tokens
                  - For
                  - Stored
                  - Payments
                  - Details
                  - Pay
                  - Sessions
                  - Cancels
                  - Details
                  - Donations
                  - Orders
                  - Cancel
                  - Keys
                  - Links
                  - Link
                  - Identifiers
                  - Methods
                  - Balance
                  - Sessions
                  - Payments
                  - Results
                  - Psp
                  - References
                  - Amount
                  - Updates
                  - Captures
                  - Refunds
                  - Reversals
                  - Payments
                  - Stored
                  - Methods
                summary: Delete a token for stored payment details
                description: Deletes the token identified in the path. The token can no lo
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-response-post-201-status-code-info
              message: POST 201 Status Code
            - code: openapi-response-get-201-content-info
              message: POST Content
            - code: openapi-response-post-201-media-type-info
              message: JSON Media Type POST
            - code: openapi-response-post-201-media-type-schema-info
              message: Schema POST
            - code: openapi-response-post-201-schema-components-warn
              message: GET Response 201 Schema Components
            - code: openapi-response-post-201-schema-ref-error
              message: GET Response 201 Schema Ref
            - code: openapi-response-post-201-schema-ref-info
              message: GET Response 201 Schema Ref
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-parameters-path-names-snake-case-error
              message: Parameter Path Name Snake Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
            - code: openapi-no-request-body-on-delete-info
              message: DELETE Request Body
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-response-delete-204-status-code-info
              message: DELETE 204 Status Code
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/checkout-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/checkout-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-checkout-api
  - name: Adyen Configuration API
    description: >-
      The Configuration API enables you to create a platform where you can
      onboard your users as account holders and create balance accounts, cards,
      and business accounts.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/balanceplatform/2/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/balanceplatform/2/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Configuration API
          tags:
            - name: Platforms
            - name: Account holders
            - name: Balance accounts
            - name: Payment instruments
            - name: Payment instrument groups
            - name: Transaction rules
            - name: Bank account validation
            - name: Network tokens
            - name: Grant accounts
            - name: Grant offers
            - name: Functionality
            - name: Card orders
            - name: Transfer routes
          paths:
            /accountHolders:
              post:
                tags:
                  - Create
                  - An
                  - Account
                  - Holders
                  - Holders
                summary: Create an account holder
                description: >+
                  Creates an account holder linked to a [legal
                  entity](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities).

            /accountHolders/{id}:
              get:
                tags:
                  - Get
                  - An
                  - Account
                  - Holders
                  - Holders
                  - Identifiers
                summary: Get an account holder
                description: Returns an account holder.
              patch:
                tags:
                  - Update
                  - An
                  - Account
                  - Holders
                  - Holders
                  - Identifiers
                summary: Update an account holder
                description: >-
                  Updates an account holder. When updating an account holder
                  resource, if a parameter is not provided in the request, it is
                  left unchanged.
            /accountHolders/{id}/balanceAccounts:
              get:
                tags:
                  - Get
                  - All
                  - Balance
                  - Accounts
                  - Of
                  - An
                  - Account
                  - Holders
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                summary: Get all balance accounts of an account holder
                description: >-
                  Returns a paginated list of the balance accounts associated
                  with an account holder. To fetch multiple pages, use the query
                  parameters. 


                  For example, to limit the page to 5 balance accounts and skip
                  the first 10, use
                  `/accountHolders/{id}/balanceAccounts?limit=5&offset=10`.
            /accountHolders/{id}/taxForms:
              get:
                tags:
                  - Get
                  - Taxes
                  - Forms
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                summary: Get a tax form
                description: >-
                  Generates a tax form for account holders operating in the US.
                  For more information, refer to [Providing tax
                  forms](https://docs.adyen.com/marketplaces-and-platforms/us-tax-forms/).
            /balanceAccounts:
              post:
                tags:
                  - Create
                  - Balance
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                summary: Create a balance account
                description: >-
                  Creates a balance account that holds the funds of the
                  associated account holder.
            /balanceAccounts/{balanceAccountId}/sweeps:
              get:
                tags:
                  - Get
                  - All
                  - Sweeps
                  - For
                  - Balance
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                summary: Get all sweeps for a balance account
                description: >-
                  Returns a list of the sweeps configured for a balance account.


                  To fetch multiple pages, use the query parameters. For
                  example, to limit the page to 5 sweeps and to skip the first
                  10, use
                  `/balanceAccounts/{balanceAccountId}/sweeps?limit=5&offset=10`.
              post:
                tags:
                  - Create
                  - Sweep
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                summary: Create a sweep
                description: >-
                  Creates a sweep that results in moving funds from or to a
                  balance account.


                  A sweep pulls in or pushes out funds based on a defined
                  schedule, amount, currency, and a source or a destination.
            /balanceAccounts/{balanceAccountId}/sweeps/{sweepId}:
              delete:
                tags:
                  - Delete
                  - Sweep
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                summary: Delete a sweep
                description: Deletes a sweep for a balance account.
              get:
                tags:
                  - Get
                  - Sweep
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                summary: Get a sweep
                description: Returns a sweep.
              patch:
                tags:
                  - Update
                  - Sweep
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                summary: Update a sweep
                description: >-
                  Updates a sweep. When updating a sweep resource, note that if
                  a request parameter is not provided, the parameter is left
                  unchanged.
            /balanceAccounts/{id}:
              get:
                tags:
                  - Get
                  - Balance
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                summary: Get a balance account
                description: >-
                  Returns a balance account and its balances for the default
                  currency and other currencies with a non-zero balance.
              patch:
                tags:
                  - Update
                  - Balance
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                summary: Update a balance account
                description: Updates a balance account.
            /balanceAccounts/{id}/paymentInstruments:
              get:
                tags:
                  - Get
                  - Payments
                  - Instruments
                  - Linked
                  - To
                  - Balance
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                summary: Get payment instruments linked to a balance account
                description: >-
                  Returns a paginated list of the payment instruments associated
                  with a balance account. 


                  To fetch multiple pages, use the query parameters.For example,
                  to limit the page to 3 payment instruments which are in active
                  status and to skip the first 6, use
                  `/balanceAccounts/{id}/paymentInstruments?limit=3&offset=6&status=active`.
            /balancePlatforms/{id}:
              get:
                tags:
                  - Get
                  - Balance
                  - Platforms
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                summary: Get a balance platform
                description: Returns a balance platform.
            /balancePlatforms/{id}/accountHolders:
              get:
                tags:
                  - Get
                  - All
                  - Account
                  - Holders
                  - Under
                  - Balance
                  - Platforms
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                summary: Get all account holders under a balance platform
                description: >-
                  Returns a paginated list of all the account holders that
                  belong to the balance platform. To fetch multiple pages, use
                  the query parameters. 


                  For example, to limit the page to 5 account holders and to
                  skip the first 20, use
                  `/balancePlatforms/{id}/accountHolders?limit=5&offset=20`.
            /cardorders:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Cards
                  - Orders
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                summary: Get a list of card orders
                description: Returns a paginated list of card orders.
            /cardorders/{id}/items:
              get:
                tags:
                  - Get
                  - Cards
                  - Orders
                  - Items
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                summary: Get card order items
                description: Returns the item list of a specific card order.
            /grantAccounts/{id}:
              get:
                tags:
                  - Get
                  - Grant
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                summary: Get a grant account
                description: >-
                  Returns the details of the [grant
                  account](https://docs.adyen.com/marketplaces-and-platforms/capital#grant-account).
            /grantOffers:
              get:
                tags:
                  - Get
                  - All
                  - Available
                  - Grant
                  - Offers
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                summary: Get all available grant offers
                description: >-
                  Returns a list of all [grant
                  offers](https://docs.adyen.com/marketplaces-and-platforms/capital#grant-offers)
                  available for `accountHolderId` specified as a query
                  parameter.
            /grantOffers/{grantOfferId}:
              get:
                tags:
                  - Get
                  - Grant
                  - Offers
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                summary: Get a grant offer
                description: Returns the details of a single grant offer.
            /networkTokens/{networkTokenId}:
              get:
                tags:
                  - Get
                  - Networks
                  - Tokens
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                summary: Get a network token
                description: Returns the details of a network token.
              patch:
                tags:
                  - Update
                  - Networks
                  - Tokens
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                summary: Update a network token
                description: Updates the status of the network token.
            /paymentInstrumentGroups:
              post:
                tags:
                  - Create
                  - Payments
                  - Instruments
                  - Group
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                summary: Create a payment instrument group
                description: >-
                  Creates a payment instrument group to associate and group
                  payment instrument resources together. You can apply a
                  transaction rule to a payment instrument group.
            /paymentInstrumentGroups/{id}:
              get:
                tags:
                  - Get
                  - Payments
                  - Instruments
                  - Group
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                summary: Get a payment instrument group
                description: Returns the details of a payment instrument group.
            /paymentInstrumentGroups/{id}/transactionRules:
              get:
                tags:
                  - Get
                  - All
                  - Transactions
                  - Rules
                  - For
                  - Payments
                  - Instruments
                  - Group
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                summary: Get all transaction rules for a payment instrument group
                description: >-
                  Returns a list of all the transaction rules associated with a
                  payment instrument group.
            /paymentInstruments:
              post:
                tags:
                  - Create
                  - Payments
                  - Instruments
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                summary: Create a payment instrument
                description: >-
                  Creates a payment instrument to issue a physical card, a
                  virtual card, or a business account to your user.

                   For more information, refer to [Issue cards](https://docs.adyen.com/issuing/create-cards) or [Issue business accounts](https://docs.adyen.com/marketplaces-and-platforms/business-accounts).
            /paymentInstruments/{id}:
              get:
                tags:
                  - Get
                  - Payments
                  - Instruments
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                summary: Get a payment instrument
                description: Returns the details of a payment instrument.
              patch:
                tags:
                  - Update
                  - Payments
                  - Instruments
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                summary: Update a payment instrument
                description: >-
                  Updates a payment instrument. Once a payment instrument is
                  already active, you can only update its status. However, for
                  cards created with **inactive** status, you can still update
                  the balance account associated with the card.
            /paymentInstruments/{id}/networkTokens:
              get:
                tags:
                  - Lists
                  - Networks
                  - Tokens
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                summary: List network tokens
                description: List the network tokens connected to a payment instrument.
            /paymentInstruments/{id}/reveal:
              get:
                tags:
                  - Get
                  - The
                  - Of
                  - Payments
                  - Instruments
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                summary: Get the PAN of a payment instrument
                description: >-
                  Returns the primary account number (PAN) of a payment
                  instrument.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/issuing/manage-access/api-credentials-web-service#api-permissions):


                  * Balance Platform BCL PCI role
            /paymentInstruments/{id}/transactionRules:
              get:
                tags:
                  - Get
                  - All
                  - Transactions
                  - Rules
                  - For
                  - Payments
                  - Instruments
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                summary: Get all transaction rules for a payment instrument
                description: >-
                  Returns a list of transaction rules associated with a payment
                  instrument.
            /pins/change:
              post:
                tags:
                  - Change
                  - Pin
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                summary: Change Pin
                description: Change Pin
            /pins/publicKey:
              get:
                tags:
                  - Get
                  - Public
                  - Keys
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                summary: Get RSA publicKey
                description: Get RSA publicKey
            /pins/reveal:
              post:
                tags:
                  - Reveal
                  - Pin
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                summary: Reveal Pin
                description: Reveal Pin
            /transactionRules:
              post:
                tags:
                  - Create
                  - Transactions
                  - Rules
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                summary: Create a transaction rule
                description: >-
                  Creates a [transaction
                  rule](https://docs.adyen.com/issuing/transaction-rules). When
                  your user makes a transaction with their Adyen-issued card,
                  the transaction is allowed or declined based on the conditions
                  and outcome defined in the transaction rule. You can apply the
                  transaction rule to several cards, such as all the cards in
                  your platform, or to a specific card. For use cases, see
                  [examples](https://docs.adyen.com/issuing/transaction-rules/examples).
            /transactionRules/{transactionRuleId}:
              delete:
                tags:
                  - Delete
                  - Transactions
                  - Rules
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                  - Rules
                summary: Delete a transaction rule
                description: Deletes a transaction rule.
              get:
                tags:
                  - Get
                  - Transactions
                  - Rules
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                  - Rules
                summary: Get a transaction rule
                description: Returns the details of a transaction rule.
              patch:
                tags:
                  - Update
                  - Transactions
                  - Rules
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                  - Rules
                summary: Update a transaction rule
                description: >-
                  Updates a transaction rule. 


                  * To update only the status of a transaction rule, send only
                  the `status` parameter. All other parameters not provided in
                  the request are left unchanged.


                  * When updating any other parameter, you need to send all
                  existing resource parameters. If you omit a parameter in the
                  request, that parameter is removed from the resource.
            /transferRoutes/calculate:
              post:
                tags:
                  - Calculate
                  - Transfers
                  - Routes
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                  - Rules
                  - Routes
                  - Calculate
                summary: Calculate transfer routes
                description: >-
                  Returns available transfer routes based on a combination of
                  transfer `country`, `currency`, `counterparty`, and
                  `priorities`. Use this endpoint to find optimal transfer
                  priorities and associated requirements before you [make a
                  transfer](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers).
            /validateBankAccountIdentification:
              post:
                tags:
                  - Validate
                  - Bank
                  - Account
                  - Holders
                  - Identifiers
                  - Balance
                  - Accounts
                  - Taxes
                  - Forms
                  - Account
                  - Sweeps
                  - Sweep
                  - Payments
                  - Instruments
                  - Platforms
                  - Card Orders
                  - Items
                  - Offers
                  - Grant
                  - Offers
                  - Tokens
                  - Networks
                  - Tokens
                  - Instruments
                  - Groups
                  - Transactions
                  - Rules
                  - Reveal
                  - Pins
                  - Change
                  - Keys
                  - Rules
                  - Routes
                  - Calculate
                  - Bank
                  - Identification
                summary: Validate a bank account
                description: >-
                  Validates bank account identification details. You can use
                  this endpoint to validate bank account details before you
                  [make a
                  transfer](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers)
                  or [create a transfer
                  instrument](https://docs.adyen.com/api-explorer/legalentity
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-parameters-path-names-snake-case-error
              message: Parameter Path Name Snake Case
            - code: openapi-no-request-body-on-delete-info
              message: DELETE Request Body
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-204-status-code-info
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-info
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-info
              message: 500 Status Code for DELETE Responses
            - code: openapi-operations-summary-length-error
              message: Operation Summary Length
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/configuration-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/configuration-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-configuration-api
  - name: Adyen Configuration Webhooks API
    description: >-
      Adyen sends webhooks to inform your system about events that occur in your
      platform. These events include, for example, when an account holders
      capabilities are updated, or when a sweep configuration is created or
      updated. When an event occurs, Adyen makes an HTTP POST request to a URL
      on your server and includes the details of the event in the request body.
      You can use these webhooks to build your implementation.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/balanceplatform-webhooks/1/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/api-explorer/balanceplatform-webhooks/1/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Configuration webhooks
          tags:
            - name: Account holder
            - name: Balance Accounts
            - name: Payment instrument
            - name: Card Orders
          x-staticResponse: response.json
          webhooks:
            balancePlatform.accountHolder.created:
              post:
                tags:
                  - Account holder
                summary: Account holder created
                description: >-
                  Adyen sends this webhook when you successfully [create an
                  account
                  holder](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/accountHolders).
                operationId: post-balancePlatform.accountHolder.created
                x-sortIndex: 1
                x-methodName: accountHolderCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-accountHolder-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.created-balancePlatform-accountHolder-created
                        balancePlatform-accountHolder-created-lem-v3:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.created-balancePlatform-accountHolder-created-lem-v3
                      schema:
                        $ref: '#/components/schemas/AccountHolderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-accountHolder-created:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-accountHolder-created-lem-v3:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.accountHolder.updated:
              post:
                tags:
                  - Account holder
                summary: Account holder updated
                description: >-
                  Adyen sends this webhook when you successfully [update an
                  account
                  holder](https://docs.adyen.com/api-explorer/balanceplatform/latest/patch/accountHolders/_id_).
                operationId: post-balancePlatform.accountHolder.updated
                x-sortIndex: 2
                x-methodName: accountHolderUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-accountHolder-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.updated-balancePlatform-accountHolder-updated
                        balancePlatform-accountHolder-updated-lem-v3:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.updated-balancePlatform-accountHolder-updated-lem-v3
                      schema:
                        $ref: '#/components/schemas/AccountHolderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-accountHolder-updated:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-accountHolder-updated-lem-v3:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccount.created:
              post:
                tags:
                  - Balance account
                summary: Balance account created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  balance
                  account](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts).
                operationId: post-balancePlatform.balanceAccount.created
                x-sortIndex: 1
                x-methodName: balanceAccountCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-balanceAccount-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccount.created-balancePlatform-balanceAccount-created
                      schema:
                        $ref: '#/components/schemas/BalanceAccountNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-balanceAccount-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccount.updated:
              post:
                tags:
                  - Balance account
                summary: Balance account updated
                description: >-
                  Adyen sends this webhook when you successfully [update a
                  balance
                  account](https://docs.adyen.com/api-explorer/balanceplatform/latest/patch/balanceAccounts/_id_).
                operationId: post-balancePlatform.balanceAccount.updated
                x-sortIndex: 2
                x-methodName: balanceAccountUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-balanceAccount-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccount.updated-balancePlatform-balanceAccount-updated
                      schema:
                        $ref: '#/components/schemas/BalanceAccountNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-balanceAccount-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.created:
              post:
                tags:
                  - Balance account
                summary: Sweep created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  sweep](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts/_balanceAccountId_/sweeps).
                operationId: post-balancePlatform.balanceAccountSweep.created
                x-sortIndex: 3
                x-methodName: sweepCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.created-balancePlatform-sweep-created
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.deleted:
              post:
                tags:
                  - Balance account
                summary: Sweep deleted
                description: >-
                  Adyen sends this webhook when you successfully [delete a
                  sweep](https://docs.adyen.com/api-explorer/balanceplatform/latest/delete/balanceAccounts/_balanceAccountId_/sweeps/_sweepId_).
                operationId: post-balancePlatform.balanceAccountSweep.deleted
                x-sortIndex: 5
                x-methodName: sweepDeleted
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-deleted:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.deleted-balancePlatform-sweep-deleted
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-deleted:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.updated:
              post:
                tags:
                  - Balance account
                summary: Sweep updated
                description: >-
                  Adyen sends this webhook when you successfully [update a
                  sweep](https://docs.adyen.com/api-explorer/balanceplatform/latest/patch/balanceAccounts/_balanceAccountId_/sweeps/_sweepId_).
                operationId: post-balancePlatform.balanceAccountSweep.updated
                x-sortIndex: 4
                x-methodName: sweepUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.updated-balancePlatform-sweep-updated
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.cardorder.created:
              post:
                tags:
                  - Card order
                summary: Card order created
                description: >-
                  Adyen sends this webhook to indicate a successful creation of
                  a card order after you create a [payment
                  instrument](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/paymentInstruments)
                  of `type` **card** and `formFactor` **physical**.
                operationId: post-balancePlatform.cardorder.created
                x-sortIndex: 1
                x-methodName: cardOrderCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      schema:
                        $ref: '#/components/schemas/CardOrderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.cardorder.updated:
              post:
                tags:
                  - Card order
                summary: Card order updated
                description: >-
                  Adyen sends this webhook when there is an update in card order
                  status.
                operationId: post-balancePlatform.cardorder.updated
                x-sortIndex: 2
                x-methodName: cardOrderUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      schema:
                        $ref: '#/components/schemas/CardOrderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.paymentInstrument.created:
              post:
                tags:
                  - Payment instrument
                summary: Payment instrument created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  payment
                  instrument](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/paymentInstruments). 

                  >The webhook does not include the card number when creating
                  virtual cards. You can only get the card number in the
                  response of the POST
                  [/paymentInstruments](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/paymentInstruments#responses-200-card-number)
                  request.
                operationId: post-balancePlatform.paymentInstrument.created
                x-sortIndex: 1
                x-methodName: paymentInstrumentCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-paymentInstrument-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.paymentInstrument.created-balancePlatform-paymentInstrument-created
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-paymentInstrument-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.paymentInstrument.updated:
              post:
                tags:
                  - Payment instrument
                summary: Payment instrument updated
                description: >-
                  Adyen sends this webhook when you successfully [update a
                  payment
                  instrument](https://docs.adyen.com/api-explorer/balanceplatform/latest/patch/paymentInstruments/_id_). 
                operationId: post-balancePlatform.paymentInstrument.updated
                x-sortIndex: 2
                x-methodName: paymentInstrumentUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-paymentInstrument-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.paymentInstrument.updated-balancePlatform-paymentInstrument-updated
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-paymentInstrument-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/configuration-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/configuration-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-configuration-webhooks-api
  - name: Adyen Data Protection API
    description: >-
      Adyen Data Protection API provides a way for you to process [Subject
      Erasure Requests](https://gdpr-info.eu/art-17-gdpr/) as mandated in GDPR.
      Use our API to submit a request to delete shopper''s data, including
      payment details and other related information (for example, delivery
      address or shopper email).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://gdpr-info.eu/art-17-gdpr/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://gdpr-info.eu/art-17-gdpr/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Data Protection API
          tags:
            - name: General
          paths:
            /requestSubjectErasure:
              post:
                tags:
                  - Submit
                  - Subjects
                  - Erasure
                  - Request.
                  - Subjects
                  - Erasure
                summary: Submit a Subject Erasure Request.
                description: Sends the PSP reference containing t
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-error
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/data-protection-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/data-protection-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-data-protection-api
  - name: Adyen Disputes API
    description: >-
      You can use the Disputes API to automate the dispute handling process so
      that you can respond to disputes and chargebacks as soon as they are
      initiated. The Disputes API lets you retrieve defense reasons, supply and
      delete defense documents, and accept or defend disputes.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/risk-management/disputes-api
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/risk-management/disputes-api
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Disputes API
          tags:
            - name: General
          paths:
            /acceptDispute:
              post:
                tags:
                  - Accept
                  - Disputes
                  - Disputes
                summary: Accept a dispute
                description: Accepts a specific dispute.
            /defendDispute:
              post:
                tags:
                  - Defend
                  - Disputes
                  - Disputes
                summary: Defend a dispute
                description: Defends a specific dispute.
            /deleteDisputeDefenseDocument:
              post:
                tags:
                  - Delete
                  - Defense
                  - Document
                  - Disputes
                  - Defense
                  - Document
                summary: Delete a defense document
                description: >-
                  Deletes a specific dispute defense document that was supplied
                  earlier.
            /retrieveApplicableDefenseReasons:
              post:
                tags:
                  - Get
                  - Applicable
                  - Defense
                  - Reasons
                  - Disputes
                  - Defense
                  - Document
                  - Applicable
                  - Reasons
                summary: Get applicable defense reasons
                description: >-
                  Returns a list of all applicable defense reasons to defend a
                  specific dispute.
            /supplyDefenseDocument:
              post:
                tags:
                  - Supply
                  - Defense
                  - Document
                  - Disputes
                  - Defense
                  - Document
                  - Applicable
                  - Reasons
                summary: Supply a defense document
                description: Supplies a
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/disputes-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/disputes-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-disputes-api
  - name: Adyen Funds API
    description: >-
      The Fund API provides endpoints for managing the funds in the accounts on
      your platform. These management operations include, for example, the
      transfer of funds from one account to another, the payout of funds to an
      account holder, and the retrieval of balances in an account.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/marketplaces-and-platforms/classic/fund-transfer/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/classic/fund-transfer/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Fund API
            x-timestamp: '2023-05-30T15:27:19Z'
          x-groups:
            - General
            - Migration
          tags:
            - name: General
          paths:
            /accountHolderBalance:
              post:
                tags:
                  - Get
                  - The
                  - Balances
                  - Of
                  - An
                  - Account
                  - Holders
                  - Holders
                  - Balance
                summary: Get the balances of an account holder
                description: >-
                  Returns the account balances of an account holder. An
                  account's balances are organized according by currencies. This
                  mean that an account may have multiple balances: one for each
                  currency.
            /accountHolderTransactionList:
              post:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Transactions
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                summary: Get a list of transactions
                description: >-
                  Returns a list of transactions for an account holder's
                  accounts. You can specify the accounts and transaction
                  statuses to be included on the list. The call returns a
                  maximum of 50 transactions for each account. To retrieve all
                  transactions, you must make another call with the 'page' value
                  incremented. Transactions are listed in chronological order,
                  with the most recent transaction first.
            /debitAccountHolder:
              post:
                tags:
                  - Send
                  - Direct
                  - Debit
                  - Request
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                summary: Send a direct debit request
                description: >-
                  Sends a direct debit request to an account holder's bank
                  account. If the direct debit is successful, the funds are
                  settled in the accounts specified in the split instructions.
                  Adyen sends the result of the direct debit in a
                  [`DIRECT_DEBIT_INITIATED`](https://docs.adyen.com/api-explorer/#/NotificationService/latest/post/DIRECT_DEBIT_INITIATED)
                  notification webhook.

                   To learn more about direct debits, see [Top up accounts](https://docs.adyen.com/marketplaces-and-platforms/classic/top-up-accounts).
            /payoutAccountHolder:
              post:
                tags:
                  - Pay
                  - Out
                  - From
                  - An
                  - Account
                  - To
                  - The
                  - Holders
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                summary: Pay out from an account to the account holder
                description: >-
                  Pays out a specified amount from an account to the bank
                  account of account holder.
            /refundFundsTransfer:
              post:
                tags:
                  - Refunds
                  - Funds
                  - Transfers
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                  - Funds
                  - Transfers
                summary: Refund a funds transfer
                description: >-
                  Refunds funds transferred from one account to another. Both
                  accounts must be in the same platform, but can have different
                  account holders. 
            /refundNotPaidOutTransfers:
              post:
                tags:
                  - Refunds
                  - All
                  - Transactions
                  - Of
                  - An
                  - Account
                  - Since
                  - The
                  - Most
                  - Recent
                  - Payouts
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                  - Funds
                  - Transfers
                  - Not
                  - Paid
                  - Out
                  - Transfers
                summary: >-
                  Refund all transactions of an account since the most recent
                  payout
                description: >-
                  Refunds all the transactions of an account that have taken
                  place since the most recent payout. This request is on a
                  account basis (as opposed to a payment basis), so only the
                  portion of the payment that was made to the specified account
                  is refunded. The commissions, fees, and payments to other
                  accounts remain in the accounts to which they were sent as
                  designated by the original payment's split details.
            /setupBeneficiary:
              post:
                tags:
                  - Designate
                  - Beneficiary
                  - Account
                  - And
                  - Transfers
                  - The
                  - Benefactor's
                  - Current
                  - Balance
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                  - Funds
                  - Transfers
                  - Not
                  - Paid
                  - Out
                  - Transfers
                  - Beneficiary
                summary: >-
                  Designate a beneficiary account and transfer the benefactor's
                  current balance
                description: >-
                  Defines a benefactor and a beneficiary relationship between
                  two accounts. At the time of benefactor/beneficiary setup, the
                  funds in the benefactor account are transferred to the
                  beneficiary account, and any further payments to the
                  benefactor account are automatically sent to the beneficiary
                  account. A series of benefactor/beneficiaries may not exceed
                  four beneficiaries and may not have a cycle in it.
            /transferFunds:
              post:
                tags:
                  - Transfers
                  - Funds
                  - Between
                  - Platforms
                  - Accounts
                  - Holders
                  - Balance
                  - Transactions
                  - Lists
                  - Account
                  - Funds
                  - Transfers
                  - Not
                  - Paid
                  - Out
                  - Transfers
                  - Beneficiary
                summary: Transfer funds between platform accounts
                description: >-
                  Transfers funds from one account to another account. Both
                  accounts must be in the same platform, but can have different
                  account holders. The transfer must include a transfer code,
                  which should be determined by the platform, in 
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-operations-summary-length-error
              message: Operation Summary Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/funds-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/funds-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-funds-api
  - name: Adyen Hosted Onboarding API
    description: >-
      The Fund API provides endpoints for managing the funds in the accounts on
      your platform. These management operations include, for example, the
      transfer of funds from one account to another, the payout of funds to an
      account holder, and the retrieval of balances in an account.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/collect-verification-details/hosted/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/collect-verification-details/hosted/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Hosted Onboarding API
            x-timestamp: '2023-05-30T15:27:20Z'
          x-groups:
            - Hosted Onboarding Page
            - PCI Compliance Questionnaire Page
          tags:
            - name: Hosted Onboarding Page
            - name: PCI Compliance Questionnaire Page
          paths:
            /getOnboardingUrl:
              post:
                tags:
                  - Get
                  - Link
                  - To
                  - Adyen-hosted
                  - Onboarding
                  - Page
                  - Onboarding
                  - URL
                summary: Get a link to a Adyen-hosted onboarding page
                description: >-
                  Returns a link to an Adyen-hosted onboarding page (HOP) that
                  you can send to your account holder. For more information on
                  how to use HOP, refer to [Hosted
                  onboarding](https://docs.adyen.com/marketplaces-and-platforms/classic/collect-verification-details/hosted-onboarding-page). 
            /getPciQuestionnaireUrl:
              post:
                tags:
                  - Get
                  - Link
                  - To
                  - Compliance
                  - Questionnaires
                  - Onboarding
                  - URL
                  - PCI
                  - Questionnaires
                summary: Get a link to a PCI compliance questionnaire
                description: >-
                  Returns a link to a PCI compliance questionnaire that you can
                  send to your account holder.
                   > You should only use this endpoint if you have a [partner platform setup](https://docs.adyen.com/marketplaces-and-platform
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/hosted-onboarding-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/hosted-onboarding-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-hosted-onboarding-api
  - name: Adyen Legal Entity API
    description: >-
      The Legal Entity Management API enables you to manage legal entities that
      contain information required for verification.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/legal-entity-management-api/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/legal-entity-management-api/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Legal Entity Management API
          tags:
            - name: Legal entities
            - name: Transfer instruments
            - name: Business lines
            - name: Documents
            - name: Terms of Service
            - name: Hosted Onboarding
            - name: Questionnaires
          paths:
            /businessLines:
              post:
                tags:
                  - Create
                  - Business
                  - Line
                  - Lines
                summary: Create a business line
                description: >+
                  Creates a business line. 


                  This resource contains information about your user's line of
                  business, including their industry and their source of funds.
                  Adyen uses this information to verify your users as required
                  by payment industry regulations. Adyen informs you of the
                  verification results through webhooks or API responses.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /businessLines/{id}:
              delete:
                tags:
                  - Delete
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Delete a business line
                description: |-
                  Deletes a business line.

                   >If you delete a business line linked to a [payment method](https://docs.adyen.com/development-resources/paymentmethodvariant#management-api), it can affect your merchant account's ability to use the [payment method](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/_merchantId_/paymentMethodSettings). The business line is removed from all linked merchant accounts.
              get:
                tags:
                  - Get
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Get a business line
                description: Returns the detail of a business line.
              patch:
                tags:
                  - Update
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Update a business line
                description: Updates a business line.
            /documents:
              post:
                tags:
                  - Uploads
                  - Document
                  - For
                  - Verification
                  - Checks
                  - Lines
                  - Identifiers
                  - Documents
                summary: Upload a document for verification checks
                description: |-
                  Uploads a document for verification checks.

                   Adyen uses the information from the [legal entity](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities) to run automated verification checks. If these checks fail, you will be notified to provide additional documents.

                   You should only upload documents when Adyen requests additional information for the legal entity.

                   >You can upload a maximum of 15 pages for photo IDs.
            /documents/{id}:
              delete:
                tags:
                  - Delete
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Delete a document
                description: Deletes a document.
              get:
                tags:
                  - Get
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Get a document
                description: Returns a document.
              patch:
                tags:
                  - Update
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Update a document
                description: |-
                  Updates a document.

                   >You can upload a maximum of 15 pages for photo IDs.
            /legalEntities:
              post:
                tags:
                  - Create
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Create a legal entity
                description: >+
                  Creates a legal entity. 


                  This resource contains information about the user that will be
                  onboarded in your platform. Adyen uses this information to
                  perform verification checks as required by payment industry
                  regulations. Adyen informs you of the verification results
                  through webhooks or API responses. 


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /legalEntities/{id}:
              get:
                tags:
                  - Get
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Get a legal entity
                description: Returns a legal entity.
              patch:
                tags:
                  - Update
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Update a legal entity
                description: |-
                  Updates a legal entity.

                   >To change the legal entity type, include only the new `type` in your request. To update the `entityAssociations` array, you need to replace the entire array. For example, if the array has 3 entries and you want to remove 1 entry, you need to PATCH the resource with the remaining 2 entries.
            /legalEntities/{id}/businessLines:
              get:
                tags:
                  - Get
                  - All
                  - Business
                  - Lines
                  - Under
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                summary: Get all business lines under a legal entity
                description: Returns the business lines owned by a legal entity.
            /legalEntities/{id}/checkVerificationErrors:
              post:
                tags:
                  - Checks
                  - Legal
                  - Entities
                  - Verification
                  - Errors
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                summary: Check a legal entity's verification errors
                description: >-
                  Returns the verification errors for a legal entity and its
                  supporting entities.
            /legalEntities/{id}/confirmDataReview:
              post:
                tags:
                  - Confirm
                  - Data
                  - Reviews
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                summary: Confirm data review
                description: >-
                  Confirms that your user has reviewed the data for the legal
                  entity specified in the path. Call this endpoint to inform
                  Adyen that your user reviewed and verified that the data is
                  up-to-date. The endpoint returns the timestamp of when Adyen
                  received the request.
            /legalEntities/{id}/onboardingLinks:
              post:
                tags:
                  - Get
                  - Link
                  - To
                  - An
                  - Adyen-hosted
                  - Onboarding
                  - Page
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                summary: Get a link to an Adyen-hosted onboarding page
                description: >+
                  Returns a link to an Adyen-hosted onboarding page where you
                  need to redirect your user.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /legalEntities/{id}/pciQuestionnaires:
              get:
                tags:
                  - Get
                  - Questionnaires
                  - Details
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                summary: Get PCI questionnaire details
                description: Get a list of signed PCI questionnaires.
            /legalEntities/{id}/pciQuestionnaires/generatePciTemplates:
              post:
                tags:
                  - Generate
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                summary: Generate PCI questionnaire
                description: >-
                  Generates the required PCI questionnaires based on the user's
                  [salesChannel](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/businessLines__reqParam_salesChannels).
            /legalEntities/{id}/pciQuestionnaires/signPciTemplates:
              post:
                tags:
                  - Sign
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                summary: Sign PCI questionnaire
                description: Signs the required PCI questionnaire.
            /legalEntities/{id}/pciQuestionnaires/{pciid}:
              get:
                tags:
                  - Get
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                summary: Get PCI questionnaire
                description: Returns the signed PCI questionnaire.
            /legalEntities/{id}/termsOfService:
              post:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                summary: Get Terms of Service document
                description: Returns the Terms of Service document for a legal entity.
            /legalEntities/{id}/termsOfService/{termsofservicedocumentid}:
              patch:
                tags:
                  - Accept
                  - Terms
                  - Of
                  - Services
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                summary: Accept Terms of Service
                description: Accepts Terms of Service.
            /legalEntities/{id}/termsOfServiceAcceptanceInfos:
              get:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Information
                  - For
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                summary: Get Terms of Service information for a legal entity
                description: Returns Terms of Service information for a legal entity.
            /legalEntities/{id}/termsOfServiceStatus:
              get:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Status
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                summary: Get Terms of Service status
                description: >-
                  Returns the required types of Terms of Service that need to be
                  accepted by a legal entity.
            /themes:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Hosted
                  - Onboarding
                  - Page
                  - Themes
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                summary: Get a list of hosted onboarding page themes
                description: >+
                  Returns a list of hosted onboarding page themes.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /themes/{id}:
              get:
                tags:
                  - Get
                  - An
                  - Onboarding
                  - Link
                  - Theme
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                summary: Get an onboarding link theme
                description: >+
                  Returns the details of the theme identified in the path.>If
                  you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /transferInstruments:
              post:
                tags:
                  - Create
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Create a transfer instrument
                description: >-
                  Creates a transfer instrument. 


                  A transfer instrument is a bank account that a legal entity
                  owns. Adyen performs verification checks on the transfer
                  instrument as required by payment industry regulations. We
                  inform you of the verification results through webhooks or API
                  responses.


                  When the transfer instrument passes the verification checks,
                  you can start sending funds from the balance platform to the
                  transfer instrument (such as payouts).
            /transferInstruments/{id}:
              delete:
                tags:
                  - Delete
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Delete a transfer instrument
                description: Deletes a transfer instrument.
              get:
                tags:
                  - Get
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Get a transfer instrument
                description: Returns the details of a transfer instrument.
              patch:
                tags:
                  - Update
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Update a transfer instrument
                description: null
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-no-request-body-on-delete-info
              message: DELETE Request Body
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-204-status-code-info
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-info
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-info
              message: 500 Status Code for DELETE Responses
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-request-body-on-post-error
              message: Request Body POST
            - code: openapi-operations-summary-length-error
              message: Operation Summary Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/legal-entity-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/legal-entity-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-legal-entity-api
  - name: Adyen Legal Entity API
    description: >-
      The Legal Entity Management API enables you to manage legal entities that
      contain information required for verification.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/legal-entity-management-api/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/legal-entity-management-api/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Legal Entity Management API
          tags:
            - name: Legal entities
            - name: Transfer instruments
            - name: Business lines
            - name: Documents
            - name: Terms of Service
            - name: Hosted Onboarding
            - name: Questionnaires
          paths:
            /businessLines:
              post:
                tags:
                  - Create
                  - Business
                  - Line
                  - Lines
                summary: Create a business line
                description: >+
                  Creates a business line. 


                  This resource contains information about your user's line of
                  business, including their industry and their source of funds.
                  Adyen uses this information to verify your users as required
                  by payment industry regulations. Adyen informs you of the
                  verification results through webhooks or API responses.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /businessLines/{id}:
              delete:
                tags:
                  - Delete
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Delete a business line
                description: |-
                  Deletes a business line.

                   >If you delete a business line linked to a [payment method](https://docs.adyen.com/development-resources/paymentmethodvariant#management-api), it can affect your merchant account's ability to use the [payment method](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/_merchantId_/paymentMethodSettings). The business line is removed from all linked merchant accounts.
              get:
                tags:
                  - Get
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Get a business line
                description: Returns the detail of a business line.
              patch:
                tags:
                  - Update
                  - Business
                  - Line
                  - Lines
                  - Identifiers
                summary: Update a business line
                description: Updates a business line.
            /documents:
              post:
                tags:
                  - Uploads
                  - Document
                  - For
                  - Verification
                  - Checks
                  - Lines
                  - Identifiers
                  - Documents
                summary: Upload a document for verification checks
                description: |-
                  Uploads a document for verification checks.

                   Adyen uses the information from the [legal entity](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities) to run automated verification checks. If these checks fail, you will be notified to provide additional documents.

                   You should only upload documents when Adyen requests additional information for the legal entity.

                   >You can upload a maximum of 15 pages for photo IDs.
            /documents/{id}:
              delete:
                tags:
                  - Delete
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Delete a document
                description: Deletes a document.
              get:
                tags:
                  - Get
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Get a document
                description: Returns a document.
              patch:
                tags:
                  - Update
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                summary: Update a document
                description: |-
                  Updates a document.

                   >You can upload a maximum of 15 pages for photo IDs.
            /legalEntities:
              post:
                tags:
                  - Create
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Create a legal entity
                description: >+
                  Creates a legal entity. 


                  This resource contains information about the user that will be
                  onboarded in your platform. Adyen uses this information to
                  perform verification checks as required by payment industry
                  regulations. Adyen informs you of the verification results
                  through webhooks or API responses. 


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /legalEntities/{id}:
              get:
                tags:
                  - Get
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Get a legal entity
                description: Returns a legal entity.
              patch:
                tags:
                  - Update
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                summary: Update a legal entity
                description: |-
                  Updates a legal entity.

                   >To change the legal entity type, include only the new `type` in your request. To update the `entityAssociations` array, you need to replace the entire array. For example, if the array has 3 entries and you want to remove 1 entry, you need to PATCH the resource with the remaining 2 entries.
            /legalEntities/{id}/businessLines:
              get:
                tags:
                  - Get
                  - All
                  - Business
                  - Lines
                  - Under
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                summary: Get all business lines under a legal entity
                description: Returns the business lines owned by a legal entity.
            /legalEntities/{id}/checkVerificationErrors:
              post:
                tags:
                  - Checks
                  - Legal
                  - Entities
                  - Verification
                  - Errors
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                summary: Check a legal entity's verification errors
                description: >-
                  Returns the verification errors for a legal entity and its
                  supporting entities.
            /legalEntities/{id}/confirmDataReview:
              post:
                tags:
                  - Confirm
                  - Data
                  - Reviews
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                summary: Confirm data review
                description: >-
                  Confirms that your user has reviewed the data for the legal
                  entity specified in the path. Call this endpoint to inform
                  Adyen that your user reviewed and verified that the data is
                  up-to-date. The endpoint returns the timestamp of when Adyen
                  received the request.
            /legalEntities/{id}/onboardingLinks:
              post:
                tags:
                  - Get
                  - Link
                  - To
                  - An
                  - Adyen-hosted
                  - Onboarding
                  - Page
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                summary: Get a link to an Adyen-hosted onboarding page
                description: >+
                  Returns a link to an Adyen-hosted onboarding page where you
                  need to redirect your user.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /legalEntities/{id}/pciQuestionnaires:
              get:
                tags:
                  - Get
                  - Questionnaires
                  - Details
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                summary: Get PCI questionnaire details
                description: Get a list of signed PCI questionnaires.
            /legalEntities/{id}/pciQuestionnaires/generatePciTemplates:
              post:
                tags:
                  - Generate
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                summary: Generate PCI questionnaire
                description: >-
                  Generates the required PCI questionnaires based on the user's
                  [salesChannel](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/businessLines__reqParam_salesChannels).
            /legalEntities/{id}/pciQuestionnaires/signPciTemplates:
              post:
                tags:
                  - Sign
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                summary: Sign PCI questionnaire
                description: Signs the required PCI questionnaire.
            /legalEntities/{id}/pciQuestionnaires/{pciid}:
              get:
                tags:
                  - Get
                  - Questionnaires
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                summary: Get PCI questionnaire
                description: Returns the signed PCI questionnaire.
            /legalEntities/{id}/termsOfService:
              post:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Document
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                summary: Get Terms of Service document
                description: Returns the Terms of Service document for a legal entity.
            /legalEntities/{id}/termsOfService/{termsofservicedocumentid}:
              patch:
                tags:
                  - Accept
                  - Terms
                  - Of
                  - Services
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                summary: Accept Terms of Service
                description: Accepts Terms of Service.
            /legalEntities/{id}/termsOfServiceAcceptanceInfos:
              get:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Information
                  - For
                  - Legal
                  - Entities
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                summary: Get Terms of Service information for a legal entity
                description: Returns Terms of Service information for a legal entity.
            /legalEntities/{id}/termsOfServiceStatus:
              get:
                tags:
                  - Get
                  - Terms
                  - Of
                  - Services
                  - Status
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                summary: Get Terms of Service status
                description: >-
                  Returns the required types of Terms of Service that need to be
                  accepted by a legal entity.
            /themes:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Hosted
                  - Onboarding
                  - Page
                  - Themes
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                summary: Get a list of hosted onboarding page themes
                description: >+
                  Returns a list of hosted onboarding page themes.


                  >If you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /themes/{id}:
              get:
                tags:
                  - Get
                  - An
                  - Onboarding
                  - Link
                  - Theme
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                summary: Get an onboarding link theme
                description: >+
                  Returns the details of the theme identified in the path.>If
                  you are using hosted onboarding and just beginning your
                  integration, use v3 for your API requests. Otherwise, use v2.

            /transferInstruments:
              post:
                tags:
                  - Create
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Create a transfer instrument
                description: >-
                  Creates a transfer instrument. 


                  A transfer instrument is a bank account that a legal entity
                  owns. Adyen performs verification checks on the transfer
                  instrument as required by payment industry regulations. We
                  inform you of the verification results through webhooks or API
                  responses.


                  When the transfer instrument passes the verification checks,
                  you can start sending funds from the balance platform to the
                  transfer instrument (such as payouts).
            /transferInstruments/{id}:
              delete:
                tags:
                  - Delete
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Delete a transfer instrument
                description: Deletes a transfer instrument.
              get:
                tags:
                  - Get
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Get a transfer instrument
                description: Returns the details of a transfer instrument.
              patch:
                tags:
                  - Update
                  - Transfers
                  - Instruments
                  - Lines
                  - Identifiers
                  - Documents
                  - Entities
                  - Business
                  - Checks
                  - Verification
                  - Errors
                  - Confirm
                  - Data
                  - Reviews
                  - Onboarding
                  - Links
                  - PCI
                  - Questionnaires
                  - Generate
                  - Templates
                  - Sign
                  - Pciid
                  - Terms
                  - Of
                  - Services
                  - Terms Of Service Documents
                  - Acceptance
                  - Information
                  - Status
                  - Themes
                  - Instruments
                summary: Update a transfer instrument
                description: null
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-no-request-body-on-delete-info
              message: DELETE Request Body
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-204-status-code-info
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-info
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-info
              message: 500 Status Code for DELETE Responses
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-request-body-on-post-error
              message: Request Body POST
            - code: openapi-operations-summary-length-error
              message: Operation Summary Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/legal-entity-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/legal-entity-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-legal-entity-api
  - name: Adyen Management API
    description: >-
      Configure and manage your Adyen company and merchant accounts, stores, and
      payment terminals.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/Management/3/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/Management/3/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Management API
          tags:
            - name: Account - company level
            - name: Account - merchant level
            - name: Account - store level
            - name: Payout settings - merchant level
            - name: Users - company level
            - name: Users - merchant level
            - name: My API credential
            - name: API credentials - company level
            - name: API credentials - merchant level
            - name: API key - company level
            - name: API key - merchant level
            - name: Client key - company level
            - name: Client key - merchant level
            - name: Allowed origins - company level
            - name: Allowed origins - merchant level
            - name: Webhooks - company level
            - name: Webhooks - merchant level
            - name: Payment methods - merchant level
            - name: Terminals - terminal level
            - name: Terminal actions - company level
            - name: Terminal actions - terminal level
            - name: Terminal orders - company level
            - name: Terminal orders - merchant level
            - name: Terminal settings - company level
            - name: Terminal settings - merchant level
            - name: Terminal settings - store level
            - name: Terminal settings - terminal level
            - name: Android files - company level
            - name: Split configuration - merchant level
          paths:
            /companies:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Companies
                  - Accounts
                  - Companies
                summary: Get a list of company accounts
                description: >-
                  Returns the list of company accounts that your API credential
                  has access to. The list is grouped into pages as defined by
                  the query parameters.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):


                  * Management API—Account read
            /companies/{companyId}:
              get:
                tags:
                  - Get
                  - Companies
                  - Account
                  - Companies
                  - Identifiers
                summary: Get a company account
                description: >-
                  Returns the company account specified in the path. Your API
                  credential must have access to the company account. 


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Account read
            /companies/{companyId}/androidApps:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Android
                  - Applications
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                summary: Get a list of Android apps
                description: >-
                  Returns a list of the Android apps that are available for the
                  company identified in the path. 

                  These apps have been uploaded to Adyen and can be installed or
                  uninstalled on Android payment terminals through [terminal
                  actions](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Android files read

                  * Management API—Android files read and write

                  * Management API—Terminal actions read

                  * Management API—Terminal actions read and write
              post:
                tags:
                  - Uploads
                  - Android
                  - Applications
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                summary: Upload Android App
                description: >-
                  Uploads an Android APK file to Adyen.

                  The maximum APK file size is 200 MB.

                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Android files read and write


                  >By choosing to upload, install, or run any third-party
                  applications on an Adyen payment terminal, you accept full
                  responsibility and liability for any consequences of
                  uploading, installing, or running any such applications.
            /companies/{companyId}/androidApps/{id}:
              get:
                tags:
                  - Get
                  - Android
                  - Applications
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                summary: Get Android app
                description: >-
                  Returns the details of the Android app identified in the
                  path. 

                  These apps have been uploaded to Adyen and can be installed or
                  uninstalled on Android payment terminals through [terminal
                  actions](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Android files read

                  * Management API—Android files read and write
            /companies/{companyId}/androidCertificates:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Android
                  - Certificates
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                summary: Get a list of Android certificates
                description: >-
                  Returns a list of the Android certificates that are available
                  for the company identified in the path.

                  Typically, these certificates enable running apps on Android
                  payment terminals. The certifcates in the list have been
                  uploaded to Adyen and can be installed or uninstalled on
                  Android terminals through [terminal
                  actions](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Android files read

                  * Management API—Android files read and write

                  * Management API—Terminal actions read

                  * Management API—Terminal actions read and write
            /companies/{companyId}/apiCredentials:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                summary: Get a list of API credentials
                description: >-
                  Returns the list of [API
                  credentials](https://docs.adyen.com/development-resources/api-credentials)
                  for the company account. The list is grouped into pages as
                  defined by the query parameters.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              post:
                tags:
                  - Create
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                summary: Create an API credential.
                description: >-
                  Creates an [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  for the company account identified in the path. In the
                  request, you can specify which merchant accounts the new API
                  credential will have access to, as well as its roles and
                  allowed origins.


                  The response includes several types of authentication details:

                  * [API
                  key](https://docs.adyen.com/development-resources/api-authentication#api-key-authentication):
                  used for API request authentication.

                  * [Client
                  key](https://docs.adyen.com/development-resources/client-side-authentication#how-it-works):
                  public key used for client-side authentication.

                  * [Username and
                  password](https://docs.adyen.com/development-resources/api-authentication#using-basic-authentication):
                  used for basic authentication.


                  > Make sure you store the API key securely in your system. You
                  won't be able to retrieve it later.


                  If your API key is lost or compromised, you need to [generate
                  a new API
                  key](https://docs.adyen.com/api-explorer/#/ManagementService/v1/post/companies/{companyId}/apiCredentials/{apiCredentialId}/generateApiKey).


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/apiCredentials/{apiCredentialId}:
              get:
                tags:
                  - Get
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                summary: Get an API credential
                description: >-
                  Returns the [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              patch:
                tags:
                  - Update
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                summary: Update an API credential.
                description: >-
                  Changes the API credential's roles, merchant account access,
                  or allowed origins. The request has the new values for the
                  fields you want to change. The response contains the full
                  updated API credential, including the new values from the
                  request. 


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/apiCredentials/{apiCredentialId}/allowedOrigins:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Allowed
                  - Origins
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                summary: Get a list of allowed origins
                description: >-
                  Returns the list of [allowed
                  origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  for the API credential identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              post:
                tags:
                  - Create
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                summary: Create an allowed origin
                description: >-
                  Adds a new [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  to the API credential's list of allowed origins.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/apiCredentials/{apiCredentialId}/allowedOrigins/{originId}:
              delete:
                tags:
                  - Delete
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                summary: Delete an allowed origin
                description: >-
                  Removes the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  identified in the path. As soon as an allowed origin is
                  removed, we no longer accept client-side requests from that
                  domain.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              get:
                tags:
                  - Get
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                summary: Get an allowed origin
                description: >-
                  Returns the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/apiCredentials/{apiCredentialId}/generateApiKey:
              post:
                tags:
                  - Generate
                  - New
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                summary: Generate new API key
                description: >-
                  Returns a new API key for the API credential. You can use the
                  new API key a few minutes after generating it. The old API key
                  stops working 24 hours after generating a new one.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/apiCredentials/{apiCredentialId}/generateClientKey:
              post:
                tags:
                  - Generate
                  - New
                  - Client
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                summary: Generate new client key
                description: >-
                  Returns a new [client
                  key](https://docs.adyen.com/development-resources/client-side-authentication#how-it-works)
                  for the API credential identified in the path. You can use the
                  new client key a few minutes after generating it. The old
                  client key stops working 24 hours after generating a new one.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /companies/{companyId}/billingEntities:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Billing
                  - Entities
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                summary: Get a list of billing entities
                description: >-
                  Returns the billing entities of the company identified in the
                  path and all merchant accounts belonging to the company.

                  A billing entity is a legal entity where we charge orders to.
                  An order for terminal products must contain the ID of a
                  billing entity.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/merchants:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Merchants
                  - Accounts
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                summary: Get a list of merchant accounts
                description: >-
                  Returns the list of merchant accounts under the company
                  account specified in the path. The list only includes merchant
                  accounts that your API credential has access to. The list is
                  grouped into pages as defined by the query parameters. 


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Account read
            /companies/{companyId}/shippingLocations:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Shipping
                  - Locations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                summary: Get a list of shipping locations
                description: >-
                  Returns the shipping locations for the company identified in
                  the path and all merchant accounts belonging to the company.

                  A shipping location includes the address where orders can be
                  delivered, and an ID which you need to specify when ordering
                  terminal products.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              post:
                tags:
                  - Create
                  - Shipping
                  - Locations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                summary: Create a shipping location
                description: >-
                  Creates a shipping location for the company identified in the
                  path. A shipping location defines an address where orders can
                  be delivered.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/terminalActions:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminal
                  - Actions
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                summary: Get a list of terminal actions
                description: >-
                  Returns the [terminal
                  actions](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api)
                  that have been scheduled for the company identified in the
                  path.The response doesn't include actions that are scheduled
                  by Adyen.

                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal actions read

                  * Management API—Terminal actions read and write
            /companies/{companyId}/terminalActions/{actionId}:
              get:
                tags:
                  - Get
                  - Terminal
                  - Actions
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                summary: Get terminal action
                description: >-
                  Returns the details of the [terminal
                  action](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api)
                  identified in the path.

                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal actions read

                  * Management API—Terminal actions read and write
            /companies/{companyId}/terminalLogos:
              get:
                tags:
                  - Get
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                summary: Get the terminal logo
                description: >-
                  Returns the logo that is configured for a specific payment
                  terminal model at the company identified in the path. 


                  The logo is returned as a Base64-encoded string. You need to
                  Base64-decode the string to get the actual image file. 

                  This logo applies to all terminals of the specified model
                  under the company, unless a different logo is configured at a
                  lower level (merchant account, store, or individual terminal).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                summary: Update the terminal logo
                description: >-
                  Updates the logo that is configured for a specific payment
                  terminal model at the company identified in the path. You can
                  update the logo for only one terminal model at a time.

                  This logo applies to all terminals of the specified model
                  under the company, unless a different logo is configured at a
                  lower level (merchant account, store, or individual
                  terminal). 

                  * To change the logo, specify the image file as a
                  Base64-encoded string.

                  * To restore the logo inherited from the Adyen PSP level,
                  specify an empty logo value.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /companies/{companyId}/terminalModels:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminal
                  - Models
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                summary: Get a list of terminal models
                description: >-
                  Returns a list of payment terminal models that the company
                  identified in the path has access to.

                  The response includes the terminal model ID, which can be used
                  as a query parameter when getting a list of terminals or a
                  list of products for ordering.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/terminalOrders:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                summary: Get a list of orders
                description: >-
                  Returns a lists of terminal products orders for the company
                  identified in the path.

                  To filter the list, use one or more of the query parameters.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              post:
                tags:
                  - Create
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                summary: Create an order
                description: >-
                  Creates an order for payment terminal products for the company
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write

                  >Requests to the Management API test endpoint do not create
                  actual orders for test terminals. To order test terminals, you
                  need to [submit a sales
                  order](https://docs.adyen.com/point-of-sale/managing-terminals/order-terminals/#sales-order-steps)
                  in your Customer Area.
            /companies/{companyId}/terminalOrders/{orderId}:
              get:
                tags:
                  - Get
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                summary: Get an order
                description: >-
                  Returns the details of the terminal products order identified
                  in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              patch:
                tags:
                  - Update
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                summary: Update an order
                description: >-
                  Updates the terminal products order identified in the path.

                  Updating is only possible while the order has the status
                  **Placed**.


                  The request body only needs to contain what you want to
                  change. 

                  However, to update the products in the `items` array, you must
                  provide the entire array. For example, if the array has three
                  items:
                   To remove one item, the array must include the remaining two items. Or to add one item, the array must include all four items.

                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/terminalOrders/{orderId}/cancel:
              post:
                tags:
                  - Cancel
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                summary: Cancel an order
                description: >-
                  Cancels the terminal products order identified in the path.

                  Cancelling is only possible while the order has the status
                  **Placed**.

                  To cancel an order, make a POST call without a request body.
                  The response returns the full order details, but with the
                  status changed to **Cancelled**.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/terminalProducts:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminal
                  - Products
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                summary: Get a list of terminal products
                description: >-
                  Returns a country-specific list of payment terminal packages
                  and parts that the company identified in the path has access
                  to.
                   
                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /companies/{companyId}/terminalSettings:
              get:
                tags:
                  - Get
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                summary: Get terminal settings
                description: >-
                  Returns the payment terminal settings that are configured for
                  the company identified in the path. These settings apply to
                  all terminals under the company, unless different values are
                  configured at a lower level (merchant account, store, or
                  individual terminal).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
              patch:
                tags:
                  - Update
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                summary: Update terminal settings
                description: >-
                  Updates payment terminal settings for the company identified
                  in the path. These settings apply to all terminals under the
                  company, unless different values are configured at a lower
                  level (merchant account, store, or individual terminal).


                  * To change a parameter value, include the full object that
                  contains the parameter, even if you don't want to change all
                  parameters in the object.

                  * To restore a parameter value inherited from the Adyen PSP
                  level, include the full object that contains the parameter,
                  and specify an empty value for the parameter or omit the
                  parameter.

                  * Objects that are not included in the request are not
                  updated.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
            /companies/{companyId}/users:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Users
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                summary: Get a list of users
                description: >
                  Returns the list of users for the `companyId` identified in
                  the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
              post:
                tags:
                  - Create
                  - New
                  - Users
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                summary: Create a new user
                description: >
                  Creates the user for the `companyId` identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
            /companies/{companyId}/users/{userId}:
              get:
                tags:
                  - Get
                  - Users
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                summary: Get user details
                description: >
                  Returns user details for the `userId` and the `companyId`
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
              patch:
                tags:
                  - Update
                  - Users
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                summary: Update user details
                description: >
                  Updates user details for the `userId` and the `companyId`
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
            /companies/{companyId}/webhooks:
              get:
                tags:
                  - Lists
                  - All
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                summary: List all webhooks
                description: >-
                  Lists all webhook configurations for the company account.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read

                  * Management API—Webhooks read and write
              post:
                tags:
                  - Sets
                  - Up
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                summary: Set up a webhook
                description: >-
                  Subscribe to receive webhook notifications about events
                  related to your company account. You can add basic
                  authentication to make sure the data is secure.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /companies/{companyId}/webhooks/{webhookId}:
              delete:
                tags:
                  - Removes
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                summary: Remove a webhook
                description: >-
                  Remove the configuration for the webhook identified in the
                  path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
              get:
                tags:
                  - Get
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                summary: Get a webhook
                description: >-
                  Returns the configuration for the webhook identified in the
                  path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read

                  * Management API—Webhooks read and write
              patch:
                tags:
                  - Update
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                summary: Update a webhook
                description: >-
                  Make changes to the configuration of the webhook identified in
                  the path. The request contains the new values you want to have
                  in the webhook configuration. The response contains the full
                  configuration for the webhook, which includes the new values
                  from the request.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /companies/{companyId}/webhooks/{webhookId}/generateHmac:
              post:
                tags:
                  - Generate
                  - An
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                summary: Generate an HMAC key
                description: >-
                  Returns an [HMAC key](https://en.wikipedia.org/wiki/HMAC) for
                  the webhook identified in the path. This key allows you to
                  check the integrity and the origin of the notifications you
                  receive.By creating an HMAC key, you start receiving
                  [HMAC-signed
                  notifications](https://docs.adyen.com/development-resources/webhooks/verify-hmac-signatures#enable-hmac-signatures)
                  from Adyen. Find out more about how to [verify HMAC
                  signatures](https://docs.adyen.com/development-resources/webhooks/verify-hmac-signatures).


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /companies/{companyId}/webhooks/{webhookId}/test:
              post:
                tags:
                  - Tests
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                summary: Test a webhook
                description: >-
                  Sends sample notifications to test if the webhook is set up
                  correctly.


                  We send sample notifications for maximum 20 of the merchant
                  accounts that the webhook is configured for. If the webhook is
                  configured for more than 20 merchant accounts, use the
                  `merchantIds` array to specify a subset of the merchant
                  accounts for which to send test notifications.


                  We send four test notifications for each event code you
                  choose. They cover success and failure scenarios for the
                  hard-coded currencies EUR and GBP, regardless of the
                  currencies configured in the merchant accounts. For custom
                  notifications, we only send the specified custom notification.


                  The response describes the result of the test. The `status`
                  field tells you if the test was successful or not. You can use
                  the other response fields to troubleshoot unsuccessful tests.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /me:
              get:
                tags:
                  - Get
                  - Credentials
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Get API credential details
                description: >-
                  Returns your [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  details based on the API Key you used in the request.


                  You can make this request with any of the Management API
                  roles.
            /me/allowedOrigins:
              get:
                tags:
                  - Get
                  - Allowed
                  - Origins
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Get allowed origins
                description: >-
                  Returns the list of [allowed
                  origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  of your [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  based on the API key you used in the request.


                  You can make this request with any of the Management API
                  roles.
              post:
                tags:
                  - Add
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Add allowed origin
                description: >-
                  Adds an allowed origin to the list of [allowed
                  origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  of your API credential.

                  The API key from the request is used to identify the [API
                  credential](https://docs.adyen.com/development-resources/api-credentials).


                  You can make this request with any of the Management API
                  roles.
            /me/allowedOrigins/{originId}:
              delete:
                tags:
                  - Removes
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Remove allowed origin
                description: >-
                  Removes the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  specified in the path.

                  The API key from the request is used to identify the [API
                  credential](https://docs.adyen.com/development-resources/api-credentials).


                  You can make this request with any of the Management API
                  roles.
              get:
                tags:
                  - Get
                  - Allowed
                  - Origin
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Get allowed origin details
                description: >-
                  Returns the details of the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  specified in the path.

                  The API key from the request is used to identify the [API
                  credential](https://docs.adyen.com/development-resources/api-credentials).


                  You can make this request with any of the Management API
                  roles.
            /me/generateClientKey:
              post:
                tags:
                  - Generate
                  - Client
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Generate a client key
                description: >-
                  Generates a new [client
                  key](https://docs.adyen.com/development-resources/client-side-authentication/)
                  used to authenticate requests from your payment environment.

                  You can use the new client key a few minutes after generating
                  it.

                  The old client key stops working 24 hours after generating a
                  new one.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Merchants
                  - Accounts
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Get a list of merchant accounts
                description: >-
                  Returns the list of merchant accounts that your API credential
                  has access to. The list is grouped into pages as defined by
                  the query parameters. 


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Account read
              post:
                tags:
                  - Create
                  - Merchants
                  - Account
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Create a merchant account
                description: >-
                  Creates a merchant account for the company account specified
                  in the request.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Accounts read and write
            /merchants/{merchantId}:
              get:
                tags:
                  - Get
                  - Merchants
                  - Account
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                summary: Get a merchant account
                description: >-
                  Returns the merchant account specified in the path. Your API
                  credential must have access to the merchant account.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Account read
            /merchants/{merchantId}/activate:
              post:
                tags:
                  - Request
                  - To
                  - Activate
                  - Merchants
                  - Account
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Request to activate a merchant account
                description: >-
                  Sends a request to activate the merchant account identified in
                  the path.


                  You get the result of the activation asynchronously through a
                  [`merchant.updated`](https://docs.adyen.com/api-explorer/ManagementNotification/latest/post/merchant.updated)
                  webhook. Once the merchant account is activated, you can start
                  using it to accept payments and payouts.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Accounts read and write
            /merchants/{merchantId}/apiCredentials:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Get a list of API credentials
                description: >-
                  Returns the list of [API
                  credentials](https://docs.adyen.com/development-resources/api-credentials)
                  for the merchant account. The list is grouped into pages as
                  defined by the query parameters.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              post:
                tags:
                  - Create
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Create an API credential
                description: >-
                  Creates an [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  for the company account identified in the path. In the
                  request, you can specify the roles and allowed origins for the
                  new API credential.


                  The response includes the:

                  * [API
                  key](https://docs.adyen.com/development-resources/api-authentication#api-key-authentication):
                  used for API request authentication.

                  * [Client
                  key](https://docs.adyen.com/development-resources/client-side-authentication#how-it-works):
                  public key used for client-side authentication.

                  * [Username and
                  password](https://docs.adyen.com/development-resources/api-authentication#using-basic-authentication):
                  used for basic authentication.


                  > Make sure you store the API key securely in your system. You
                  won't be able to retrieve it later.


                  If your API key is lost or compromised, you need to [generate
                  a new API
                  key](https://docs.adyen.com/api-explorer/#/ManagementService/v1/post/merchants/{merchantId}/apiCredentials/{apiCredentialId}/generateApiKey).


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/apiCredentials/{apiCredentialId}:
              get:
                tags:
                  - Get
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Get an API credential
                description: >-
                  Returns the [API
                  credential](https://docs.adyen.com/development-resources/api-credentials)
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              patch:
                tags:
                  - Update
                  - An
                  - Credentials
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Update an API credential
                description: >-
                  Changes the API credential's roles, or allowed origins. The
                  request has the new values for the fields you want to change.
                  The response contains the full updated API credential,
                  including the new values from the request. 


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/apiCredentials/{apiCredentialId}/allowedOrigins:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Allowed
                  - Origins
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Get a list of allowed origins
                description: >-
                  Returns the list of [allowed
                  origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  for the API credential identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              post:
                tags:
                  - Create
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Create an allowed origin
                description: >-
                  Adds a new [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  to the API credential's list of allowed origins.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/apiCredentials/{apiCredentialId}/allowedOrigins/{originId}:
              delete:
                tags:
                  - Delete
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Delete an allowed origin
                description: >-
                  Removes the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  identified in the path. As soon as an allowed origin is
                  removed, we no longer accept client-side requests from that
                  domain.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
              get:
                tags:
                  - Get
                  - An
                  - Allowed
                  - Origin
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Get an allowed origin
                description: >-
                  Returns the [allowed
                  origin](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins)
                  identified in the path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/apiCredentials/{apiCredentialId}/generateApiKey:
              post:
                tags:
                  - Generate
                  - New
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Generate new API key
                description: >-
                  Returns a new API key for the API credential. You can use the
                  new API key a few minutes after generating it. The old API key
                  stops working 24 hours after generating a new one.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/apiCredentials/{apiCredentialId}/generateClientKey:
              post:
                tags:
                  - Generate
                  - New
                  - Client
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Generate new client key
                description: >-
                  Returns a new [client
                  key](https://docs.adyen.com/development-resources/client-side-authentication#how-it-works)
                  for the API credential identified in the path. You can use the
                  new client key a few minutes after generating it. The old
                  client key stops working 24 hours after generating a new one.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—API credentials read and write
            /merchants/{merchantId}/billingEntities:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Billing
                  - Entities
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                summary: Get a list of billing entities
                description: >-
                  Returns the billing entities of the merchant account
                  identified in the path.

                  A billing entity is a legal entity where we charge orders to.
                  An order for terminal products must contain the ID of a
                  billing entity.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/paymentMethodSettings:
              get:
                tags:
                  - Get
                  - All
                  - Payments
                  - Methods
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                summary: Get all payment methods
                description: >
                  Returns details for all payment methods of the merchant
                  account identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read
              post:
                tags:
                  - Request
                  - Payments
                  - Methods
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                summary: Request a payment method
                description: >
                  Sends a request to add a new payment method to the merchant
                  account identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read and write
            /merchants/{merchantId}/paymentMethodSettings/{paymentMethodId}:
              get:
                tags:
                  - Get
                  - Payments
                  - Methods
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                summary: Get payment method details
                description: >
                  Returns details for the merchant account and the payment
                  method identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read
              patch:
                tags:
                  - Update
                  - Payments
                  - Methods
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                summary: Update a payment method
                description: >
                  Updates payment method details for the merchant account and
                  the payment method identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read and write
            /merchants/{merchantId}/paymentMethodSettings/{paymentMethodId}/addApplePayDomains:
              post:
                tags:
                  - Add
                  - An
                  - Apple
                  - Pay
                  - Domains
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                summary: Add an Apple Pay domain
                description: >
                  Adds the new domain to the list of Apple Pay domains that are
                  registered with the merchant account and the payment method
                  identified in the path. For more information, see [Apple Pay
                  documentation](https://docs.adyen.com/payment-methods/apple-pay/enable-apple-pay#register-merchant-domain).


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read and write
            /merchants/{merchantId}/paymentMethodSettings/{paymentMethodId}/getApplePayDomains:
              get:
                tags:
                  - Get
                  - Apple
                  - Pay
                  - Domains
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                summary: Get Apple Pay domains
                description: >
                  Returns all Apple Pay domains that are registered with the
                  merchant account and the payment method identified in the
                  path. For more information, see [Apple Pay
                  documentation](https://docs.adyen.com/payment-methods/apple-pay/enable-apple-pay#register-merchant-domain).


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payment methods read
            /merchants/{merchantId}/payoutSettings:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Payouts
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Get a list of payout settings
                description: >-
                  Returns the list of payout settings for the merchant account
                  identified in the path.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payout account settings read
              post:
                tags:
                  - Add
                  - Payouts
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Add a payout setting
                description: >-
                  Sends a request to add a payout setting for the merchant
                  account specified in the path. A payout setting links the
                  merchant account to the [transfer
                  instrument](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments)
                  that contains the details of the payout bank account. Adyen
                  verifies the bank account before allowing and enabling the
                  payout setting.


                  If you're accepting payments in multiple currencies, you may
                  add multiple payout settings for the merchant account.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):


                  * Management API—Payout account settings read and write
            /merchants/{merchantId}/payoutSettings/{payoutSettingsId}:
              delete:
                tags:
                  - Delete
                  - Payouts
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Delete a payout setting
                description: >-
                  Deletes the payout setting identified in the path.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):


                  * Management API—Payout account settings read and write
              get:
                tags:
                  - Get
                  - Payouts
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Get a payout setting
                description: >-
                  Returns the payout setting identified in the path.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Payout account settings read
              patch:
                tags:
                  - Update
                  - Payouts
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Update a payout setting
                description: >-
                  Updates the payout setting identified in the path. You can
                  enable or disable the payout setting.


                  Use this endpoint if your integration requires it, such as
                  Adyen for Platforms Manage. Your Adyen contact will set up
                  your access.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):


                  * Management API—Payout account settings read and write
            /merchants/{merchantId}/shippingLocations:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Shipping
                  - Locations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Get a list of shipping locations
                description: >-
                  Returns the shipping locations for the merchant account
                  identified in the path.

                  A shipping location includes the address where orders can be
                  delivered, and an ID which you need to specify when ordering
                  terminal products.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              post:
                tags:
                  - Create
                  - Shipping
                  - Locations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                summary: Create a shipping location
                description: >-
                  Creates a shipping location for the merchant account
                  identified in the path. A shipping location defines an address
                  where orders can be shipped to. 


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/splitConfigurations:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Split
                  - Configurations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                summary: Get a list of split configurations
                description: >-
                  Returns the list of split configurations for the merchant
                  account.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
              post:
                tags:
                  - Create
                  - Split
                  - Configurations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                summary: Create a split configuration
                description: >-
                  Creates a split configuration for the merchant account
                  specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
            /merchants/{merchantId}/splitConfigurations/{splitConfigurationId}:
              delete:
                tags:
                  - Delete
                  - Split
                  - Configurations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                summary: Delete a split configuration
                description: >-
                  Deletes the split configuration specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
              get:
                tags:
                  - Get
                  - Split
                  - Configurations
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                summary: Get a split configuration
                description: >-
                  Returns the split configuration specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
              patch:
                tags:
                  - Update
                  - Split
                  - Configurations
                  - Descriptions
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                summary: Update split configuration description
                description: >-
                  Changes the description of the split configuration specified
                  in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
              post:
                tags:
                  - Create
                  - Rules
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                summary: Create a rule
                description: >-
                  Creates a rule in the split configuration specified in the
                  path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
            /merchants/{merchantId}/splitConfigurations/{splitConfigurationId}/rules/{ruleId}:
              delete:
                tags:
                  - Delete
                  - Split
                  - Configurations
                  - Rules
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                summary: Delete a split configuration rule
                description: >-
                  Deletes the split configuration rule specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
              patch:
                tags:
                  - Update
                  - Split
                  - Conditions
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                summary: Update split conditions
                description: >-
                  Changes the conditions of the split configuration rule
                  specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
            /merchants/{merchantId}/splitConfigurations/{splitConfigurationId}/rules/{ruleId}/splitLogic/{splitLogicId}:
              patch:
                tags:
                  - Update
                  - The
                  - Split
                  - Logic
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                summary: Update the split logic
                description: >-
                  Changes the split logic specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API - SplitConfiguration read and write
            /merchants/{merchantId}/stores:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Stores
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                summary: Get a list of stores
                description: >-
                  Returns a list of stores for the merchant account identified
                  in the path. The list is grouped into pages as defined by the
                  query parameters.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read

                  * Management API—Stores read and write
              post:
                tags:
                  - Create
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                summary: Create a store
                description: >-
                  Creates a store for the merchant account identified in the
                  path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read and write
            /merchants/{merchantId}/stores/{reference}/terminalLogos:
              get:
                tags:
                  - Get
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                summary: Get the terminal logo
                description: >-
                  Returns the logo that is configured for a specific payment
                  terminal model at the store identified in the path. 

                  The logo is returned as a Base64-encoded string. You need to
                  Base64-decode the string to get the actual image file. 

                  This logo applies to all terminals of the specified model
                  under the store, unless a different logo is configured for an
                  individual terminal.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                summary: Update the terminal logo
                description: >-
                  Updates the logo that is configured for a specific payment
                  terminal model at the store identified in the path. You can
                  update the logo for only one terminal model at a time.

                  This logo applies to all terminals of the specified model
                  under the store, unless a different logo is configured for an
                  individual terminal. 


                  * To change the logo, specify the image file as a
                  Base64-encoded string.

                  * To restore the logo inherited from a higher level (merchant
                  or company account), specify an empty logo value.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /merchants/{merchantId}/stores/{reference}/terminalSettings:
              get:
                tags:
                  - Get
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                summary: Get terminal settings
                description: >-
                  Returns the payment terminal settings that are configured for
                  the store identified in the path. These settings apply to all
                  terminals under the store unless different values are
                  configured for an individual terminal.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
              patch:
                tags:
                  - Update
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                summary: Update terminal settings
                description: >-
                  Updates payment terminal settings for the store identified in
                  the path. These settings apply to all terminals under the
                  store, unless different values are configured for an
                  individual terminal.


                  * To change a parameter value, include the full object that
                  contains the parameter, even if you don't want to change all
                  parameters in the object.

                  * To restore a parameter value inherited from a higher level,
                  include the full object that contains the parameter, and
                  specify an empty value for the parameter or omit the
                  parameter.

                  * Objects that are not included in the request are not
                  updated.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
            /merchants/{merchantId}/stores/{storeId}:
              get:
                tags:
                  - Get
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a store
                description: >-
                  Returns the details of the store identified in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read

                  * Management API—Stores read and write
              patch:
                tags:
                  - Update
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update a store
                description: >-
                  Updates the store identified in the path. You can only update
                  some store parameters.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read and write
            /merchants/{merchantId}/terminalLogos:
              get:
                tags:
                  - Get
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get the terminal logo
                description: >-
                  Returns the logo that is configured for a specific payment
                  terminal model at the merchant account identified in the
                  path. 

                  The logo is returned as a Base64-encoded string. You need to
                  Base64-decode the string to get the actual image file. 

                  This logo applies to all terminals of the specified model
                  under the merchant account, unless a different logo is
                  configured at a lower level (store or individual terminal).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update the terminal logo
                description: >-
                  Updates the logo for a specific payment terminal model at the
                  merchant account identified in the path. You can update the
                  logo for only one terminal model at a time. 

                  This logo applies to all terminals of the specified model
                  under the merchant account, unless a different logo is
                  configured at a lower level (store or individual terminal).


                  * To change the logo, specify the image file as a
                  Base64-encoded string.

                  * To restore the logo inherited from the company account,
                  specify an empty logo value.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /merchants/{merchantId}/terminalModels:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminal
                  - Models
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a list of terminal models
                description: >-
                  Returns the payment terminal models that merchant account
                  identified in the path has access to. The response includes
                  the terminal model ID, which can be used as a query parameter
                  when getting a list of terminals or a list of products for
                  ordering.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/terminalOrders:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a list of orders
                description: >-
                  Returns a list of terminal products orders for the merchant
                  account identified in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              post:
                tags:
                  - Create
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Create an order
                description: >-
                  Creates an order for payment terminal products for the
                  merchant account identified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write

                  >Requests to the Management API test endpoint do not create
                  actual orders for test terminals. To order test terminals, you
                  need to [submit a sales
                  order](https://docs.adyen.com/point-of-sale/managing-terminals/order-terminals/#sales-order-steps)
                  in your Customer Area.
            /merchants/{merchantId}/terminalOrders/{orderId}:
              get:
                tags:
                  - Get
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get an order
                description: >-
                  Returns the details of the terminal products order identified
                  in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
              patch:
                tags:
                  - Update
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update an order
                description: >-
                  Updates the terminal products order identified in the path.

                  Updating is only possible while the order has the status
                  **Placed**.


                  The request body only needs to contain what you want to
                  change. 

                  However, to update the products in the `items` array, you must
                  provide the entire array. For example, if the array has three
                  items:
                   To remove one item, the array must include the remaining two items. Or to add one item, the array must include all four items.

                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/terminalOrders/{orderId}/cancel:
              post:
                tags:
                  - Cancel
                  - An
                  - Orders
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Cancel an order
                description: >-
                  Cancels the terminal products order identified in the path.

                  Cancelling is only possible while the order has the status
                  **Placed**.

                  To cancel an order, make a POST call without a request body.
                  The response returns the full order details, but with the
                  status changed to **Cancelled**.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/terminalProducts:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminal
                  - Products
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a list of terminal products
                description: >-
                  Returns a country-specific list of payment terminal packages
                  and parts that the merchant account identified in the path has
                  access to.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal ordering read

                  * Management API—Terminal ordering read and write
            /merchants/{merchantId}/terminalSettings:
              get:
                tags:
                  - Get
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get terminal settings
                description: >-
                  Returns the payment terminal settings that are configured for
                  the merchant account identified in the path. These settings
                  apply to all terminals under the merchant account unless
                  different values are configured at a lower level (store or
                  individual terminal).


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update terminal settings
                description: >-
                  Updates payment terminal settings for the merchant account
                  identified in the path.

                  These settings apply to all terminals under the merchant
                  account, unless different values are configured at a lower
                  level (store or individual terminal).


                  * To change a parameter value, include the full object that
                  contains the parameter, even if you don't want to change all
                  parameters in the object.

                  * To restore a parameter value inherited from a higher level,
                  include the full object that contains the parameter, and
                  specify an empty value for the parameter or omit the
                  parameter.

                  * Objects that are not included in the request are not
                  updated.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /merchants/{merchantId}/users:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Users
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a list of users
                description: >
                  Returns a list of users associated with the `merchantId`
                  specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
              post:
                tags:
                  - Create
                  - New
                  - Users
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Create a new user
                description: >
                  Creates a user for the `merchantId` specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
            /merchants/{merchantId}/users/{userId}:
              get:
                tags:
                  - Get
                  - Users
                  - Details
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get user details
                description: >
                  Returns user details for the `userId` and the `merchantId`
                  specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
              patch:
                tags:
                  - Update
                  - Users
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update a user
                description: >
                  Updates user details for the `userId` and the `merchantId`
                  specified in the path.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Users read and write
            /merchants/{merchantId}/webhooks:
              get:
                tags:
                  - Lists
                  - All
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: List all webhooks
                description: >-
                  Lists all webhook configurations for the merchant account.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read

                  * Management API—Webhooks read and write
              post:
                tags:
                  - Sets
                  - Up
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Set up a webhook
                description: >-
                  Subscribe to receive webhook notifications about events
                  related to your merchant account. You can add basic
                  authentication to make sure the data is secure.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /merchants/{merchantId}/webhooks/{webhookId}:
              delete:
                tags:
                  - Removes
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Remove a webhook
                description: >-
                  Remove the configuration for the webhook identified in the
                  path.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
              get:
                tags:
                  - Get
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a webhook
                description: >-
                  Returns the configuration for the webhook identified in the
                  path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read

                  * Management API—Webhooks read and write
              patch:
                tags:
                  - Update
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update a webhook
                description: >-
                  Make changes to the configuration of the webhook identified in
                  the path. The request contains the new values you want to have
                  in the webhook configuration. The response contains the full
                  configuration for the webhook, which includes the new values
                  from the request.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /merchants/{merchantId}/webhooks/{webhookId}/generateHmac:
              post:
                tags:
                  - Generate
                  - An
                  - Keys
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Generate an HMAC key
                description: >-
                  Returns an [HMAC key](https://en.wikipedia.org/wiki/HMAC) for
                  the webhook identified in the path. This key allows you to
                  check the integrity and the origin of the notifications you
                  receive.By creating an HMAC key, you start receiving
                  [HMAC-signed
                  notifications](https://docs.adyen.com/development-resources/webhooks/verify-hmac-signatures#enable-hmac-signatures)
                  from Adyen. Find out more about how to [verify HMAC
                  signatures](https://docs.adyen.com/development-resources/webhooks/verify-hmac-signatures).


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /merchants/{merchantId}/webhooks/{webhookId}/test:
              post:
                tags:
                  - Tests
                  - Webhooks
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Test a webhook
                description: >-
                  Sends sample notifications to test if the webhook is set up
                  correctly.


                  We send four test notifications for each event code you
                  choose. They cover success and failure scenarios for the
                  hard-coded currencies EUR and GBP, regardless of the
                  currencies configured in the merchant accounts. For custom
                  notifications, we only send the specified custom notification.


                  The response describes the result of the test. The `status`
                  field tells you if the test was successful or not. You can use
                  the other fields to troubleshoot unsuccessful tests.


                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Webhooks read and write
            /stores:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Stores
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a list of stores
                description: >-
                  Returns a list of stores. The list is grouped into pages as
                  defined by the query parameters.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read

                  * Management API—Stores read and write
              post:
                tags:
                  - Create
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Create a store
                description: >-
                  Creates a store for the merchant account specified in the
                  request.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read and write
            /stores/{storeId}:
              get:
                tags:
                  - Get
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get a store
                description: >-
                  Returns the details of the store identified in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read

                  * Management API—Stores read and write
              patch:
                tags:
                  - Update
                  - Store
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update a store
                description: >-
                  Updates the store identified in the path.

                  You can only update some store parameters.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Stores read and write
            /stores/{storeId}/terminalLogos:
              get:
                tags:
                  - Get
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get the terminal logo
                description: >-
                  Returns the logo that is configured for a specific payment
                  terminal model at the store identified in the path. 

                  The logo is returned as a Base64-encoded string. You need to
                  Base64-decode the string to get the actual image file. 

                  This logo applies to all terminals of that model under the
                  store unless a different logo is configured for an individual
                  terminal.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update the terminal logo
                description: >-
                  Updates the logo that is configured for a specific payment
                  terminal model at the store identified in the path. You can
                  update the logo for only one terminal model at a time.

                  This logo applies to all terminals of the specified model
                  under the store, unless a different logo is configured for an
                  individual terminal. 


                  * To change the logo, specify the image file as a
                  Base64-encoded string.

                  * To restore the logo inherited from a higher level (merchant
                  or company account), specify an empty logo value.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /stores/{storeId}/terminalSettings:
              get:
                tags:
                  - Get
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Get terminal settings
                description: >-
                  Returns the payment terminal settings that are configured for
                  the store identified in the path. These settings apply to all
                  terminals under the store unless different values are
                  configured for an individual terminal.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
              patch:
                tags:
                  - Update
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                summary: Update terminal settings
                description: >-
                  Updates payment terminal settings for the store identified in
                  the path. These settings apply to all terminals under the
                  store, unless different values are configured for an
                  individual terminal.


                  * To change a parameter value, include the full object that
                  contains the parameter, even if you don't want to change all
                  parameters in the object.

                  * To restore a parameter value inherited from a higher level,
                  include the full object that contains the parameter, and
                  specify an empty value for the parameter or omit the
                  parameter.

                  * Objects that are not included in the request are not
                  updated.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
            /terminals:
              get:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Terminals
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                summary: Get a list of terminals
                description: >-
                  Returns the payment terminals that the API credential has
                  access to and that match the query parameters. 

                  To make this request, your API credential must have the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API — Terminal actions read
            /terminals/scheduleActions:
              post:
                tags:
                  - Create
                  - Terminal
                  - Actions
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                summary: Create a terminal action
                description: >-
                  Schedules a [terminal
                  action](https://docs.adyen.com/point-of-sale/automating-terminal-management/terminal-actions-api)
                  by specifying the action and the terminals that the action
                  must be applied to. 


                  The following restrictions apply:

                  * You can schedule only one action at a time. For example, to
                  install a new app version and remove an old app version, you
                  have to make two API requests. 

                  * The maximum number of terminals in a request is **100**. For
                  example, to apply an action to 250 terminals, you have to
                  divide the terminals over three API requests. 

                  * If there is an error with one or more terminal IDs in the
                  request, the action is scheduled for none of the terminals.
                  You need to fix the error and try again. 


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal actions read and write
            /terminals/{terminalId}/reassign:
              post:
                tags:
                  - Reassign
                  - Terminal
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                  - Reassign
                summary: Reassign a terminal
                description: >-
                  Reassigns a payment terminal to a company account, merchant
                  account, merchant account inventory, or a store.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Assign Terminal
            /terminals/{terminalId}/terminalLogos:
              get:
                tags:
                  - Get
                  - The
                  - Terminal
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                  - Reassign
                summary: Get the terminal logo
                description: >-
                  Returns the logo that is configured for the payment terminal
                  identified in the path.

                  The logo is returned as a Base64-encoded string. You need to
                  Base64-decode the string to get the actual image file.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write
              patch:
                tags:
                  - Update
                  - The
                  - Logo
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                  - Reassign
                summary: Update the logo
                description: >-
                  Updates the logo for the payment terminal identified in the
                  path.


                  * To change the logo, specify the image file as a
                  Base64-encoded string.

                  * To restore the logo inherited from a higher level (store,
                  merchant account, or company account), specify an empty logo
                  value.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write
            /terminals/{terminalId}/terminalSettings:
              get:
                tags:
                  - Get
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                  - Reassign
                summary: Get terminal settings
                description: >-
                  Returns the settings that are configured for the payment
                  terminal identified in the path.


                  To make this request, your API credential must have one of the
                  following
                  [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Terminal settings Advanced read and write
              patch:
                tags:
                  - Update
                  - Terminal
                  - Settings
                  - Companies
                  - Identifiers
                  - Android
                  - Applications
                  - Certificates
                  - APIs
                  - Credentials
                  - Credentials
                  - Allowed
                  - Origins
                  - Origin
                  - Generate
                  - Keys
                  - Client
                  - Billing
                  - Entities
                  - Merchants
                  - Shipping
                  - Locations
                  - Terminal
                  - Actions
                  - Actions
                  - Logos
                  - Models
                  - Orders
                  - Orders
                  - Cancel
                  - Products
                  - Settings
                  - Users
                  - Users
                  - Webhooks
                  - Webhooks
                  - HMAC
                  - Tests
                  - Me
                  - Activate
                  - Payments
                  - Methods
                  - Add
                  - Apple
                  - Pay
                  - Domains
                  - Get
                  - Payouts
                  - Split
                  - Configurations
                  - Configurations
                  - Rules
                  - Rules
                  - Logic
                  - Stores
                  - References
                  - Store
                  - Terminals
                  - Reassign
                summary: Update terminal settings
                description: >-
                  Updates the settings that are configured for the payment
                  terminal identified in the path.


                  * To change a parameter value, include the full object that
                  contains the parameter, even if you don't want to change all
                  parameters in the object.

                  * To restore a parameter value inherited from a higher level,
                  include the full object that contains the parameter, and
                  specify an empty value for the parameter or omit the
                  parameter.

                  * Objects that are not included in the request are not
                  updated.


                  To make this request, your API credential must have the
                  following
                  [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

                  * Management API—Terminal settings read and write


                  For [sensitive terminal
                  settings](https://docs.adyen.com/point-of-sale/automating-terminal-management/configure-terminals-api#sensitive-terminal-settings),
                  your API credential must have the following role:

                  * Management API—Termina
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-parameters-path-names-snake-case-error
              message: Parameter Path Name Snake Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-error
              message: Request Body POST
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-operations-summary-period-none-error
              message: Operation Summary Period
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-no-request-body-on-delete-info
              message: DELETE Request Body
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-204-status-code-info
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-info
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-info
              message: 500 Status Code for DELETE Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/management-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/management-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-management-api
  - name: Adyen Management Webhooks API
    description: >-
      Adyen uses webhooks to inform your system about events that happen with
      your Adyen company and merchant accounts, stores, payment terminals, and
      payment methods when using [Management
      API](https://docs.adyen.com/api-explorer/#/ManagementService/latest/overview).
      When a and includes the details of the event in the request body. See
      [Webhooks](https://docs.adyen.com/development-resources/webhooks) for more
      information.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/#/ManagementService/latest/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/api-explorer/#/ManagementService/latest/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Management Webhooks
          tags:
            - name: Merchant account
            - name: Payment method
          x-staticResponse: response.json
          webhooks:
            merchant.created:
              post:
                tags:
                  - Merchant account
                summary: Merchant account created
                description: >-
                  A merchant account [was
                  created](https://docs.adyen.com/api-explorer/#/ManagementService/latest/post/merchants).
                x-addedInVersion: '1'
                operationId: post-merchant.created
                x-sortIndex: 1
                x-methodName: merchantAccountCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        merchant.created:
                          $ref: >-
                            #/components/examples/post-merchant.created-merchant.created
                      schema:
                        $ref: >-
                          #/components/schemas/MerchantCreatedNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          merchant.created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/AccountNotificationResponse'
                    description: OK - the request has succeeded.
            merchant.updated:
              post:
                tags:
                  - Merchant account
                summary: Merchant account capability updated
                description: >-
                  There were changes to the verification status and capabilities
                  of a [merchant
                  account](https://docs.adyen.com/api-explorer/#/ManagementService/latest/post/merchants).
                  If the verification fails, this webhook includes the errors
                  and the actions that you can take to resolve them.
                x-addedInVersion: '1'
                operationId: post-merchant.updated
                x-sortIndex: 2
                x-methodName: merchantAccountCapabilityUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        merchant-updated-valid:
                          $ref: >-
                            #/components/examples/post-merchant.updated-merchant-updated-valid
                        merchant-updated-with-errors:
                          $ref: >-
                            #/components/examples/post-merchant.updated-merchant-updated-with-errors
                      schema:
                        $ref: >-
                          #/components/schemas/MerchantUpdatedNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          merchant-updated-valid:
                            $ref: '#/components/examples/WebhookAck'
                          merchant-updated-with-errors:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/AccountNotificationResponse'
                    description: OK - the request has succeeded.
            paymentMethod.created:
              post:
                tags:
                  - Payment method
                summary: Payment method created
                description: >-
                  A request to [add a payment
                  method](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/_merchantId_/paymentMethodSettings)
                  was completed.
                x-addedInVersion: '1'
                operationId: post-paymentMethod.created
                x-sortIndex: 1
                x-methodName: paymentMethodCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        paymentMethod.created:
                          $ref: >-
                            #/components/examples/post-paymentMethod.created-paymentMethod.created
                      schema:
                        $ref: >-
                          #/components/schemas/PaymentMethodCreatedNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          paymentMethod.created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/PaymentMethodNotificationResponse
                    description: OK - the request has succeeded.
            paymentMethod.requestRemoved:
              post:
                tags:
                  - Payment method
                summary: Payment method request removed
                description: >-
                  A request to add a payment method is removed. You must make
                  another request to [add a payment
                  method](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/_merchantId_/paymentMethodSettings).
                x-addedInVersion: '2'
                operationId: post-paymentMethod.requestRemoved
                x-sortIndex: 3
                x-methodName: paymentMethodRequestRemoved
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        paymentMethod.requestRemoved:
                          $ref: >-
                            #/components/examples/post-paymentMethod.requestRemoved-paymentMethod.requestRemoved
                      schema:
                        $ref: >-
                          #/components/schemas/PaymentMethodRequestRemovedNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          paymentMethod.requestRemoved:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/PaymentMethodNotificationResponse
                    description: OK - the request has succeeded.
            paymentMethod.requestScheduledForRemoval:
              post:
                tags:
                  - Payment method
                summary: Payment method request scheduled for removal
                description: >-
                  A request to [add a payment
                  method](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/_merchantId_/paymentMethodSettings)
                  will be removed in 30 days. To make sure the payment method is
                  added, provide the missing [KYC
                  information](https://docs.adyen.com/marketplaces-and-platforms/collect-verification-details).
                x-addedInVersion: '2'
                operationId: post-paymentMethod.requestScheduledForRemoval
                x-sortIndex: 2
                x-methodName: paymentMethodRequestScheduledForRemoval
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        paymentMethod.requestScheduledForRemoval:
                          $ref: >-
                            #/components/examples/post-paymentMethod.requestScheduledForRemoval-paymentMethod.requestScheduledForRemoval
                      schema:
                        $ref: >-
                          #/components/schemas/PaymentMethodScheduledForRemovalNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          paymentMethod.requestScheduledForRemoval:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/PaymentMethodNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/management-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/management-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-management-webhooks-api
  - name: Adyen Notification Configuration API
    description: >-
      This API is used for the classic integration. If you are just starting
      your implementation, refer to our [new integration
      guide](https://docs.adyen.com/marketplaces-and-platforms) instead.\n\nThe
      Notification Configuration API provides endpoints for setting up and
      testing notifications that inform you of events on your platform, for
      example when a verification check or a payout has been completed.\n\nFor
      more information, refer to our
      [documentation](https://docs.adyen.com/marketplaces-and-platforms/classic/notifications).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/marketplaces-and-platforms/classic/notifications
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/classic/notifications
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Notification Configuration API
            x-timestamp: '2023-05-30T15:27:19Z'
          x-groups:
            - General
          tags:
            - name: General
          paths:
            /createNotificationConfiguration:
              post:
                tags:
                  - Subscribe
                  - To
                  - Notifications
                  - Notifications
                  - Configurations
                summary: Subscribe to notifications
                description: >-
                  Creates a subscription to notifications informing you of
                  events on your platform. After the subscription is created,
                  the events specified in the configuration will be sent to the
                  URL specified in the configuration. Subscriptions must be
                  configured on a per-event basis (as opposed to, for example, a
                  per-account holder basis), so all event notifications of a
                  marketplace and of a given type will be sent to the same
                  endpoint(s). A marketplace may have multiple endpoints if
                  desired; an event notification may be sent to as many or as
                  few different endpoints as configured.
            /deleteNotificationConfigurations:
              post:
                tags:
                  - Delete
                  - Notifications
                  - Subscriptions
                  - Configurations
                  - Notifications
                  - Configurations
                  - Configurations
                summary: Delete a notification subscription configuration
                description: >-
                  Deletes an existing notification subscription configuration.
                  After the subscription is deleted, no further event
                  notifications will be sent to the URL defined in the
                  subscription.
            /getNotificationConfiguration:
              post:
                tags:
                  - Get
                  - Notifications
                  - Subscriptions
                  - Configurations
                  - Notifications
                  - Configurations
                  - Configurations
                summary: Get a notification subscription configuration
                description: >-
                  Returns the details of the configuration of a notification
                  subscription.
            /getNotificationConfigurationList:
              post:
                tags:
                  - Get
                  - Lists
                  - Of
                  - Notifications
                  - Subscriptions
                  - Configurations
                  - Notifications
                  - Configurations
                  - Configurations
                  - Lists
                summary: Get a list of notification subscription configurations
                description: >-
                  Returns the details of the configurations of all of the
                  notification subscriptions in the platform of the executing
                  user.
            /testNotificationConfiguration:
              post:
                tags:
                  - Tests
                  - Notifications
                  - Configurations
                  - Notifications
                  - Configurations
                  - Configurations
                  - Lists
                summary: Test a notification configuration
                description: >-
                  Tests an existing notification subscription configuration. For
                  each event type specified, a test notification will be
                  generated and sent to the URL configured in the subscription
                  specified.
            /updateNotificationConfiguration:
              post:
                tags:
                  - Update
                  - Notifications
                  - Subscriptions
                  - Configurations
                  - Notifications
                  - Configurations
                  - Configurations
                  - Lists
                summary: Update a notification subscription configuration
                description: >-
                  Updates an existing notification subscription configuration.
                  If you are updating the event types, you must provide all
                  event types, otherwise the previous event type 
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-operations-summary-length-error
              message: Operation Summary Length
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/notification-configurations-openapi-search.yml
      - type: API Evangelist Ratings
        url: >-
          overlays/notification-configurations-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-notification-configuration-api
  - name: Adyen Notification Webhooks API
    description: >-
      Adyen sends notifications through webhooks to inform your system about
      events that occur in the balance platform. These events include, for
      example, a card user making a payment, or a merchant starting a refund.
      When an event occurs, Adyen makes an HTTP POST request to a URL on your
      server and includes the details of the event in the request body. You can
      use the webhooks to build your implementation. For example, you can use
      this information to update balances in your own dashboards or to keep
      track of incoming funds.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/point-of-sale/design-your-integration/notifications/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/point-of-sale/design-your-integration/notifications/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Notification webhooks
            x-timestamp: '2022-09-19T22:19:02Z'
          x-groups:
            - Account holder and balance account
            - Payment Instrument
            - Authorisation, refund, or transfer requests
            - Fund movements
            - Reports
          tags: []
          x-staticResponse: response.json
          webhooks:
            balancePlatform.accountHolder.created:
              post:
                tags:
                  - Account holder and balance account
                summary: Account holder created
                description: >-
                  Adyen sends this webhook when you successfully [create an
                  account
                  holder](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/accountHolders).
                operationId: post-balancePlatform.accountHolder.created
                x-groupName: Account holder and balance account
                x-sortIndex: 5
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-accountHolder-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.created-balancePlatform-accountHolder-created
                      schema:
                        $ref: '#/components/schemas/AccountHolderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-accountHolder-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.accountHolder.updated:
              post:
                tags:
                  - Account holder and balance account
                summary: Account holder updated
                description: >-
                  Adyen sends this webhook when you successfully [update an
                  account
                  holder](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/patch/accountHolders/{id}).
                operationId: post-balancePlatform.accountHolder.updated
                x-groupName: Account holder and balance account
                x-sortIndex: 5
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-accountHolder-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.accountHolder.updated-balancePlatform-accountHolder-updated
                      schema:
                        $ref: '#/components/schemas/AccountHolderNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-accountHolder-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccount.created:
              post:
                tags:
                  - Account holder and balance account
                summary: Balance account created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  balance
                  account](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/balanceAccounts).
                operationId: post-balancePlatform.balanceAccount.created
                x-groupName: Account holder and balance account
                x-sortIndex: 5
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-balanceAccount-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccount.created-balancePlatform-balanceAccount-created
                      schema:
                        $ref: '#/components/schemas/BalanceAccountNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-balanceAccount-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.created:
              post:
                tags:
                  - Account holder and balance account
                summary: Balance account sweep created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  sweep](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/balanceAccounts/{balanceAccountId}/sweeps).
                operationId: post-balancePlatform.balanceAccountSweep.created
                x-groupName: Account holder and balance account
                x-sortIndex: 6
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.created-balancePlatform-sweep-created
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.deleted:
              post:
                tags:
                  - Account holder and balance account
                summary: Balance account sweep deleted
                description: >-
                  Adyen sends this webhook when you successfully [delete a
                  sweep](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/delete/balanceAccounts/{balanceAccountId}/sweeps/{sweepId}).
                operationId: post-balancePlatform.balanceAccountSweep.deleted
                x-groupName: Account holder and balance account
                x-sortIndex: 6
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-deleted:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.deleted-balancePlatform-sweep-deleted
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-deleted:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.balanceAccountSweep.updated:
              post:
                tags:
                  - Account holder and balance account
                summary: Balance account sweep updated
                description: >-
                  Adyen sends this webhook when you successfully [update a
                  sweep](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/patch/balanceAccounts/{balanceAccountId}/sweeps/{sweepId}).
                operationId: post-balancePlatform.balanceAccountSweep.updated
                x-groupName: Account holder and balance account
                x-sortIndex: 6
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-sweep-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.balanceAccountSweep.updated-balancePlatform-sweep-updated
                      schema:
                        $ref: >-
                          #/components/schemas/SweepConfigurationNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-sweep-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.incomingTransfer.created:
              post:
                tags:
                  - Fund movements
                summary: Incoming transfer created
                description: >-
                  Adyen sends this webhook when there are incoming funds due to
                  a refund or a fund transfer. Use the `paymentId` to link to
                  the original refund request or funds transfer request. Check
                  the content of the webhook to differentiate the events.


                  * For refunds, the webhook includes the payment instrument to
                  which funds will be refunded.


                  * For incoming fund transfers, the webhook only includes
                  information about the balance account.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.incomingTransfer.created
                x-groupName: Fund movements
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-incomingTransfer-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.incomingTransfer.created-balancePlatform-incomingTransfer-created
                      schema:
                        $ref: >-
                          #/components/schemas/IncomingTransferNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-incomingTransfer-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.incomingTransfer.updated:
              post:
                tags:
                  - Fund movements
                summary: Outgoing transfer updated
                description: >-
                  Adyen sends this webhook when funds were added to the balance
                  account. This could be due to a refund or a funds transfer.
                  Use the `data.id` to track the original incoming transfer
                  resource in the `balancePlatform.incomingTransfer.created`
                  webhook.


                  The `status` field indicates the event that triggered the
                  webhook. 


                  * For refunds, the `status` is **Refunded**. 


                  * For incoming fund transfers, the `status` is
                  **IncomingTransfer**.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.incomingTransfer.updated
                x-groupName: Fund movements
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-incomingTransfer-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.incomingTransfer.updated-balancePlatform-incomingTransfer-updated
                      schema:
                        $ref: >-
                          #/components/schemas/IncomingTransferNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-incomingTransfer-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.outgoingTransfer.created:
              post:
                tags:
                  - Fund movements
                summary: Outgoing transfer created
                description: >-
                  Adyen sends this webhook when funds were deducted from a
                  balance account due to a capture or a funds transfer. Use the
                  `paymentId` to link to the original payment authorisation or
                  funds transfer request.


                  The `status` field indicates the event that triggered the
                  webhook. 


                  * For captures, the `status` will be **Captured**. 


                  * For outgoing fund transfers, the `status` will be
                  **OutgoingTransfer**.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.outgoingTransfer.created
                x-groupName: Fund movements
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-outgoingTransfer-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.outgoingTransfer.created-balancePlatform-outgoingTransfer-created
                      schema:
                        $ref: >-
                          #/components/schemas/OutgoingTransferNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-outgoingTransfer-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.outgoingTransfer.updated:
              post:
                tags:
                  - Fund movements
                summary: Outgoing transfer updated
                description: >-
                  Adyen sends this webhook when there is updated information
                  after funds have been deducted from a balance account. For
                  example, if the fund transfer failed.


                  Use the `data.id` to track the original outgoing transfer
                  resource from the `balancePlatform.outgoingTransfer.created`
                  webhook.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.outgoingTransfer.updated
                x-groupName: Fund movements
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-outgoingTransfer-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.outgoingTransfer.updated-balancePlatform-outgoingTransfer-updated
                      schema:
                        $ref: >-
                          #/components/schemas/OutgoingTransferNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-outgoingTransfer-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.payment.created:
              post:
                tags:
                  - Authorisation, refund, or transfer requests
                summary: Payment authorisation, refund, or funds transfer initiated
                description: >-
                  Adyen sends this webhook when a payment authorisation, a
                  refund, or a funds transfer has been initiated. This webhook
                  only informs your server of requests. For the actual fund
                  movements, you'll get the information from the subsequent
                  outgoing or incoming transfer webhooks.

                   To differentiate the requests, check the content of the webhook.

                  * For payments, the webhook contains the authorisation result,
                  information about the processing merchant, and shows a
                  negative amount.

                   * For refunds, the webhook contains to which payment instrument the funds will be refunded, and shows a positive amount.

                  * For outgoing or incoming fund transfers, the webhook shows a
                  positive or negative amount depending on the direction of the
                  transfer, and only includes information about the balance
                  account.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.payment.created
                x-groupName: Authorisation, refund, or transfer requests
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-payment-created-authorized:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.created-balancePlatform-payment-created-authorized
                        balancePlatform-payment-created-funds-transfer:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.created-balancePlatform-payment-created-funds-transfer
                        balancePlatform-payment-created-refund-requested:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.created-balancePlatform-payment-created-refund-requested
                        balancePlatform-payment-created-rejected:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.created-balancePlatform-payment-created-rejected
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest-2'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-payment-created-authorized:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-payment-created-funds-transfer:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-payment-created-refund-requested:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-payment-created-rejected:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.payment.updated:
              post:
                tags:
                  - Authorisation, refund, or transfer requests
                summary: Payment authorisation expired or cancelled
                description: >-
                  Adyen sends this webhook when a payment authorisation has
                  expired or has been cancelled. Use the `data.id` to track the
                  original payment authorisation from the
                  `balancePlatform.payment.created` webhook.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.payment.updated
                x-groupName: Authorisation, refund, or transfer requests
                x-sortIndex: 1
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-payment-updated-expired:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.updated-balancePlatform-payment-updated-expired
                        balancePlatform-payment-updated-partially-cancelled:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.updated-balancePlatform-payment-updated-partially-cancelled
                        balancePlatform-payment-updated-partially-expired:
                          $ref: >-
                            #/components/examples/post-balancePlatform.payment.updated-balancePlatform-payment-updated-partially-expired
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest-2'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-payment-updated-expired:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-payment-updated-partially-cancelled:
                            $ref: '#/components/examples/WebhookAck'
                          balancePlatform-payment-updated-partially-expired:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.paymentInstrument.created:
              post:
                tags:
                  - Payment Instrument
                summary: Payment instrument created
                description: >-
                  Adyen sends this webhook when you successfully [create a
                  payment
                  instrument](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/paymentInstruments). 

                  >The notification does not include the card number when
                  creating virtual cards. You can only get the card number in
                  the POST response.
                operationId: post-balancePlatform.paymentInstrument.created
                x-groupName: Payment Instrument
                x-sortIndex: 3
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-paymentInstrument-created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.paymentInstrument.created-balancePlatform-paymentInstrument-created
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-paymentInstrument-created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.paymentInstrument.updated:
              post:
                tags:
                  - Payment Instrument
                summary: Payment instrument updated
                description: >-
                  Adyen sends this webhook when you successfully [update a
                  payment
                  instrument](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/patch/paymentInstruments/{id}). 
                operationId: post-balancePlatform.paymentInstrument.updated
                x-groupName: Payment Instrument
                x-sortIndex: 3
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform-paymentInstrument-updated:
                          $ref: >-
                            #/components/examples/post-balancePlatform.paymentInstrument.updated-balancePlatform-paymentInstrument-updated
                      schema:
                        $ref: '#/components/schemas/PaymentNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform-paymentInstrument-updated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.report.created:
              post:
                tags:
                  - Reports
                summary: Report generated
                description: >-
                  Adyen sends this webhook after a report is generated and ready
                  to be downloaded. The webhook contains the URL at which the
                  report can be downloaded.


                  Before you download reports, ask your Adyen contact for your
                  report credentials. You must use your the credentials to
                  authenticate your GET request.
                operationId: post-balancePlatform.report.created
                x-groupName: Reports
                x-sortIndex: 7
                security:
                  - ApiKeyAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform.report.created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.report.created-balancePlatform.report.created
                      schema:
                        $ref: '#/components/schemas/ReportNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform.report.created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-one-error
              message: One Tag
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/notification-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/notification-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-notification-webhooks-api
  - name: Adyen Notifications API
    description: >-
      The Notification API sends notifications to the endpoints specified in a
      given subscription. Subscriptions are managed through the Notification
      Configuration API. The API specifications listed here detail the format of
      each notification. For more information, refer to our
      [documentation](https://docs.adyen.com/marketplaces-and-platforms/classic/notifications).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/marketplaces-and-platforms/classic/notifications
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/classic/notifications
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Classic Platforms - Notifications
            x-timestamp: '2023-06-02T11:23:48Z'
          x-groups:
            - Account holders
            - Accounts
            - Fund management
            - Other
          tags: []
          x-staticResponse: response.json
          webhooks:
            /ACCOUNT_CLOSED:
              post:
                tags:
                  - Accounts
                summary: Account closed
                description: >-
                  Adyen sends this webhook when [an account is
                  closed](https://docs.adyen.com/api-explorer/#/Account/latest/post/closeAccount).
                operationId: post-ACCOUNT_CLOSED
                x-groupName: Accounts
                x-sortIndex: 3
                x-methodName: accountClosed
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountClosed:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_CLOSED-accountClosed
                      schema:
                        $ref: '#/components/schemas/AccountCloseNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountClosed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_CREATED:
              post:
                tags:
                  - Accounts
                summary: Account created
                description: >-
                  Adyen sends this webhook when [an account is
                  created](https://docs.adyen.com/api-explorer/#/Account/latest/post/createAccount).
                operationId: post-ACCOUNT_CREATED
                x-groupName: Accounts
                x-sortIndex: 1
                x-methodName: accountCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountCreated:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_CREATED-accountCreated
                      schema:
                        $ref: '#/components/schemas/AccountCreateNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountCreated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_FUNDS_BELOW_THRESHOLD:
              post:
                tags:
                  - Fund management
                summary: Liable account's funds are below configured threshold
                description: >-
                  Adyen sends this notification when the current funds of your
                  liable account are below the configured threshold.
                operationId: post-ACCOUNT_FUNDS_BELOW_THRESHOLD
                x-groupName: Fund management
                x-sortIndex: 7
                x-methodName: liableAccountsFundsAreBelowConfiguredThreshold
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountFundsBelowThreshold:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_FUNDS_BELOW_THRESHOLD-accountFundsBelowThreshold
                      schema:
                        $ref: >-
                          #/components/schemas/AccountFundsBelowThresholdNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountFundsBelowThreshold:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_CREATED:
              post:
                tags:
                  - Account holders
                summary: Account holder created
                description: >-
                  Adyen sends this webhook when [an account holder is
                  created](https://docs.adyen.com/api-explorer/#/Account/latest/post/createAccountHolder).
                operationId: post-ACCOUNT_HOLDER_CREATED
                x-groupName: Account holders
                x-sortIndex: 1
                x-methodName: accountHolderCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderCreated-businesses:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_CREATED-accountHolderCreated-businesses
                        accountHolderCreated-failed:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_CREATED-accountHolderCreated-failed
                        accountHolderCreated-individuals:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_CREATED-accountHolderCreated-individuals
                      schema:
                        $ref: '#/components/schemas/AccountHolderCreateNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderCreated-businesses:
                            $ref: '#/components/examples/WebhookAck'
                          accountHolderCreated-failed:
                            $ref: '#/components/examples/WebhookAck'
                          accountHolderCreated-individuals:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_PAYOUT:
              post:
                tags:
                  - Fund management
                summary: Paid out to account holder
                description: >-
                  Adyen sends this notification when a [payout
                  request](https://docs.adyen.com/api-explorer/#/Fund/latest/post/payoutAccountHolder)
                  to an account holder is processed and the payout is scheduled.
                operationId: post-ACCOUNT_HOLDER_PAYOUT
                x-groupName: Fund management
                x-sortIndex: 1
                x-methodName: paidOutToAccountHolder
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderPayout-failed:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_PAYOUT-accountHolderPayout-failed
                        accountHolderPayout-initiated:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_PAYOUT-accountHolderPayout-initiated
                      schema:
                        $ref: '#/components/schemas/AccountHolderPayoutNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderPayout-failed:
                            $ref: '#/components/examples/WebhookAck'
                          accountHolderPayout-initiated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_STATUS_CHANGE:
              post:
                tags:
                  - Account holders
                summary: Account holder status changed
                description: >-
                  Adyen sends this webhook when [the status of an account holder
                  is
                  changed](https://docs.adyen.com/api-explorer/#/Account/latest/post/updateAccountHolderState).
                operationId: post-ACCOUNT_HOLDER_STATUS_CHANGE
                x-groupName: Account holders
                x-sortIndex: 4
                x-methodName: accountHolderStatusChanged
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderStatusChange:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_STATUS_CHANGE-accountHolderStatusChange
                      schema:
                        $ref: >-
                          #/components/schemas/AccountHolderStatusChangeNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderStatusChange:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_STORE_STATUS_CHANGE:
              post:
                tags:
                  - Account holders
                summary: Store status changed
                description: >-
                  Adyen sends this webhook when [the status of a
                  store](https://docs.adyen.com/api-explorer/#/Account/latest/post/createAccountHolder__reqParam_accountHolderDetails-storeDetails-status)
                  associated with an account holder is changed.
                operationId: post-ACCOUNT_HOLDER_STORE_STATUS_CHANGE
                x-groupName: Account holders
                x-sortIndex: 4
                x-methodName: storeStatusChanged
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderStoreStatusChange:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_STORE_STATUS_CHANGE-accountHolderStoreStatusChange
                      schema:
                        $ref: >-
                          #/components/schemas/AccountHolderStoreStatusChangeNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderStoreStatusChange:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_UPCOMING_DEADLINE:
              post:
                tags:
                  - Account holders
                summary: Upcoming deadline
                description: >-
                  Adyen sends this notification when an account holders deadline
                  to fulfill the requirements of a specific event is coming up.
                operationId: post-ACCOUNT_HOLDER_UPCOMING_DEADLINE
                x-groupName: Account holders
                x-sortIndex: 1
                x-methodName: upcomingDeadline
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderUpcomingDeadline:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_UPCOMING_DEADLINE-accountHolderUpcomingDeadline
                      schema:
                        $ref: >-
                          #/components/schemas/AccountHolderUpcomingDeadlineNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderUpcomingDeadline:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_UPDATED:
              post:
                tags:
                  - Account holders
                summary: Account holder updated
                description: >-
                  Adyen sends this webhook when [an account holder is
                  updated](https://docs.adyen.com/api-explorer/#/Account/latest/post/updateAccountHolder).
                operationId: post-ACCOUNT_HOLDER_UPDATED
                x-groupName: Account holders
                x-sortIndex: 2
                x-methodName: accountHolderUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderUpdated:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_UPDATED-accountHolderUpdated
                      schema:
                        $ref: '#/components/schemas/AccountHolderUpdateNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderUpdated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_HOLDER_VERIFICATION:
              post:
                tags:
                  - Account holders
                summary: Verification results received
                description: >-
                  Adyen sends this webhook when verification results are
                  available.
                operationId: post-ACCOUNT_HOLDER_VERIFICATION
                x-groupName: Account holders
                x-sortIndex: 3
                x-methodName: verificationResultsReceived
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountHolderVerification:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_HOLDER_VERIFICATION-accountHolderVerification
                      schema:
                        $ref: >-
                          #/components/schemas/AccountHolderVerificationNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountHolderVerification:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ACCOUNT_UPDATED:
              post:
                tags:
                  - Accounts
                summary: Account updated
                description: >-
                  Adyen sends this webhook when [an account is
                  updated](https://docs.adyen.com/api-explorer/#/Account/latest/post/updateAccount).
                operationId: post-ACCOUNT_UPDATED
                x-groupName: Accounts
                x-sortIndex: 2
                x-methodName: accountUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        accountUpdated:
                          $ref: >-
                            #/components/examples/post-ACCOUNT_UPDATED-accountUpdated
                      schema:
                        $ref: '#/components/schemas/AccountUpdateNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          accountUpdated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /BENEFICIARY_SETUP:
              post:
                tags:
                  - Fund management
                summary: Beneficiary defined
                description: >-
                  Adyen sends this notification when a [benefactor/beneficiary
                  relationship is
                  created](https://docs.adyen.com/api-explorer/#/Fund/latest/post/transferFunds).
                operationId: post-BENEFICIARY_SETUP
                x-groupName: Fund management
                x-sortIndex: 3
                x-methodName: beneficiaryDefined
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        beneficiarySetup:
                          $ref: >-
                            #/components/examples/post-BENEFICIARY_SETUP-beneficiarySetup
                      schema:
                        $ref: '#/components/schemas/BeneficiarySetupNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          beneficiarySetup:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /COMPENSATE_NEGATIVE_BALANCE:
              post:
                tags:
                  - Fund management
                summary: Negative account balances compensated
                description: >-
                  Adyen sends this notification when funds are transferred from
                  your platform's liable account to an overdrawn account to
                  compensate for the overdraft.
                operationId: post-COMPENSATE_NEGATIVE_BALANCE
                x-groupName: Fund management
                x-sortIndex: 5
                x-methodName: negativeAccountBalancesCompensated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        compensateNegativeBalance:
                          $ref: >-
                            #/components/examples/post-COMPENSATE_NEGATIVE_BALANCE-compensateNegativeBalance
                      schema:
                        $ref: >-
                          #/components/schemas/CompensateNegativeBalanceNotification
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          compensateNegativeBalance:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /DIRECT_DEBIT_INITIATED:
              post:
                tags:
                  - Fund management
                summary: Automated direct debit initiated
                description: >-
                  Adyen sends this notification when a [direct debit is
                  initiated](https://docs.adyen.com/api-explorer/#/Fund/latest/post/debitAccountHolder).
                operationId: post-DIRECT_DEBIT_INITIATED
                x-groupName: Fund management
                x-sortIndex: 7
                x-methodName: automatedDirectDebitInitiated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        directDebitInitiated:
                          $ref: >-
                            #/components/examples/post-DIRECT_DEBIT_INITIATED-directDebitInitiated
                      schema:
                        $ref: '#/components/schemas/DirectDebitInitiatedNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          directDebitInitiated:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PAYMENT_FAILURE:
              post:
                tags:
                  - Other
                summary: Booking for a capture or refund failed
                description: >-
                  Adyen sends this notification when a [split
                  payment](https://docs.adyen.com/marketplaces-and-platforms/classic/processing-payments#providing-split-information)
                  booking for a capture or refund fails. When a booking fails
                  due to an invalid account status or an unknown `accountCode`,
                  the funds are credited or debited to or fromyour platform's
                  liable account instead of the account specified in the split
                  data.
                operationId: post-PAYMENT_FAILURE
                x-groupName: Other
                x-sortIndex: 1
                x-methodName: bookingForCaptureOrRefundFailed
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        paymentFailure:
                          $ref: >-
                            #/components/examples/post-PAYMENT_FAILURE-paymentFailure
                      schema:
                        $ref: '#/components/schemas/PaymentFailureNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          paymentFailure:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REFUND_FUNDS_TRANSFER:
              post:
                tags:
                  - Fund management
                summary: Funds transfer between accounts refunded
                description: >-
                  Adyen sends this notification when [funds transferred between
                  accounts are
                  refunded](https://docs.adyen.com/api-explorer/#/Fund/v6/latest/refundFundsTransfer).
                operationId: post-REFUND_FUNDS_TRANSFER
                x-groupName: Fund management
                x-sortIndex: 6
                x-methodName: fundsTransferBetweenAccountsRefunded
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        refundFundsTransfer:
                          $ref: >-
                            #/components/examples/post-REFUND_FUNDS_TRANSFER-refundFundsTransfer
                      schema:
                        $ref: '#/components/schemas/RefundFundsTransferNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          refundFundsTransfer:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REPORT_AVAILABLE:
              post:
                tags:
                  - Other
                summary: Report available
                description: >-
                  Adyen sends this notification when a report has been generated
                  and it is available for download.
                operationId: post-REPORT_AVAILABLE
                x-groupName: Other
                x-sortIndex: 2
                x-methodName: reportAvailable
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        reportAvailable:
                          $ref: >-
                            #/components/examples/post-REPORT_AVAILABLE-reportAvailable
                      schema:
                        $ref: '#/components/schemas/ReportAvailableNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          reportAvailable:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /SCHEDULED_REFUNDS:
              post:
                tags:
                  - Fund management
                summary: >-
                  'Refund Transfers Not Paid Out' call processed and refunds
                  scheduled
                description: >-
                  Adyen sends this notification when a request to [refund
                  transfers that are not yet paid
                  out](https://docs.adyen.com/api-explorer/#/Fund/latest/refundNotPaidOutTransfers)
                  is processed and the associated refunds are scheduled.
                operationId: post-SCHEDULED_REFUNDS
                x-groupName: Fund management
                x-sortIndex: 4
                x-methodName: refundTransfersNotPaidOutCallProcessedAndRefundsScheduled
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        scheduledRefunds:
                          $ref: >-
                            #/components/examples/post-SCHEDULED_REFUNDS-scheduledRefunds
                      schema:
                        $ref: '#/components/schemas/ScheduledRefundsNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          scheduledRefunds:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /TRANSFER_FUNDS:
              post:
                tags:
                  - Fund management
                summary: Funds transferred between accounts
                description: >-
                  Adyen sends this notification when [funds are transferred
                  between
                  accounts](https://docs.adyen.com/api-explorer/#/Fund/latest/post/transferFunds).
                operationId: post-TRANSFER_FUNDS
                x-groupName: Fund management
                x-sortIndex: 2
                x-methodName: fundsTransferredBetweenAccounts
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        transferFunds:
                          $ref: >-
                            #/components/examples/post-TRANSFER_FUNDS-transferFunds
                      schema:
                        $ref: '#/components/schemas/TransferFundsNotification'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          transferFunds:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-one-error
              message: One Tag
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/notifications-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/notifications-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-notifications-api
  - name: Adyen Payments API
    description: >-
      A set of API endpoints that allow you to initiate, settle, and modify
      payments on the Adyen payments platform. You can use the API to accept
      card payments (including One-Click and 3D Secure), bank transfers,
      ewallets, and many other payment methods.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/online-payments/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/online-payments/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Payment API
          tags:
            - name: Payments
            - name: Modifications
          paths:
            /adjustAuthorisation:
              post:
                tags:
                  - Change
                  - The
                  - Authorised
                  - Amount
                  - Authorization
                summary: Change the authorised amount
                description: >-
                  Allows you to increase or decrease the authorised amount after
                  the initial authorisation has taken place. This functionality
                  enables for example tipping, improving the chances your
                  authorisation will be valid, or charging the shopper when they
                  have already left the merchant premises.


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).

                  > If you have a [newer
                  integration](https://docs.adyen.com/online-payments), and are
                  doing:

                  > * [Asynchronous
                  adjustments](https://docs.adyen.com/online-payments/adjust-authorisation#asynchronous-or-synchronous-adjustment),
                  use the
                  [`/payments/{paymentPspReference}/amountUpdates`](https://docs.adyen.com/api-explorer/#/CheckoutService/v67/post/payments/{paymentPspReference}/amountUpdates)
                  endpoint on Checkout API.

                  > * [Synchronous
                  adjustments](https://docs.adyen.com/online-payments/adjust-authorisation#asynchronous-or-synchronous-adjustment),
                  use this endpoint.
            /authorise:
              post:
                tags:
                  - Create
                  - An
                  - Authorization
                  - Authorization
                  - Authorization
                summary: Create an authorisation
                description: >-
                  Creates a payment with a unique reference (`pspReference`) and
                  attempts to obtain an authorisation hold. For cards, this
                  amount can be captured or cancelled later. Non-card payment
                  methods typically don't support this and will automatically
                  capture as part of the authorisation.

                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments)
                  endpoint under Checkout API instead.
            /authorise3d:
              post:
                tags:
                  - Complete
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                summary: Complete a 3DS authorisation
                description: >-
                  For an authenticated 3D Secure session, completes the payment
                  authorisation. This endpoint must receive the `md` and
                  `paResponse` parameters that you get from the card issuer
                  after a shopper pays via 3D Secure.


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce/3d-secure).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/details`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments/details)
                  endpoint under Checkout API instead.
            /authorise3ds2:
              post:
                tags:
                  - Complete
                  - S2
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                summary: Complete a 3DS2 authorisation
                description: >-
                  For an authenticated 3D Secure 2 session, completes the
                  payment authorisation. This endpoint must receive the
                  `threeDS2Token` and `threeDS2Result` parameters.


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce/3d-secure).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/details`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments/details)
                  endpoint under Checkout API instead.
            /cancel:
              post:
                tags:
                  - Cancel
                  - An
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                summary: Cancel an authorisation
                description: >-
                  Cancels the authorisation hold on a payment, returning a
                  unique reference for this request. You can cancel payments
                  after authorisation only for payment methods that support
                  distinct authorisations and captures.


                  For more information, refer to
                  [Cancel](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/cancel).


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/{paymentPspReference}/cancels`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments/{paymentPspReference}/cancels)
                  endpoint under Checkout API instead.
            /cancelOrRefund:
              post:
                tags:
                  - Cancel
                  - Or
                  - Refunds
                  - Payments
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                summary: Cancel or refund a payment
                description: >-
                  Cancels a payment if it has not been captured yet, or refunds
                  it if it has already been captured. This is useful when it is
                  not certain if the payment has been captured or not (for
                  example, when using auto-capture).


                  Do not use this endpoint for payments that involve:
                   * [Multiple partial captures](https://docs.adyen.com/online-payments/capture).
                   * [Split data](https://docs.adyen.com/marketplaces-and-platforms/processing-payments#providing-split-information) either at time of payment or capture for Adyen for Platforms.

                   Instead, check if the payment has been captured and make a corresponding [`/refund`](https://docs.adyen.com/api-explorer/#/Payment/refund) or [`/cancel`](https://docs.adyen.com/api-explorer/#/Payment/cancel) call.

                  For more information, refer to [Cancel or
                  refund](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/cancel-or-refund).


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/{paymentPspReference}/reversals`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments/{paymentPspReference}/reversals)
                  endpoint under Checkout API instead.
            /capture:
              post:
                tags:
                  - Capture
                  - An
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                summary: Capture an authorisation
                description: >+
                  Captures the authorisation hold on a payment, returning a
                  unique reference for this request. Usually the full
                  authorisation amount is captured, however it's also possible
                  to capture a smaller amount, which results in cancelling the
                  remaining authorisation balance.


                  Payment methods that are captured automatically after
                  authorisation don't need to be captured. However, submitting a
                  capture request on these transactions will not result in
                  double charges. If immediate or delayed auto-capture is
                  enabled, calling the capture method is not neccessary.


                  For more information refer to
                  [Capture](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/capture).


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/{paymentPspReference}/captures`](https://docs.adyen.com/api-explorer/#/CheckoutService/v67/post/payments/{paymentPspReference}/captures)
                  endpoint on Checkout API instead.

            /donate:
              post:
                tags:
                  - Create
                  - Donations
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                summary: Create a donation
                description: >-
                  Schedules a new payment to be created (including a new
                  authorisation request) for the specified donation using the
                  payment details of the original payment.


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/donations`](https://docs.adyen.com/api-explorer/#/CheckoutService/latest/post/donations)
                  endpoint under Checkout API instead.
            /getAuthenticationResult:
              post:
                tags:
                  - Get
                  - The
                  - Authentication
                  - Results
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                  - Authentication
                  - Results
                summary: Get the 3DS authentication result
                description: >-
                  Return the authentication result after doing a 3D Secure
                  authentication only.
            /refund:
              post:
                tags:
                  - Refunds
                  - Captured
                  - Payments
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                  - Authentication
                  - Results
                summary: Refund a captured payment
                description: >-
                  Refunds a payment that has previously been captured, returning
                  a unique reference for this request. Refunding can be done on
                  the full captured amount or a partial amount. Multiple
                  (partial) refunds will be accepted as long as their sum
                  doesn't exceed the captured amount. Payments which have been
                  authorised, but not captured, cannot be refunded, use the
                  /cancel method instead.


                  Some payment methods/gateways do not support partial/multiple
                  refunds.

                  A margin above the captured limit can be configured to cover
                  shipping/handling costs.


                  For more information, refer to
                  [Refund](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/refund).


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/payments/{paymentPspReference}/refunds`](https://docs.adyen.com/api-explorer/#/CheckoutService/payments/{paymentPspReference}/refunds)
                  endpoint under Checkout API instead.
            /retrieve3ds2Result:
              post:
                tags:
                  - Get
                  - The
                  - S2
                  - Authentication
                  - Results
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                  - Authentication
                  - Results
                summary: Get the 3DS2 authentication result
                description: >-
                  Retrieves the `threeDS2Result` after doing a 3D Secure 2
                  authentication only.
            /technicalCancel:
              post:
                tags:
                  - Cancel
                  - An
                  - Authorization
                  - Using
                  - Your
                  - References
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                  - Authentication
                  - Results
                summary: Cancel an authorisation using your reference
                description: >-
                  This endpoint allows you to cancel a payment if you do not
                  have the PSP reference of the original payment request
                  available.


                  In your call, refer to the original payment by using the
                  `reference` that you specified in your payment request.


                  For more information, see [Technical
                  cancel](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/cancel#technical-cancel). 


                  > This endpoint is part of our [classic API
                  integration](https://docs.adyen.com/online-payments/classic-integrations/api-integration-ecommerce).
                  If using a [newer
                  integration](https://docs.adyen.com/online-payments), use the
                  [`/cancels`](https://docs.adyen.com/api-explorer/#/CheckoutService/cancels)
                  endpoint under Checkout API instead.
            /voidPendingRefund:
              post:
                tags:
                  - Cancel
                  - An
                  - In-person
                  - Refunds
                  - Authorization
                  - Authorization
                  - Authorization
                  - Authorization
                  - Cancel
                  - Or
                  - Refunds
                  - Capture
                  - Donate
                  - Authentication
                  - Results
                  - Pending
                summary: Cancel an in-person refund
                description: >-
                  This endpoint allows you to cancel an unreferenced refund
                  request before it has been completed.


                  In your call, you can refer to the original refund request
                  either by using the `tenderReference`, or the `pspReference`.
                  We recommend implementing based on the `tenderReference`, as
                  this is generated for both offline and online transactions.


                  For more information, refer to [Cancel an unreferenced
                  refund](https://docs.adyen.com/point-of-sale/re
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payments-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payments-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-payments-api
  - name: Adyen Payouts API
    description: >-
      A set of API endpoints that allow you to store payout details, confirm, or
      decline a payout.\n\nFor more information, refer to [Online
      payouts](https://docs.adyen.com/online-payments/online-payouts).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/online-payments/online-payouts
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/online-payments/online-payouts
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Payout API
          tags:
            - name: Initialization
            - name: Reviewing
            - name: Instant payouts
          paths:
            /confirmThirdParty:
              post:
                tags:
                  - Confirm
                  - Payouts
                  - Third
                  - Party
                summary: Confirm a payout
                description: |-
                  Confirms a previously submitted payout.

                  To cancel a payout, use the `/declineThirdParty` endpoint.
            /declineThirdParty:
              post:
                tags:
                  - Cancel
                  - Payouts
                  - Third
                  - Party
                summary: Cancel a payout
                description: >-
                  Cancels a previously submitted payout.


                  To confirm and send a payout, use the `/confirmThirdParty`
                  endpoint.
            /payout:
              post:
                tags:
                  - Make
                  - An
                  - Instant
                  - Cards
                  - Payouts
                  - Third
                  - Party
                  - Payouts
                summary: Make an instant card payout
                description: >-
                  With this call, you can pay out to your customers, and funds
                  will be made available within 30 minutes on the cardholder's
                  bank account (this is dependent on whether the issuer supports
                  this functionality). Instant card payouts are only supported
                  for Visa and Mastercard cards.
            /storeDetail:
              post:
                tags:
                  - Store
                  - Payouts
                  - Details
                  - Third
                  - Party
                  - Payouts
                  - Detail
                summary: Store payout details
                description: >-
                  Stores payment details under the `PAYOUT` recurring contract.
                  These payment details can be used later to submit a payout via
                  the `/submitThirdParty` call.
            /storeDetailAndSubmitThirdParty:
              post:
                tags:
                  - Store
                  - Details
                  - And
                  - Submit
                  - Payouts
                  - Third
                  - Party
                  - Payouts
                  - Detail
                  - And
                  - Submit
                summary: Store details and submit a payout
                description: >-
                  Submits a payout and stores its details for subsequent
                  payouts.


                  The submitted payout must be confirmed or declined either by a
                  reviewer or via `/confirmThirdParty` or `/declineThirdParty`
                  calls.
            /submitThirdParty:
              post:
                tags:
                  - Submit
                  - Payouts
                  - Third
                  - Party
                  - Payouts
                  - Detail
                  - And
                  - Submit
                summary: Submit a payout
                description: >-
                  Submits a payout using the previously stored payment details.
                  To store payment details, use the `/storeDetail` API call.


                  The submitted payout must be confirmed or declined either by a
                  reviewer or via `/confirmThirdPar
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payouts-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payouts-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-payouts-api
  - name: Adyen POS Terminal API
    description: >-
      This API provides endpoints for managing your point-of-sale (POS) payment
      terminals. You can use the API to obtain information about a specific
      terminal, retrieve overviews of your terminals and stores, and assign
      terminals to a merchant account or store.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/point-of-sale/design-your-integration/terminal-api/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/point-of-sale/design-your-integration/terminal-api/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: POS Terminal Management API
          tags:
            - name: General
          paths:
            /assignTerminals:
              post:
                tags:
                  - Assign
                  - Terminals
                  - Terminals
                summary: Assign terminals
                description: >-
                  Assigns one or more payment terminals to a merchant account or
                  a store. You can also use this endpoint to reassign terminals
                  between merchant accounts or stores, and to unassign a
                  terminal and return it to company inventory.
            /findTerminal:
              post:
                tags:
                  - Get
                  - The
                  - Account
                  - Or
                  - Store
                  - Of
                  - Terminal
                  - Terminals
                  - Terminal
                summary: Get the account or store of a terminal
                description: >-
                  Returns the company account, merchant account, or store that a
                  payment terminal is assigned to.
            /getStoresUnderAccount:
              post:
                tags:
                  - Get
                  - The
                  - Stores
                  - Of
                  - An
                  - Account
                  - Terminals
                  - Terminal
                  - Stores
                  - Under
                  - Account
                summary: Get the stores of an account
                description: >-
                  Returns a list of stores associated with a company account or
                  a merchant account, including the status of each store.
            /getTerminalDetails:
              post:
                tags:
                  - Get
                  - The
                  - Details
                  - Of
                  - Terminal
                  - Terminals
                  - Terminal
                  - Stores
                  - Under
                  - Account
                  - Details
                summary: Get the details of a terminal
                description: >-
                  Returns the details of a payment terminal, including where the
                  terminal is assigned to. The response returns the same details
                  that are provided in the terminal list in your Customer Area
                  and in the Terminal Fleet report.
            /getTerminalsUnderAccount:
              post:
                tags:
                  - Get
                  - The
                  - Lists
                  - Of
                  - Terminals
                  - Terminals
                  - Terminal
                  - Stores
                  - Under
                  - Account
                  - Details
                summary: Get the list of terminals
                description: >-
                  Returns a list of payment terminals associated with a company
                  account, merchant account, or store. The response shows
                  whether the terminals are in the inventory, or in-store (ready
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/pos-terminal-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/pos-terminal-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-pos-terminal-api
  - name: Adyen Recurring API
    description: >-
      The Recurring APIs allow you to manage and remove your tokens or saved
      payment details. Tokens should be created with validation during a payment
      request. For more information, refer to our [Tokenization
      documentation](https://docs.adyen.com/online-payments/tokenization).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/online-payments/tokenization
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/online-payments/tokenization
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Recurring API
          tags:
            - name: General
          paths:
            /createPermit:
              post:
                tags:
                  - Create
                  - New
                  - Permits
                  - Linked
                  - To
                  - Recurring
                  - Contracts
                  - Permits
                summary: Create new permits linked to a recurring contract.
                description: >-
                  Create permits for a recurring contract, including support for
                  defining restrictions.
            /disable:
              post:
                tags:
                  - Disable
                  - Stored
                  - Payments
                  - Details
                  - Permits
                  - Disable
                summary: Disable stored payment details
                description: >-
                  Disables stored payment details to stop charging a shopper
                  with this particular recurring detail ID.


                  For more information, refer to [Disable stored
                  details](https://docs.adyen.com/classic-integration/recurring-payments/disable-stored-details/).
            /disablePermit:
              post:
                tags:
                  - Disable
                  - An
                  - Existing
                  - Permits
                  - Permits
                  - Disable
                summary: Disable an existing permit.
                description: >-
                  Disable a permit that was previously linked to a
                  recurringDetailReference.
            /listRecurringDetails:
              post:
                tags:
                  - Get
                  - Stored
                  - Payments
                  - Details
                  - Permits
                  - Disable
                  - Recurring
                  - Details
                summary: Get stored payment details
                description: >-
                  Lists the stored payment details for a shopper, if there are
                  any available. The recurring detail ID can be used with a
                  regular authorisation request to charge the shopper. A summary
                  of the payment detail is returned for presentation to the
                  shopper.


                  For more information, refer to [Retrieve stored
                  details](https://docs.adyen.com/classic-integration/recurring-payments/retrieve-stored-details/).
            /notifyShopper:
              post:
                tags:
                  - Ask
                  - Issuer
                  - To
                  - Notify
                  - The
                  - Shopper
                  - Permits
                  - Disable
                  - Recurring
                  - Details
                  - Shopper
                summary: Ask issuer to notify the shopper
                description: >-
                  Sends a request to the issuer so they can inform the shopper
                  about the upcoming recurring payment. This endpoint is used
                  only for local acquiring in India. For more information, refer
                  to [Recurring card payments in
                  India](https://docs.adyen.com/payment-methods/cards/cards-recurring-india).
            /scheduleAccountUpdater:
              post:
                tags:
                  - Schedules
                  - Running
                  - The
                  - Account
                  - Updater
                  - Permits
                  - Disable
                  - Recurring
                  - Details
                  - Shopper
                  - Account
                  - Updater
                summary: Schedule running the Account Updater
                description: >-
                  When making the API call, you can submit either the credit
                  card information, or the recurring detail reference and the
                  shopper reference:

                  * If the card information is provided, all the sub-fields for
                  `card` are mandatory.

                  * If the recurring detail reference is provided, the fields
                  for `shopperReference` and `selectedRecurr
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-error
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/recurring-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/recurring-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-recurring-api
  - name: Adyen Report Webhooks API
    description: >-
      Adyen sends webhooks to inform your system that reports were generated and
      are ready to be downloaded. You can download reports programmatically by
      making an HTTP GET request, or manually from your [Balance Platform
      Customer Area](https://balanceplatform-test.adyen.com/balanceplatform).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/report-webhooks/1/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/report-webhooks/1/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Report Webhooks
          tags:
            - name: General
          webhooks:
            balancePlatform.report.created:
              post:
                tags:
                  - General
                summary: Report generated
                description: >-
                  Adyen sends this webhook after a report is generated and ready
                  to be downloaded. The webhook contains the URL at which the
                  report can be downloaded.


                  Before you download reports, ask your Adyen contact for your
                  report credentials. You must use your the credentials to
                  authenticate your GET request.
                operationId: post-balancePlatform.report.created
                x-sortIndex: 0
                x-methodName: reportGenerated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        balancePlatform.report.created:
                          $ref: >-
                            #/components/examples/post-balancePlatform.report.created-balancePlatform.report.created
                      schema:
                        $ref: '#/components/schemas/ReportNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          balancePlatform.report.created:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/report-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/report-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-report-webhooks-api
  - name: Adyen Stored Value API
    description: A set of API endpoints to manage stored value products.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/payment-methods/gift-cards/stored-value-api/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/payment-methods/gift-cards/stored-value-api/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Stored Value API
          x-groups:
            - General
          tags:
            - name: General
          paths:
            /changeStatus:
              post:
                tags:
                  - Changes
                  - The
                  - Status
                  - Of
                  - Payments
                  - Methods
                  - Status
                summary: Changes the status of the payment method.
                description: >-
                  Changes the status of the provided payment method to the
                  specified status.
            /checkBalance:
              post:
                tags:
                  - Checks
                  - The
                  - Balances
                  - Status
                  - Balance
                summary: Checks the balance.
                description: Checks the balance of the provided payment method.
            /issue:
              post:
                tags:
                  - Issues
                  - New
                  - Cards
                  - Status
                  - Balance
                  - Issues
                summary: Issues a new card.
                description: Issues a new card of the given payment method.
            /load:
              post:
                tags:
                  - Loads
                  - The
                  - Payments
                  - Methods
                  - Status
                  - Balance
                  - Issues
                  - Load
                summary: Loads the payment method.
                description: Loads the payment method with the specified funds.
            /mergeBalance:
              post:
                tags:
                  - Merge
                  - The
                  - Balance
                  - Of
                  - Two
                  - Cards
                  - Status
                  - Balance
                  - Issues
                  - Load
                summary: Merge the balance of two cards.
                description: >-
                  Increases the balance of the paymentmethod by the full amount
                  left on the source paymentmethod
            /voidTransaction:
              post:
                tags:
                  - Voids
                  - Transactions
                  - Status
                  - Balance
                  - Issues
                  - Load
                  - Transactions
                summary: Voids a transaction.
                description: Voids the
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-error
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/stored-value-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/stored-value-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-stored-value-api
  - name: Adyen Terminal API
    description: >-
      The Adyen Terminal API lets you make payments, issue refunds, collect
      shopper information, and perform other shopper-terminal interactions using
      a payment terminal supplied by Adyen.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/point-of-sale/design-your-integration/terminal-api/terminal-api-reference/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/point-of-sale/design-your-integration/terminal-api/terminal-api-reference/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            title: Adyen Terminal API
          paths:
            /login:
              post:
                description: >-
                  It conveys Information related to the session (period between
                  a Login and the following Logout) to process. Content of the
                  Login Request message.
                summary: Login Request
                tags:
                  - Login
                  - Request
                  - Login
            /logout:
              post:
                description: Empty. Content of the Logout Request message.
                summary: Logout Request
                tags:
                  - Logout
                  - Request
                  - Login
                  - Logout
            /enableservice:
              post:
                description: >-
                  It conveys the services that will be enabled for the  POI
                  Terminal without the request of the Sale System, and a
                  possible invitation for the Customer to start the services.
                  Content of the Enable Service Request message.
                summary: EnableService Request
                tags:
                  - Enable
                  - Services
                  - Request
                  - Login
                  - Logout
                  - Enable Service
            /admin:
              post:
                description: Empty. Content of the Custom Admin Request message.
                summary: Admin Request
                tags:
                  - Administrative
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
            /payment:
              post:
                description: >-
                  Request sent to terminal to initiate payment.  It conveys
                  Information related to the Payment transaction to process.
                  Content of the Payment Request message.
                summary: Payment Request
                tags:
                  - Payments
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
            /cardacquisition:
              post:
                description: >-
                  It conveys Information related to the payment and loyalty
                  cards to read and analyse. This message pair is usually
                  followed by a message pair (e.g. payment or loyalty) which
                  refers to this Card Acquisition message pair. Content of the
                  Card Acquisition Request message.
                summary: CardAcquisition Request
                tags:
                  - Cards
                  - Acquisition
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
            /loyalty:
              post:
                description: >-
                  It conveys Information related to the Loyalty transaction to
                  process. Content of the Loyalty Request message.
                summary: Loyalty Request
                tags:
                  - Loyalty
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
            /storedvalue:
              post:
                description: >-
                  It conveys Information related to the Stored Value transaction
                  to process. Content of the Stored Value Request message.
                summary: StoredValue Request
                tags:
                  - Stored
                  - Value
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
            /reversal:
              post:
                description: >-
                  It conveys Information related to the reversal of a previous
                  payment or a loyalty transaction. Content of the Reversal
                  Request message.
                summary: Reversal Request
                tags:
                  - Reversals
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
            /reconciliation:
              post:
                description: >-
                  It conveys Information related to the Reconciliation requested
                  by the Sale System. Content of the Reconciliation Request
                  message.
                summary: Reconciliation Request
                tags:
                  - Reconciliation
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
            /gettotals:
              post:
                description: >-
                  It conveys information from the Sale System related to the
                  scope and the format of the totals to be computed by the POI
                  System. Content of the Get Totals Request message.
                summary: GetTotals Request
                tags:
                  - Get
                  - Totals
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
            /balanceinquiry:
              post:
                description: >-
                  It conveys Information related to the account for which a
                  Balance Inquiry is requested. Content of the Balance Inquiry
                  Request message.
                summary: BalanceInquiry Request
                tags:
                  - Balance
                  - Inquiries
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
            /transactionstatus:
              post:
                description: >-
                  It conveys Information requested for status of the last or
                  current Payment, Loyalty or Reversal transaction. Content of
                  the TransactionStatus Request message.
                summary: TransactionStatus Request
                tags:
                  - Transactions
                  - Status
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
            /diagnosis:
              post:
                description: >-
                  It conveys Information related to the target POI for which the
                  diagnosis is requested. Content of the Diagnosis Request
                  message.
                summary: Diagnosis Request
                tags:
                  - Diagnosis
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
                  - Diagnosis
            /display:
              post:
                description: >-
                  It conveys the data to display and the way to process the
                  display. It contains the complete content to display. It might
                  contain an operation (the DisplayOutput element) per Display
                  Device type. Content of the Display Request message.
                summary: Display Request
                tags:
                  - Display
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
                  - Diagnosis
                  - Display
            /input:
              post:
                description: >-
                  It conveys data to display and the way to process the display,
                  and contains the complete content to display. In addition to
                  the display on the Input Device, it might contain an operation
                  (the DisplayOutput element) per Display Device type. Content
                  of the Input Request message.
                summary: Input Request
                tags:
                  - Inputs
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
                  - Diagnosis
                  - Display
                  - Inputs
            /print:
              post:
                description: >-
                  It conveys the data to print and the way to process the print.
                  It contains the complete content to print. Content of the
                  Print Request message.
                summary: Print Request
                tags:
                  - Print
                  - Request
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
                  - Diagnosis
                  - Display
                  - Inputs
                  - Print
            /cardreaderapdu:
              post:
                description: >-
                  It contains the APDU request to send to the chip of the card,
                  and a possible invitation message to display on the
                  CashierInterface or the CustomerInterface. Content of the Card
                  Reader APDU Request message.
                summary: CardReaderAPDU Reque
                tags:
                  - Cards
                  - Readers
                  - Reque
                  - Login
                  - Logout
                  - Enable Service
                  - Administrative
                  - Payments
                  - Card Acquisitions
                  - Loyalty
                  - Stored Values
                  - Reversals
                  - Reconciliation
                  - Gettotals
                  - Balance Inquiry
                  - Transaction Status
                  - Diagnosis
                  - Display
                  - Inputs
                  - Print
                  - Card Reader Applications
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-info-contact-error
              message: Contact Object
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-terms-of-service-error
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-operation-ids-error
              message: Operation ID.
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-examples-info
              message: Schema Enum
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/terminal-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/terminal-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-terminal-api
  - name: Adyen Test Cards API
    description: >-
      The Test Cards API provides endpoints for generating custom test card
      numbers. For more information, refer to [Custom test
      cards](https://docs.adyen.com/development-resources/testing/create-test-cards)
      documentation.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/development-resources/testing/create-test-cards
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/development-resources/testing/create-test-cards
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Adyen Test Cards API
            x-timestamp: '2022-05-03T09:24:07Z'
          x-groups:
            - General
          tags:
            - name: General
          paths:
            /createTestCardRanges:
              post:
                tags:
                  - Creates
                  - One
                  - Or
                  - More
                  - Tests
                  - Cards
                  - Ranges
                  - Tests
                  - Cards
                  - Ranges
                summary: Creates one or more test card ranges.
                description: null
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-error
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/test-cards-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/test-cards-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-test-cards-api
  - name: Adyen Transaction Webhooks API
    description: >-
      Adyen sends webhooks to inform your system about incoming and outgoing
      transfers in your platform. You can use these webhooks to build your
      implementation. For example, you can use this information to update
      balances in your own dashboards or to keep track of incoming funds.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/business-accounts/transactions/transaction-webhooks/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/business-accounts/transactions/transaction-webhooks/
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Transaction webhooks
          x-groups:
            - General
          tags:
            - name: General
          x-staticResponse: response.json
          webhooks:
            balancePlatform.transaction.created:
              post:
                tags:
                  - General
                summary: Transaction created
                description: Adyen sends this webhook when there are new fund transfers.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.transaction.created
                x-groupName: General
                x-sortIndex: 0
                x-methodName: transactionCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      schema:
                        $ref: '#/components/schemas/TransactionNotificationRequestV4'
                responses:
                  '200':
                    content:
                      application/json:
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/transaction-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/transaction-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-transaction-webhooks-api
  - name: Adyen Transfer Webhooks API
    description: >-
      Adyen sends webhooks to inform your system about incoming and outgoing
      transfers in your platform. You can use these webhooks to build your
      implementation. For example, you can use this information to update
      balances in your own dashboards or to keep track of incoming funds.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/api-explorer/transfer-webhooks/3/overview
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/api-explorer/transfer-webhooks/3/overview
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Transfer webhooks
          tags:
            - name: General
          x-staticResponse: response.json
          webhooks:
            balancePlatform.transfer.created:
              post:
                tags:
                  - General
                summary: Transfer created
                description: >-
                  Adyen sends this webhook when there are fund movements on your
                  platform.
                x-addedInVersion: '1'
                operationId: post-balancePlatform.transfer.created
                x-sortIndex: 0
                x-methodName: transferCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      schema:
                        $ref: '#/components/schemas/TransferNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeeded.
            balancePlatform.transfer.updated:
              post:
                tags:
                  - General
                summary: Transfer updated
                description: >+
                  Adyen sends this webhook when the status of a transfer
                  changes. Use the `data.id` to track the original transfer
                  resource in the
                  [balancePlatform.transfer.created](https://docs.adyen.com/api-explorer/transfer-webhooks/1/post/balancePlatform.transfer.created)
                  webhook.


                  The `status` field indicates the event that triggered the
                  webhook. 

                x-addedInVersion: '1'
                operationId: post-balancePlatform.transfer.updated
                x-sortIndex: 0
                x-methodName: transferUpdated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      schema:
                        $ref: '#/components/schemas/TransferNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        schema:
                          $ref: >-
                            #/components/schemas/BalancePlatformNotificationResponse
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/transfer-webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/transfer-webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-transfer-webhooks-api
  - name: Adyen Transfers API
    description: >-
      This API provides endpoints that you can use to transfer funds, whether
      when [paying out to a transfer
      instrument](https://docs.adyen.com/marketplaces-and-platforms/payout-to-users/on-demand-payouts),
      [sending funds to third
      parties](https://docs.adyen.com/marketplaces-and-platforms/business-accounts/send-receive-funds)
      for users with business bank accounts, or to [request a payout for a grant
      offer](https://docs.adyen.com/marketplaces-and-platforms/capital). The API
      also supports use cases for [getting transactions for business bank
      accounts](https://docs.adyen.com/marketplaces-and-platforms/business-accounts/transactions-api)
      and getting [grants and its outstanding
      balances](https://docs.adyen.com/marketplaces-and-platforms/capital#get-balances).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://docs.adyen.com/marketplaces-and-platforms/payout-to-users/on-demand-payouts
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: >-
          https://docs.adyen.com/marketplaces-and-platforms/payout-to-users/on-demand-payouts
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Transfers API
          tags:
            - name: Transfers
            - name: Transactions
            - name: Capital
          paths:
            /grants:
              get:
                tags:
                  - Get
                  - Capital
                  - Account
                  - Grants
                summary: Get a capital account
                description: Returns a list of grants with status and outstanding balances.
              post:
                tags:
                  - Request
                  - Grant
                  - Payouts
                  - Grants
                summary: Request a grant payout
                description: Requests the payout of the selected grant offer.
            /grants/{id}:
              get:
                tags:
                  - Get
                  - Grant
                  - References
                  - Details
                  - Grants
                  - Identifiers
                summary: Get grant reference details
                description: >-
                  Returns the details of a capital account specified in the
                  path.
            /transactions:
              get:
                tags:
                  - Get
                  - All
                  - Transactions
                  - Grants
                  - Identifiers
                  - Transactions
                summary: Get all transactions
                description: >+
                  >Versions 1 and 2 of the Transfers API are deprecated. If you
                  are just starting your implementation, use the latest version.


                  Returns all the transactions related to a balance account,
                  account holder, or balance platform.


                  When making this request, you must include at least one of the
                  following:

                  - `balanceAccountId`

                  - `accountHolderId`

                  - `balancePlatform`.


                  This endpoint supports cursor-based pagination. The response
                  returns the first page of results, and returns links to the
                  next and previous pages when applicable. You can use the links
                  to page through the results.

            /transactions/{id}:
              get:
                tags:
                  - Get
                  - Transactions
                  - Grants
                  - Identifiers
                  - Transactions
                summary: Get a transaction
                description: >-
                  >Versions 1 and 2 of the Transfers API are deprecated. If you
                  are just starting your implementation, use the latest version.


                  Returns a transaction.
            /transfers:
              post:
                tags:
                  - Transfers
                  - Funds
                  - Grants
                  - Identifiers
                  - Transactions
                  - Transfers
                summary: Transfer funds
                description: >-
                  >Versions 1 and 2 of the Transfers API are deprecated. If you
                  are just starting your implementation, use the latest version.


                  Starts a request to transfer funds to [balance
                  accounts](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/post/balanceAccounts),
                  [transfer
                  instruments](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/transferInstruments),
                  or third-party bank accounts. Adyen sends the outcome of the
                  transfer request through webhooks.


                  To use this endpoint, you need an additional role for your API
                  credential and transfers must be enabled for the source
                  balance account. Your Adyen contact will set these up for you.
            /transfers/{transferId}/returns:
              post:
                tags:
                  - Returns
                  - Transfers
                  - Grants
                  - Identifiers
                  - Transactions
                  - Transfers
                  - Returns
                summary: Return a transfer
                description: Returns previously transferred funds w
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-description-length-error
              message: Info Description Length
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-version-in-path-info
              message: Version in Path
            - code: openapi-no-request-body-on-get-info
              message: GET Request Body
            - code: openapi-operations-tags-info
              message: Operation Tags
            - code: openapi-operations-summary-info
              message: Operation Summary
            - code: openapi-operations-summary-period-none-info
              message: Operation Summary Period
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-operation-security-definitions-info
              message: Operation Security Definition
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-response-get-200-status-code-info
              message: GET Response Has 200 Status Code
            - code: openapi-responses-examples-error
              message: Schema COULD have an example.
            - code: openapi-response-get-200-content-info
              message: GET Content
            - code: openapi-response-get-200-media-type-info
              message: JSON Media Type GET
            - code: openapi-response-get-200-media-type-schema-info
              message: Schema GET
            - code: openapi-response-get-200-schema-ref-warn
              message: GET Response 200 Schema Ref
            - code: openapi-response-get-400-status-code-info
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-info
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-info
              message: 500 Status Code for GET Responses
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-have-application-json-info
              message: Request Body Application JSON
            - code: openapi-request-body-json-media-type-on-post-info
              message: JSON Media Type POST
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-names-snake-case-error
              message: Request Body Schema Property Names Snake Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-info
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-info
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-info
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-parameters-path-names-snake-case-error
              message: Parameter Path Name Snake Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-oneof-info
              message: Schema Properties OneOf
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/transfers-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/transfers-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-transfers-api
  - name: Adyen Webhooks API
    description: >-
      We use webhooks to send you updates about payment status updates, newly
      available reports, and other events that you can subscribe to. For more
      information, refer to our
      [documentation](https://docs.adyen.com/development-resources/webhooks).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://docs.adyen.com/development-resources/webhooks
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://docs.adyen.com/development-resources/webhooks
      - type: OpenAPI
        data:
          openapi: 3.1.0
          info:
            x-publicVersion: true
            title: Webhooks
          tags:
            - name: Standard
            - name: Disputes
            - name: Payouts
            - name: Additional configuration
            - name: Webhooks
          x-staticResponse: response.json
          webhooks:
            /ACH_NOTIFICATION_OF_CHANGE:
              post:
                tags:
                  - Other webhooks
                summary: ACH Notification of Change
                description: >-
                  An ACH Notification of Change was processed regarding changed
                  bank account details.
                operationId: post-ACH_NOTIFICATION_OF_CHANGE
                x-sortIndex: 0
                x-methodName: achNotificationOfChange
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        ach_notification_of_change:
                          $ref: >-
                            #/components/examples/post-ACH_NOTIFICATION_OF_CHANGE-ach_notification_of_change
                      schema:
                        $ref: >-
                          #/components/schemas/AchNotificationOfChangeNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          ach_notification_of_change:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /AUTHORISATION:
              post:
                tags:
                  - Standard
                summary: Result of authorisation request
                description: >-
                  The result of the [authorisation
                  request](https://docs.adyen.com/api-explorer/#/Payment/latest/post/authorise).
                operationId: post-AUTHORISATION
                x-sortIndex: 0
                x-methodName: resultOfAuthorisationRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        authorisation:
                          $ref: >-
                            #/components/examples/post-AUTHORISATION-authorisation
                      schema:
                        $ref: '#/components/schemas/AuthorisationNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          authorisation:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /AUTHORISATION_ADJUSTMENT:
              post:
                tags:
                  - Standard
                summary: Result of payment authorisation adjustment request
                description: >-
                  The result of the request to [adjust the authorised
                  amount](https://docs.adyen.com/online-payments/adjust-authorisation)
                  sent through the
                  [/adjustAuthorisation](https://docs.adyen.com/api-explorer/#/Payment/latest/post/adjustAuthorisation)
                  endpoint.
                operationId: post-AUTHORISATION_ADJUSTMENT
                x-sortIndex: 0
                x-methodName: resultOfPaymentAuthorisationAdjustmentRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        authorisation_adjustment:
                          $ref: >-
                            #/components/examples/post-AUTHORISATION_ADJUSTMENT-authorisation_adjustment
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          authorisation_adjustment:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /AUTORESCUE:
              post:
                tags:
                  - Additional configuration
                summary: Auto Rescue process ended
                description: >-
                  The [Auto Rescue
                  process](https://docs.adyen.com/online-payments/auto-rescue#rescue-process-ended)
                  ended.
                operationId: post-AUTORESCUE
                x-sortIndex: 0
                x-methodName: autoRescueProcessEnded
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        autorescue:
                          $ref: '#/components/examples/post-AUTORESCUE-autorescue'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          autorescue:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CANCELLATION:
              post:
                tags:
                  - Standard
                summary: Result of cancel request
                description: >-
                  The result of the request to [cancel a
                  payment](https://docs.adyen.com/online-payments/cancel).
                operationId: post-CANCELLATION
                x-sortIndex: 0
                x-methodName: resultOfCancelRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        cancellation:
                          $ref: '#/components/examples/post-CANCELLATION-cancellation'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          cancellation:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CANCEL_AUTORESCUE:
              post:
                tags:
                  - Additional configuration
                summary: Auto Rescue process canceled
                description: >-
                  The [Auto Rescue
                  process](https://docs.adyen.com/online-payments/auto-rescue)
                  was canceled.
                operationId: post-CANCEL_AUTORESCUE
                x-sortIndex: 0
                x-methodName: autoRescueProcessCanceled
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        cancel_autorescue:
                          $ref: >-
                            #/components/examples/post-CANCEL_AUTORESCUE-cancel_autorescue
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          cancel_autorescue:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CANCEL_OR_REFUND:
              post:
                tags:
                  - Standard
                summary: Result of cancel or refund request
                description: >-
                  The result of the request to [cancel or refund a
                  payment](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/cancel-or-refund).
                operationId: post-CANCEL_OR_REFUND
                x-sortIndex: 0
                x-methodName: resultOfCancelOrRefundRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        cancel_or_refund:
                          $ref: >-
                            #/components/examples/post-CANCEL_OR_REFUND-cancel_or_refund
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          cancel_or_refund:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CAPTURE:
              post:
                tags:
                  - Standard
                summary: Result of capture request
                description: >-
                  The result of the request to [capture a
                  payment](https://docs.adyen.com/online-payments/capture).
                operationId: post-CAPTURE
                x-sortIndex: 0
                x-methodName: resultOfCaptureRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        capture:
                          $ref: '#/components/examples/post-CAPTURE-capture'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          capture:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CAPTURE_FAILED:
              post:
                tags:
                  - Standard
                summary: Capture request failed due to scheme rejection
                description: >-
                  The capture request [failed due to rejection by the card
                  scheme](https://docs.adyen.com/online-payments/capture#failed-capture).
                operationId: post-CAPTURE_FAILED
                x-sortIndex: 0
                x-methodName: captureRequestFailedDueToSchemeRejection
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        capture_failed:
                          $ref: >-
                            #/components/examples/post-CAPTURE_FAILED-capture_failed
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          capture_failed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CHARGEBACK:
              post:
                tags:
                  - Dispute
                summary: Payment charged back
                description: >-
                  The payment was [charged
                  back](https://docs.adyen.com/risk-management/disputes-api/dispute-notifications#chargeback),
                  and the funds were deducted from your account.
                operationId: post-CHARGEBACK
                x-sortIndex: 0
                x-methodName: paymentChargedBack
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        chargeback:
                          $ref: '#/components/examples/post-CHARGEBACK-chargeback'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          chargeback:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /CHARGEBACK_REVERSED:
              post:
                tags:
                  - Dispute
                summary: Chargeback successfully defended
                description: >-
                  The chargeback was successfully
                  [defended](https://docs.adyen.com/risk-management/understanding-disputes/defense-requirements)
                  towards the issuing bank. This stage is not final. If the
                  issuing bank presents a second chargeback, you can still lose
                  the chargeback case.
                operationId: post-CHARGEBACK_REVERSED
                x-sortIndex: 0
                x-methodName: chargebackSuccessfullyDefended
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        chargeback_reversed:
                          $ref: >-
                            #/components/examples/post-CHARGEBACK_REVERSED-chargeback_reversed
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          chargeback_reversed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /EXPIRE:
              post:
                tags:
                  - Standard
                summary: Authorisation expired
                description: The remaining uncaptured amount expired
                operationId: post-EXPIRE
                x-sortIndex: 0
                x-methodName: authorisationExpired
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        expire:
                          $ref: '#/components/examples/post-EXPIRE-expire'
                      schema:
                        $ref: '#/components/schemas/ExpireNotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          expire:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /MANUAL_REVIEW_ACCEPT:
              post:
                tags:
                  - Additional configuration
                summary: Manual review accepted
                description: >-
                  The [manual
                  review](https://docs.adyen.com/risk-management/case-management)
                  was accepted.
                operationId: post-MANUAL_REVIEW_ACCEPT
                x-sortIndex: 0
                x-methodName: manualReviewAccepted
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        manual_review_accept:
                          $ref: >-
                            #/components/examples/post-MANUAL_REVIEW_ACCEPT-manual_review_accept
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          manual_review_accept:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /MANUAL_REVIEW_REJECT:
              post:
                tags:
                  - Additional configuration
                summary: Manual review rejected
                description: >-
                  The [manual
                  review](https://docs.adyen.com/risk-management/case-management)
                  was rejected.
                operationId: post-MANUAL_REVIEW_REJECT
                x-sortIndex: 0
                x-methodName: manualReviewRejected
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        manual_review_reject:
                          $ref: >-
                            #/components/examples/post-MANUAL_REVIEW_REJECT-manual_review_reject
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          manual_review_reject:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /NOTIFICATION_OF_CHARGEBACK:
              post:
                tags:
                  - Dispute
                summary: Dispute process opened
                description: >-
                  The [dispute
                  process](https://docs.adyen.com/risk-management/understanding-disputes/dispute-process-and-flow#dispute-process)
                  was opened. You should investigate the dispute and [supply the
                  defense
                  documents](https://docs.adyen.com/risk-management/disputes-api#supply-dispute-defense-documents).
                operationId: post-NOTIFICATION_OF_CHARGEBACK
                x-sortIndex: 0
                x-methodName: disputeProcessOpened
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        notification_of_chargeback:
                          $ref: >-
                            #/components/examples/post-NOTIFICATION_OF_CHARGEBACK-notification_of_chargeback
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          notification_of_chargeback:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /NOTIFICATION_OF_FRAUD:
              post:
                tags:
                  - Dispute
                summary: Issuer sent fraud alert notification
                description: >-
                  The issuer sent a [fraud alert
                  notification](https://docs.adyen.com/risk-management/understanding-disputes/dispute-process-and-flow#dispute-process)
                  to schemes and to processors. Visa calls them TC40 and
                  Mastercard calls them System to Avoid Fraud Effectively
                  (SAFE). These are informational notifications from Adyen,
                  providing you the opportunity to take action, such as blocking
                  a shopper or issuing a refund before a chargeback happens.
                operationId: post-NOTIFICATION_OF_FRAUD
                x-sortIndex: 0
                x-methodName: issuerSentFraudAlertNotification
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        notification_of_fraud:
                          $ref: >-
                            #/components/examples/post-NOTIFICATION_OF_FRAUD-notification_of_fraud
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          notification_of_fraud:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /OFFER_CLOSED:
              post:
                tags:
                  - Additional configuration
                summary: Offer expired
                description: >-
                  The offer expired, for example, because the shopper abandoned
                  the session. For cards, offers expire after 12 hours by
                  default.
                operationId: post-OFFER_CLOSED
                x-sortIndex: 0
                x-methodName: offerExpired
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        offer_closed:
                          $ref: '#/components/examples/post-OFFER_CLOSED-offer_closed'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          offer_closed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ORDER_CLOSED:
              post:
                tags:
                  - Standard
                summary: Result of last partial payment for order
                description: >-
                  The result of the last [partial
                  payment](https://docs.adyen.com/online-payments/partial-payments)
                  for the order.
                operationId: post-ORDER_CLOSED
                x-sortIndex: 0
                x-methodName: resultOfLastPartialPaymentForOrder
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        order_closed:
                          $ref: '#/components/examples/post-ORDER_CLOSED-order_closed'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          order_closed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /ORDER_OPENED:
              post:
                tags:
                  - Standard
                summary: First partial payment request for order
                description: >-
                  The first [partial
                  payment](https://docs.adyen.com/online-payments/partial-payments)
                  was made, and the order was created.
                operationId: post-ORDER_OPENED
                x-sortIndex: 0
                x-methodName: firstPartialPaymentRequestForOrder
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        order_opened:
                          $ref: '#/components/examples/post-ORDER_OPENED-order_opened'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          order_opened:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PAIDOUT_REVERSED:
              post:
                tags:
                  - Payout
                summary: Financial institution rejected payout
                description: >-
                  The financial institution [rejected the
                  payout](https://docs.adyen.com/online-payments/online-payouts/payout-notifications).
                  We will return the funds back to your account. 

                  The reason field contains the bank statement description if
                  present.
                operationId: post-PAIDOUT_REVERSED
                x-sortIndex: 0
                x-methodName: financialInstitutionRejectedPayout
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        paidout_reversed:
                          $ref: >-
                            #/components/examples/post-PAIDOUT_REVERSED-paidout_reversed
                      schema:
                        $ref: >-
                          #/components/schemas/PaidoutReversedNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          paidout_reversed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PAYOUT_DECLINE:
              post:
                tags:
                  - Payout
                summary: Payout declined
                description: >-
                  The [payout was
                  declined](https://docs.adyen.com/online-payments/online-payouts/confirm-or-decline-payout).
                operationId: post-PAYOUT_DECLINE
                x-sortIndex: 0
                x-methodName: payoutDeclined
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        payout_decline:
                          $ref: >-
                            #/components/examples/post-PAYOUT_DECLINE-payout_decline
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          payout_decline:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PAYOUT_EXPIRE:
              post:
                tags:
                  - Payout
                summary: Payout expired
                description: >-
                  The [payout
                  expired](https://docs.adyen.com/online-payments/online-payouts/payout-notifications).
                operationId: post-PAYOUT_EXPIRE
                x-sortIndex: 0
                x-methodName: payoutExpired
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        payout_expire:
                          $ref: >-
                            #/components/examples/post-PAYOUT_EXPIRE-payout_expire
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          payout_expire:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PAYOUT_THIRDPARTY:
              post:
                tags:
                  - Payout
                summary: Result of payout request
                description: >-
                  The result of the [payout
                  request](https://docs.adyen.com/online-payments/online-payouts).
                operationId: post-PAYOUT_THIRDPARTY
                x-sortIndex: 0
                x-methodName: resultOfPayoutRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        payout_thirdparty:
                          $ref: >-
                            #/components/examples/post-PAYOUT_THIRDPARTY-payout_thirdparty
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          payout_thirdparty:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /POSTPONED_REFUND:
              post:
                tags:
                  - Additional configuration
                summary: Refund postponed until after payment capture
                description: >-
                  The refund was postponed until after [payment
                  capture](https://docs.adyen.com/online-payments/capture). To
                  enable this notification, contact our [Support
                  Team](https://www.adyen.help/hc/en-us/requests/new).
                operationId: post-POSTPONED_REFUND
                x-sortIndex: 0
                x-methodName: refundPostponedUntilAfterPaymentCapture
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        postponed_refund:
                          $ref: >-
                            #/components/examples/post-POSTPONED_REFUND-postponed_refund
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          postponed_refund:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PREARBITRATION_LOST:
              post:
                tags:
                  - Dispute
                summary: Cardholder's bank declined pre-arbitration case
                description: >-
                  The cardholder's bank declined the
                  [pre-arbitration](https://docs.adyen.com/risk-management/understanding-disputes/dispute-process-and-flow#dispute-process)
                  case.
                operationId: post-PREARBITRATION_LOST
                x-sortIndex: 0
                x-methodName: cardholdersBankDeclinedPrearbitrationCase
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        prearbitration_lost:
                          $ref: >-
                            #/components/examples/post-PREARBITRATION_LOST-prearbitration_lost
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          prearbitration_lost:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /PREARBITRATION_WON:
              post:
                tags:
                  - Dispute
                summary: Cardholder's bank accepted pre-arbitration case
                description: >-
                  The cardholder's bank accepted the
                  [pre-arbitration](https://docs.adyen.com/risk-management/understanding-disputes/dispute-process-and-flow#dispute-process)
                  case.
                operationId: post-PREARBITRATION_WON
                x-sortIndex: 0
                x-methodName: cardholdersBankAcceptedPrearbitrationCase
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        prearbitration_won:
                          $ref: >-
                            #/components/examples/post-PREARBITRATION_WON-prearbitration_won
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          prearbitration_won:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /RECURRING_CONTRACT:
              post:
                tags:
                  - Additional configuration
                summary: Recurring contract created
                description: >-
                  A recurring contract has been created. [Enable this
                  webhook](https://docs.adyen.com/development-resources/webhooks/webhook-types#non-default-event-codes)
                  in your Customer Area.
                operationId: post-RECURRING_CONTRACT
                x-sortIndex: 0
                x-methodName: recurringContractCreated
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        recurring_contract:
                          $ref: >-
                            #/components/examples/post-RECURRING_CONTRACT-recurring_contract
                      schema:
                        $ref: >-
                          #/components/schemas/RecurringContractNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          recurring_contract:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REFUND:
              post:
                tags:
                  - Standard
                summary: Result of refund request
                description: >-
                  The result of the request to [refund a
                  payment](https://docs.adyen.com/online-payments/refund).
                operationId: post-REFUND
                x-sortIndex: 0
                x-methodName: resultOfRefundRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        refund:
                          $ref: '#/components/examples/post-REFUND-refund'
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          refund:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REFUNDED_REVERSED:
              post:
                tags:
                  - Standard
                summary: Refunded amount reversed
                description: >-
                  The refunded amount was
                  [reversed](https://docs.adyen.com/online-payments/refund#refunded-reversed)
                  and returned to your bank account.
                operationId: post-REFUNDED_REVERSED
                x-sortIndex: 0
                x-methodName: refundedAmountReversed
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        refunded_reversed:
                          $ref: >-
                            #/components/examples/post-REFUNDED_REVERSED-refunded_reversed
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          refunded_reversed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REFUND_FAILED:
              post:
                tags:
                  - Standard
                summary: Refund failed due to scheme rejection
                description: >-
                  The refund [failed due to rejection by the card
                  scheme](https://docs.adyen.com/online-payments/refund#refund-failed).
                operationId: post-REFUND_FAILED
                x-sortIndex: 0
                x-methodName: refundFailedDueToSchemeRejection
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        refund_failed:
                          $ref: >-
                            #/components/examples/post-REFUND_FAILED-refund_failed
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          refund_failed:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REFUND_WITH_DATA:
              post:
                tags:
                  - Standard
                summary: Result of refund request with data
                description: >-
                  The result of the request to [refund with
                  data](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/refund#unreferenced-refund).
                operationId: post-REFUND_WITH_DATA
                x-sortIndex: 0
                x-methodName: resultOfRefundRequestWithData
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        refund_with_data:
                          $ref: >-
                            #/components/examples/post-REFUND_WITH_DATA-refund_with_data
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          refund_with_data:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REPORT_AVAILABLE:
              post:
                tags:
                  - Standard
                summary: Report available
                description: The report is generated and ready to be downloaded.
                operationId: post-REPORT_AVAILABLE
                x-sortIndex: 0
                x-methodName: reportAvailable
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        report_available:
                          $ref: >-
                            #/components/examples/post-REPORT_AVAILABLE-report_available
                      schema:
                        $ref: >-
                          #/components/schemas/ReportAvailableNotificationRequest
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          report_available:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /REQUEST_FOR_INFORMATION:
              post:
                tags:
                  - Dispute
                summary: Issuer opened Request for Information (RFI)
                description: >-
                  The issuer opened a [Request for Information
                  (RFI)](https://docs.adyen.com/risk-management/understanding-disputes/dispute-process-and-flow#dispute-process).
                  You should [supply defense
                  documents](https://docs.adyen.com/risk-management/disputes-api#supply-dispute-defense-documents)
                  to help shopper understand the charge.
                operationId: post-REQUEST_FOR_INFORMATION
                x-sortIndex: 0
                x-methodName: issuerOpenedRequestForInformationrfi
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        request_for_information:
                          $ref: >-
                            #/components/examples/post-REQUEST_FOR_INFORMATION-request_for_information
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          request_for_information:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /SECOND_CHARGEBACK:
              post:
                tags:
                  - Dispute
                summary: Issuing bank declined chargeback defense
                description: >-
                  The issuing bank declined the material submitted during
                  [defense of the original
                  chargeback](https://docs.adyen.com/risk-management/understanding-disputes/defense-requirements).
                  The disputed amount is deducted from your account.
                operationId: post-SECOND_CHARGEBACK
                x-sortIndex: 0
                x-methodName: issuingBankDeclinedChargebackDefense
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        second_chargeback:
                          $ref: >-
                            #/components/examples/post-SECOND_CHARGEBACK-second_chargeback
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          second_chargeback:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /TECHNICAL_CANCEL:
              post:
                tags:
                  - Standard
                summary: Result of technical cancel request
                description: >-
                  The result of the [technical
                  cancel](https://docs.adyen.com/online-payments/cancel#technical-cancel-webhook)
                  request.
                operationId: post-TECHNICAL_CANCEL
                x-sortIndex: 0
                x-methodName: resultOfTechnicalCancelRequest
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        technical_cancel:
                          $ref: >-
                            #/components/examples/post-TECHNICAL_CANCEL-technical_cancel
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          technical_cancel:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeeded.
            /VOID_PENDING_REFUND:
              post:
                tags:
                  - Standard
                summary: Result of request to cancel POS refund
                description: >-
                  The result of the request to [cancel a POS
                  refund](https://docs.adyen.com/point-of-sale/refund-payment/cancel-a-pos-refund-request).
                operationId: post-VOID_PENDING_REFUND
                x-sortIndex: 0
                x-methodName: resultOfRequestToCancelPosRefund
                security:
                  - BasicAuth: []
                requestBody:
                  content:
                    application/json:
                      examples:
                        void_pending_refund:
                          $ref: >-
                            #/components/examples/post-VOID_PENDING_REFUND-void_pending_refund
                      schema:
                        $ref: '#/components/schemas/NotificationRequest'
                responses:
                  '200':
                    content:
                      application/json:
                        examples:
                          void_pending_refund:
                            $ref: '#/components/examples/WebhookAck'
                        schema:
                          $ref: '#/components/schemas/NotificationResponse'
                    description: OK - the request has succeede
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-contact-email-error
              message: Contact Email
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-tags-object-info
              message: Tag Object
            - code: openapi-tags-description-error
              message: Tag Descriptions
            - code: openapi-tags-name-info
              message: Tag Name
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-names-snake-case-error
              message: Schema Property Names Snake Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-casing-info
              message: Schema Property Enum Casing
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/webhooks-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/webhooks-openapi-api-evangelist-ratings.yml
    aid: adyen:adyen-webhooks-api
common:
  - type: Terms of Service
    url: https://www.adyen.com/legal/terms-and-conditions
  - type: Authentication
    url: https://www.adyen.com/authentication-3d-secure
  - type: Plans
    url: https://www.adyen.com/pricing
  - type: Documentation
    url: https://docs.adyen.com/
  - type: Newsletter
    url: https://www.adyen.com/newsletter
  - type: Knowledge
    url: https://www.adyen.com/knowledge-hub
  - type: Login
    url: https://authn-live.adyen.com/authn/ui/login
  - type: Support
    url: https://help.adyen.com/en_US
  - type: Contact
    url: https://help.adyen.com/en_US/contact
  - type: Webinars
    url: https://help.adyen.com/en_US/academy/webinars
  - type: Privacy
    url: https://www.adyen.com/policies-and-disclaimer/privacy-policy
  - type: OpenAPI
    url: https://github.com/Adyen/adyen-openapi
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
aid: adyen
---