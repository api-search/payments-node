---
specificationVersion: '0.17'
aid: stripe
name: Stripe
description: >-
  Millions of companies of all sizes use Stripe online and in person to accept
  payments, send payouts, automate financial processes, and ultimately grow
  revenue.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://artisinal.apisjson.org/apis/stripe/apis.yml
created: 2023/10/06
modified: '2024-03-09'
tags: []
apis:
  - aid: stripe:stripe-accounts-api
    name: Stripe Accounts API
    description: >-
      This is an object representing a Stripe account. You can retrieve it to
      see properties on the account like its current requirements or if the
      account is enabled to make live charges or receive payouts.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/accounts
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/accounts
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Accounts API
          paths:
            /v1/account:
              get:
                description: <p>Retrieves the details of an account.</p>
                tags:
                  - V1
                  - Account
            /v1/account_links:
              post:
                description: >-
                  <p>Creates an AccountLink object that includes a single-use
                  Stripe URL that the platform can redirect their user to in
                  order to take them through the Connect Onboarding flow.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
            /v1/account_sessions:
              post:
                description: >-
                  <p>Creates a AccountSession object that includes a single-use
                  token that the platform can use on their front-end to grant
                  client-side API access.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
            /v1/accounts:
              get:
                description: >-
                  <p>Returns a list of accounts connected to your platform via
                  <a href="/docs/connect">Connect</a>. If you’re not a platform,
                  the list is empty.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
              post:
                description: >-
                  <p>With <a href="/docs/connect">Connect</a>, you can create
                  Stripe accounts for your users.

                  To do this, you’ll first need to <a
                  href="https://dashboard.stripe.com/account/applications/settings">register
                  your platform</a>.</p>


                  <p>If you’ve already collected information for your connected
                  accounts, you <a
                  href="/docs/connect/best-practices#onboarding">can prefill
                  that information</a> when

                  creating the account. Connect Onboarding won’t ask for the
                  prefilled information during account onboarding.

                  You can prefill any information on the account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
            /v1/accounts/{account}:
              delete:
                description: >-
                  <p>With <a href="/docs/connect">Connect</a>, you can delete
                  accounts you manage.</p>


                  <p>Accounts created using test-mode keys can be deleted at any
                  time. Standard accounts created using live-mode keys cannot be
                  deleted. Custom or Express accounts created using live-mode
                  keys can only be deleted once all balances are zero.</p>


                  <p>If you want to delete your own account, use the <a
                  href="https://dashboard.stripe.com/settings/account">account
                  information tab in your account settings</a> instead.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
              get:
                description: <p>Retrieves the details of an account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
              post:
                description: >-
                  <p>Updates a <a href="/docs/connect/accounts">connected
                  account</a> by setting the values of the parameters passed.
                  Any parameters not provided are

                  left unchanged.</p>


                  <p>For Custom accounts, you can update any information on the
                  account. For other accounts, you can update all information
                  until that

                  account has started to go through Connect Onboarding. Once you
                  create an <a href="/docs/api/account_links">Account Link</a>

                  for a Standard or Express account, some parameters can no
                  longer be changed. These are marked as <strong>Custom
                  Only</strong> or <strong>Custom and Express</strong>

                  below.</p>


                  <p>To update your own account, use the <a
                  href="https://dashboard.stripe.com/settings/account">Dashboard</a>.
                  Refer to our

                  <a href="/docs/connect/updating-accounts">Connect</a>
                  documentation to learn more about updating accounts.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
            /v1/accounts/{account}/bank_accounts:
              post:
                description: <p>Create an external account for a given account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
            /v1/accounts/{account}/bank_accounts/{id}:
              delete:
                description: >-
                  <p>Delete a specified external account for a given
                  account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
              get:
                description: >-
                  <p>Retrieve a specified external account for a given
                  account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
              post:
                description: >-
                  <p>Updates the metadata, account holder name, account holder
                  type of a bank account belonging to a <a
                  href="/docs/connect/custom-accounts">Custom account</a>, and
                  optionally sets it as the default for its currency. Other bank
                  account details are not editable by design.</p>


                  <p>You can re-enable a disabled bank account by performing an
                  update call without providing any arguments or changes.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
            /v1/accounts/{account}/capabilities:
              get:
                description: >-
                  <p>Returns a list of capabilities associated with the account.
                  The capabilities are returned sorted by creation date, with
                  the most recent capability appearing first.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
            /v1/accounts/{account}/capabilities/{capability}:
              get:
                description: >-
                  <p>Retrieves information about the specified Account
                  Capability.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
              post:
                description: >-
                  <p>Updates an existing Account Capability. Request or remove a
                  capability by updating its <code>requested</code>
                  parameter.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
            /v1/accounts/{account}/external_accounts:
              get:
                description: <p>List external accounts for an account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
              post:
                description: <p>Create an external account for a given account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
            /v1/accounts/{account}/external_accounts/{id}:
              delete:
                description: >-
                  <p>Delete a specified external account for a given
                  account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
              get:
                description: >-
                  <p>Retrieve a specified external account for a given
                  account.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
              post:
                description: >-
                  <p>Updates the metadata, account holder name, account holder
                  type of a bank account belonging to a <a
                  href="/docs/connect/custom-accounts">Custom account</a>, and
                  optionally sets it as the default for its currency. Other bank
                  account details are not editable by design.</p>


                  <p>You can re-enable a disabled bank account by performing an
                  update call without providing any arguments or changes.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
            /v1/accounts/{account}/login_links:
              post:
                description: >-
                  <p>Creates a single-use login link for an Express account to
                  access their Stripe dashboard.</p>


                  <p><strong>You may only create login links for <a
                  href="/docs/connect/express-accounts">Express accounts</a>
                  connected to your platform</strong>.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
            /v1/accounts/{account}/people:
              get:
                description: >-
                  <p>Returns a list of people associated with the account’s
                  legal entity. The people are returned sorted by creation date,
                  with the most recent people appearing first.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
              post:
                description: <p>Creates a new person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
            /v1/accounts/{account}/people/{person}:
              delete:
                description: >-
                  <p>Deletes an existing person’s relationship to the account’s
                  legal entity. Any person with a relationship for an account
                  can be deleted through the API, except if the person is the
                  <code>account_opener</code>. If your integration is using the
                  <code>executive</code> parameter, you cannot delete the only
                  verified <code>executive</code> on file.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
              get:
                description: <p>Retrieves an existing person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
              post:
                description: <p>Updates an existing person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
            /v1/accounts/{account}/persons:
              get:
                description: >-
                  <p>Returns a list of people associated with the account’s
                  legal entity. The people are returned sorted by creation date,
                  with the most recent people appearing first.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
              post:
                description: <p>Creates a new person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
            /v1/accounts/{account}/persons/{person}:
              delete:
                description: >-
                  <p>Deletes an existing person’s relationship to the account’s
                  legal entity. Any person with a relationship for an account
                  can be deleted through the API, except if the person is the
                  <code>account_opener</code>. If your integration is using the
                  <code>executive</code> parameter, you cannot delete the only
                  verified <code>executive</code> on file.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
              get:
                description: <p>Retrieves an existing person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
              post:
                description: <p>Updates an existing person.</p>
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
            /v1/accounts/{account}/reject:
              post:
                description: >-
                  <p>With <a href="/docs/connect">Connect</a>, you may flag
                  accounts as suspicious.</p>


                  <p>Test-mode Custom and Express accounts can be rejected at
                  any time. Accounts created using live-mode keys may only be
                  rejected once all balances are
                tags:
                  - V1
                  - Account
                  - Account_links
                  - Account_sessions
                  - Accounts
                  - Bank_accounts
                  - Id
                  - Capabilities
                  - Capability
                  - External_accounts
                  - Login_links
                  - People
                  - Person
                  - Persons
                  - Reje
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-response-get-200-schema-components-warn
              message: GET Response 200 Schema Components
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: invalid-ref
              message: '''#/components/schemas/account_business_profile'' does not exist'
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/accounts-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/accounts-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-apple-pay-api
    name: Stripe Apple Pay API
    description: >-
      Stripe users can accept Apple Pay in iOS applications in iOS 9 and above,
      and on the web in Safari starting with iOS 10 or macOS Sierra. There are
      no additional fees to process Apple Pay payments, and the pricing is the
      same as other card transactions.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/apple-pay
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/apple-pay
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Apple Pay API
          paths:
            /v1/apple_pay/domains:
              get:
                description: <p>List apple pay domains.</p>
                tags:
                  - V1
                  - Apple_pay
                  - Domains
              post:
                description: <p>Create an apple pay domain.</p>
                tags:
                  - V1
                  - Apple_pay
                  - Domains
            /v1/apple_pay/domains/{domain}:
              delete:
                description: <p>Delete an apple pay domain.</p>
                tags:
                  - V1
                  - Apple_pay
                  - Domains
                  - Domain
              get:
                description: <p>Retrieve an apple pay d
                tags:
                  - V1
                  - Apple_pay
                  - Domains
                  - Doma
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/apple-pay-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/apple-pay-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-application-fees-api
    name: Stripe Application Fees API
    description: >-
      When you collect a transaction fee on top of a charge made for your user
      (using Connect), an Application Fee object is created in your account. You
      can list, retrieve, and refund application fees.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/application_fees
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/application_fees
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Application Fees API
          paths:
            /v1/application_fees:
              get:
                description: >-
                  <p>Returns a list of application fees you’ve previously
                  collected. The application fees are returned in sorted order,
                  with the most recent fees appearing first.</p>
                tags:
                  - V1
                  - Application_fees
            /v1/application_fees/{fee}/refunds/{id}:
              get:
                description: >-
                  <p>By default, you can see the 10 most recent refunds stored
                  directly on the application fee object, but you can also
                  retrieve details about a specific refund stored on the
                  application fee.</p>
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
              post:
                description: >-
                  <p>Updates the specified application fee refund by setting the
                  values of the parameters passed. Any parameters not provided
                  will be left unchanged.</p>


                  <p>This request only accepts metadata as an argument.</p>
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
            /v1/application_fees/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an application fee that your
                  account has collected. The same information is returned when
                  refunding the application fee.</p>
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
            /v1/application_fees/{id}/refund:
              post:
                description: ''
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
                  - Refund
            /v1/application_fees/{id}/refunds:
              get:
                description: >-
                  <p>You can see a list of the refunds belonging to a specific
                  application fee. Note that the 10 most recent refunds are
                  always available by default on the application fee object. If
                  you need more than those 10, you can use this API method and
                  the <code>limit</code> and <code>starting_after</code>
                  parameters to page through additional refunds.</p>
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
                  - Refund
              post:
                description: >-
                  <p>Refunds an application fee that has previously been
                  collected but not yet refunded.

                  Funds will be refunded to the Stripe account from which the
                  fee was originally collected.</p>


                  <p>You can optionally refund only part of an application fee.

                  You can do so multiple times, until the entire fee has been
                  refunded.</p>


                  <p>Once entirely refunded, an application fee can’t be
                  refunded again.

                  This method will raise an error when called on an
                  already-refunded application fee,

                  or when trying to refund more money than is left on an
                  applicatio
                tags:
                  - V1
                  - Application_fees
                  - Fee
                  - Refunds
                  - Id
                  - Refu
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-operations-description-error
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/application-fees-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/application-fees-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-application-secrets-api
    name: Stripe Application Secrets API
    description: >-
      Secret Store is an API that allows Stripe Apps developers to securely
      persist secrets for use by UI Extensions and app backends.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/secret_management
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/secret_management
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Application Secrets API
          paths:
            /v1/apps/secrets:
              get:
                description: <p>List all secrets stored on the given scope.</p>
                tags:
                  - V1
                  - Apps
                  - Secrets
              post:
                description: <p>Create or replace a secret in the secret store.</p>
                tags:
                  - V1
                  - Apps
                  - Secrets
            /v1/apps/secrets/delete:
              post:
                description: >-
                  <p>Deletes a secret from the secret store by name and
                  scope.</p>
                tags:
                  - V1
                  - Apps
                  - Secrets
                  - Delete
            /v1/apps/secrets/find:
              get:
                description: <p>Finds a secret in the secret store by name and
                tags:
                  - V1
                  - Apps
                  - Secrets
                  - Delete
                  - Fi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/application-secrets-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/application-secrets-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-balance-api
    name: Stripe Balance API
    description: >-
      This is an object representing your Stripe balance. You can retrieve it to
      see the balance currently on your Stripe account. You can also retrieve
      the balance history, which contains a list of transactions that
      contributed to the balance (charges, payouts, and so forth).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/balance
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/balance
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Balance API
          paths:
            /v1/balance:
              get:
                description: >-
                  <p>Retrieves the current account balance, based on the
                  authentication that was used to make the request.
                   For a sample request, see <a href="/docs/connect/account-balances#accounting-for-negative-balances">Accounting for negative balances</a>.</p>
                tags:
                  - V1
                  - Balance
            /v1/balance/history:
              get:
                description: >-
                  <p>Returns a list of transactions that have contributed to the
                  Stripe account balance (e.g., charges, transfers, and so
                  forth). The transactions are returned in sorted order, with
                  the most recent transactions appearing first.</p>


                  <p>Note that this endpoint was previously called “Balance
                  history” and used the path
                  <code>/v1/balance/history</code>.</p>
                tags:
                  - V1
                  - Balance
                  - History
            /v1/balance/history/{id}:
              get:
                description: >-
                  <p>Retrieves the balance transaction with the given ID.</p>


                  <p>Note that this endpoint previously used the path
                  <code>/v1/balance/history/:id</code>.</p>
                tags:
                  - V1
                  - Balance
                  - History
                  - Id
            /v1/balance_transactions:
              get:
                description: >-
                  <p>Returns a list of transactions that have contributed to the
                  Stripe account balance (e.g., charges, transfers, and so
                  forth). The transactions are returned in sorted order, with
                  the most recent transactions appearing first.</p>


                  <p>Note that this endpoint was previously called “Balance
                  history” and used the path
                  <code>/v1/balance/history</code>.</p>
                tags:
                  - V1
                  - Balance
                  - History
                  - Id
                  - Balance_transactions
            /v1/balance_transactions/{id}:
              get:
                description: >-
                  <p>Retrieves the balance transaction with the given ID.</p>


                  <p>Note that this endpoint previously used the path
                  <code>/v1/balance/history/:id</
                tags:
                  - V1
                  - Balance
                  - History
                  - Id
                  - Balance_transactio
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
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
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: invalid-ref
              message: '''#/components/schemas/balance_amount'' does not exist'
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/balance-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/balance-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-billing-api
    name: Stripe Billing API
    description: >-
      Create and manage subscriptions, recurring payments, and recurring
      revenue.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/billing
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/billing
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Billing API
          paths:
            /v1/billing_portal/configurations:
              get:
                description: >-
                  <p>Returns a list of configurations that describe the
                  functionality of the customer portal.</p>
                tags:
                  - V1
                  - Billing_portal
                  - Configurations
              post:
                description: >-
                  <p>Creates a configuration that describes the functionality
                  and behavior of a PortalSession</p>
                tags:
                  - V1
                  - Billing_portal
                  - Configurations
            /v1/billing_portal/configurations/{configuration}:
              get:
                description: >-
                  <p>Retrieves a configuration that describes the functionality
                  of the customer portal.</p>
                tags:
                  - V1
                  - Billing_portal
                  - Configurations
                  - Configuration
              post:
                description: >-
                  <p>Updates a configuration that describes the functionality of
                  the customer portal.</p>
                tags:
                  - V1
                  - Billing_portal
                  - Configurations
                  - Configuration
            /v1/billing_portal/sessions:
              post:
                description: <p>Creates a session of the customer p
                tags:
                  - V1
                  - Billing_portal
                  - Configurations
                  - Configuration
                  - Sessio
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/billing-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/billing-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-charges-api
    name: Stripe Charges API
    description: >-
      The Charge object represents a single attempt to move money into your
      Stripe account. PaymentIntent confirmation is the most common way to
      create Charges, but transferring money to a different Stripe account
      through Connect also creates Charges. Some legacy payment flows create
      Charges directly, which is not recommended for new integrations.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/charges
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/charges
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Charges API
          paths:
            /v1/charges:
              get:
                description: >-
                  <p>Returns a list of charges you’ve previously created. The
                  charges are returned in sorted order, with the most recent
                  charges appearing first.</p>
                tags:
                  - V1
                  - Charges
              post:
                description: >-
                  <p>Use the <a href="/docs/api/payment_intents">Payment Intents
                  API</a> to initiate a new payment instead

                  of using this method. Confirmation of the PaymentIntent
                  creates the <code>Charge</code>

                  object used to request payment, so this method is limited to
                  legacy integrations.</p>
                tags:
                  - V1
                  - Charges
            /v1/charges/search:
              get:
                description: >-
                  <p>Search for charges you’ve previously created using Stripe’s
                  <a href="/docs/search#search-query-language">Search Query
                  Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Charges
                  - Search
            /v1/charges/{charge}:
              get:
                description: >-
                  <p>Retrieves the details of a charge that has previously been
                  created. Supply the unique charge ID that was returned from
                  your previous request, and Stripe will return the
                  corresponding charge information. The same information is
                  returned when creating or refunding the charge.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
              post:
                description: >-
                  <p>Updates the specified charge by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unchanged.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
            /v1/charges/{charge}/capture:
              post:
                description: >-
                  <p>Capture the payment of an existing, uncaptured charge that
                  was created with the <code>capture</code> option set to
                  false.</p>


                  <p>Uncaptured payments expire a set number of days after they
                  are created (<a href="/docs/charges/placing-a-hold">7 by
                  default</a>), after which they are marked as refunded and
                  capture attempts will fail.</p>


                  <p>Don’t use this method to capture a PaymentIntent-initiated
                  charge. Use <a
                  href="/docs/api/payment_intents/capture">Capture a
                  PaymentIntent</a>.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
            /v1/charges/{charge}/dispute:
              get:
                description: <p>Retrieve a dispute for a specified charge.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
              post:
                description: ''
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
            /v1/charges/{charge}/dispute/close:
              post:
                description: ''
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
            /v1/charges/{charge}/refund:
              post:
                description: >-
                  <p>When you create a new refund, you must specify either a
                  Charge or a PaymentIntent object.</p>


                  <p>This action refunds a previously created charge that’s not
                  refunded yet.

                  Funds are refunded to the credit or debit card that’s
                  originally charged.</p>


                  <p>You can optionally refund only part of a charge.

                  You can repeat this until the entire charge is refunded.</p>


                  <p>After you entirely refund a charge, you can’t refund it
                  again.

                  This method raises an error when it’s called on an
                  already-refunded charge,

                  or when you attempt to refund more money than is left on a
                  charge.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
                  - Refund
            /v1/charges/{charge}/refunds:
              get:
                description: >-
                  <p>You can see a list of the refunds belonging to a specific
                  charge. Note that the 10 most recent refunds are always
                  available by default on the charge object. If you need more
                  than those 10, you can use this API method and the
                  <code>limit</code> and <code>starting_after</code> parameters
                  to page through additional refunds.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
                  - Refund
                  - Refunds
              post:
                description: >-
                  <p>When you create a new refund, you must specify a Charge or
                  a PaymentIntent object on which to create it.</p>


                  <p>Creating a new refund will refund a charge that has
                  previously been created but not yet refunded.

                  Funds will be refunded to the credit or debit card that was
                  originally charged.</p>


                  <p>You can optionally refund only part of a charge.

                  You can do so multiple times, until the entire charge has been
                  refunded.</p>


                  <p>Once entirely refunded, a charge can’t be refunded again.

                  This method will raise an error when called on an
                  already-refunded charge,

                  or when trying to refund more money than is left on a
                  charge.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
                  - Refund
                  - Refunds
            /v1/charges/{charge}/refunds/{refund}:
              get:
                description: <p>Retrieves the details of an existing refund.</p>
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
                  - Refund
                  - Refunds
              post:
                description: <p>Update a specified r
                tags:
                  - V1
                  - Charges
                  - Search
                  - Charge
                  - Capture
                  - Dispute
                  - Close
                  - Refund
                  - Refun
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-operations-description-error
              message: Operation Description
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/charges-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/charges-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-checkout-api
    name: Stripe Checkout API
    description: >-
      Checkout is a low-code payment integration that creates a customizable
      form for collecting payments. You can embed Checkout directly in your
      website or redirect customers to a Stripe-hosted payment page. It supports
      one-time payments and subscriptions and accepts over 40 local payment
      methods.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/payments/checkout
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/payments/checkout
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Checkout API
          paths:
            /v1/checkout/sessions:
              get:
                description: <p>Returns a list of Checkout Sessions.</p>
                tags:
                  - V1
                  - Checkout
                  - Sessions
              post:
                description: <p>Creates a Session object.</p>
                tags:
                  - V1
                  - Checkout
                  - Sessions
            /v1/checkout/sessions/{session}:
              get:
                description: <p>Retrieves a Session object.</p>
                tags:
                  - V1
                  - Checkout
                  - Sessions
                  - Session
            /v1/checkout/sessions/{session}/expire:
              post:
                description: >-
                  <p>A Session can be expired when it is in one of these
                  statuses: <code>open</code> </p>


                  <p>After it expires, a customer can’t complete a Session and
                  customers loading the Session see a message saying the Session
                  is expired.</p>
                tags:
                  - V1
                  - Checkout
                  - Sessions
                  - Session
                  - Expire
            /v1/checkout/sessions/{session}/line_items:
              get:
                description: >-
                  <p>When retrieving a Checkout Session, there is an includable
                  <strong>line_items</strong> property containing the first
                  handful of those items. There is also a URL where you can
                  retrieve the full (paginated) list of line 
                tags:
                  - V1
                  - Checkout
                  - Sessions
                  - Session
                  - Expire
                  - Line_ite
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/checkout-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/checkout-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-climate-api
    name: Stripe Climate API
    description: >-
      Stripe Climate is the easiest way to help promising permanent carbon
      removal technologies launch and scale. Join a growing group of ambitious
      businesses that are changing the course of carbon removal.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/climate
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/climate
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Climate API
          paths:
            /v1/climate/orders:
              get:
                description: >-
                  <p>Lists all Climate order objects. The orders are returned
                  sorted by creation date, with the

                  most recently created orders appearing first.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
              post:
                description: >-
                  <p>Creates a Climate order object for a given Climate product.
                  The order will be processed immediately

                  after creation and payment will be deducted your Stripe
                  balance.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
            /v1/climate/orders/{order}:
              get:
                description: >-
                  <p>Retrieves the details of a Climate order object with the
                  given ID.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
              post:
                description: >-
                  <p>Updates the specified order by setting the values of the
                  parameters passed.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
            /v1/climate/orders/{order}/cancel:
              post:
                description: >-
                  <p>Cancels a Climate order. You can cancel an order within 30
                  days of creation. Stripe refunds the

                  reservation <code>amount_subtotal</code>, but not the
                  <code>amount_fees</code> for user-triggered cancellations.
                  Frontier

                  might cancel reservations if suppliers fail to deliver. If
                  Frontier cancels the reservation, Stripe

                  provides 90 days advance notice and refunds the
                  <code>amount_total</code>.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
            /v1/climate/products:
              get:
                description: <p>Lists all available Climate product objects.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
            /v1/climate/products/{product}:
              get:
                description: >-
                  <p>Retrieves the details of a Climate product with the given
                  ID.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
            /v1/climate/reservations:
              get:
                description: >-
                  <p>Lists all Climate order objects. The orders are returned
                  sorted by creation date, with the

                  most recently created orders appearing first.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
              post:
                description: >-
                  <p>Creates a Climate order object for a given Climate product.
                  The order will be processed immediately

                  after creation and payment will be deducted your Stripe
                  balance.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
            /v1/climate/reservations/{order}:
              get:
                description: >-
                  <p>Retrieves the details of a Climate order object with the
                  given ID.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
              post:
                description: >-
                  <p>Updates the specified order by setting the values of the
                  parameters passed.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
            /v1/climate/reservations/{order}/cancel:
              post:
                description: >-
                  <p>Cancels a Climate order. You can cancel an order within 30
                  days of creation. Stripe refunds the

                  reservation <code>amount_subtotal</code>, but not the
                  <code>amount_fees</code> for user-triggered cancellations.
                  Frontier

                  might cancel reservations if suppliers fail to deliver. If
                  Frontier cancels the reservation, Stripe

                  provides 90 days advance notice and refunds the
                  <code>amount_total</code>.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
            /v1/climate/reservations/{order}/confirm:
              post:
                description: >-
                  <p>Confirms a Climate order. When you confirm your order, we
                  immediately deduct the funds from your

                  Stripe balance.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
                  - Confirm
            /v1/climate/suppliers:
              get:
                description: <p>Lists all available Climate supplier objects.</p>
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
                  - Confirm
                  - Suppliers
            /v1/climate/suppliers/{supplier}:
              get:
                description: <p>Retrieves a Climate supplier o
                tags:
                  - V1
                  - Climate
                  - Orders
                  - Order
                  - Cancel
                  - Products
                  - Product
                  - Reservations
                  - Confirm
                  - Suppliers
                  - Suppli
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/climate-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/climate-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-country-api
    name: Stripe Country API
    description: >-
      Stripe needs to collect certain pieces of information about each account
      created. These requirements can differ depending on the account’s country.
      The Country Specs API makes these rules available to your integration.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/country_specs
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/country_specs
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Country API
          paths:
            /v1/country_specs:
              get:
                description: <p>Lists all Country Spec objects available in the API.</p>
                tags:
                  - V1
                  - Country_specs
            /v1/country_specs/{country}:
              get:
                description: <p>Returns a Country Spec for a given Country
                tags:
                  - V1
                  - Country_specs
                  - Count
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/country-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/country-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-coupons-api
    name: Stripe Coupons API
    description: >-
      A coupon contains information about a percent-off or amount-off discount
      you might want to apply to a customer. Coupons may be applied to
      subscriptions, invoices, checkout sessions, quotes, and more. Coupons do
      not work with conventional one-off charges or payment intents.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/coupons
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/coupons
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Coupons API
          paths:
            /v1/coupons:
              get:
                description: <p>Returns a list of your coupons.</p>
                tags:
                  - V1
                  - Coupons
              post:
                description: >-
                  <p>You can create coupons easily via the <a
                  href="https://dashboard.stripe.com/coupons">coupon
                  management</a> page of the Stripe dashboard. Coupon creation
                  is also accessible via the API if you need to create coupons
                  on the fly.</p>


                  <p>A coupon has either a <code>percent_off</code> or an
                  <code>amount_off</code> and <code>currency</code>. If you set
                  an <code>amount_off</code>, that amount will be subtracted
                  from any invoice’s subtotal. For example, an invoice with a
                  subtotal of <currency>100</currency> will have a final total
                  of <currency>0</currency> if a coupon with an
                  <code>amount_off</code> of <amount>200</amount> is applied to
                  it and an invoice with a subtotal of <currency>300</currency>
                  will have a final total of <currency>100</currency> if a
                  coupon with an <code>amount_off</code> of <amount>200</amount>
                  is applied to it.</p>
                tags:
                  - V1
                  - Coupons
            /v1/coupons/{coupon}:
              delete:
                description: >-
                  <p>You can delete coupons via the <a
                  href="https://dashboard.stripe.com/coupons">coupon
                  management</a> page of the Stripe dashboard. However, deleting
                  a coupon does not affect any customers who have already
                  applied the coupon; it means that new customers can’t redeem
                  the coupon. You can also delete coupons via the API.</p>
                tags:
                  - V1
                  - Coupons
                  - Coupon
              get:
                description: <p>Retrieves the coupon with the given ID.</p>
                tags:
                  - V1
                  - Coupons
                  - Coupon
              post:
                description: >-
                  <p>Updates the metadata of a coupon. Other coupon details
                  (currency, duration, amount_off) are, by design, not edi
                tags:
                  - V1
                  - Coupons
                  - Coup
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/coupons-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/coupons-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-credit-notes-api
    name: Stripe Credit Notes API
    description: >-
      Issue a credit note to adjust an invoice’s amount after the invoice is
      finalized.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/credit_notes
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/credit_notes
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Credit Notes API
          paths:
            /v1/credit_notes:
              get:
                description: <p>Returns a list of credit notes.</p>
                tags:
                  - V1
                  - Credit_notes
              post:
                description: >-
                  <p>Issue a credit note to adjust the amount of a finalized
                  invoice. For a <code>status=open</code> invoice, a credit note
                  reduces

                  its <code>amount_due</code>. For a <code>status=paid</code>
                  invoice, a credit note does not affect its
                  <code>amount_due</code>. Instead, it can result

                  in any combination of the following:</p>


                  <ul>

                  <li>Refund: create a new refund (using
                  <code>refund_amount</code>) or link an existing refund (using
                  <code>refund</code>).</li>

                  <li>Customer balance credit: credit the customer’s balance
                  (using <code>credit_amount</code>) which will be automatically
                  applied to their next invoice when it’s finalized.</li>

                  <li>Outside of Stripe credit: record the amount that is or
                  will be credited outside of Stripe (using
                  <code>out_of_band_amount</code>).</li>

                  </ul>


                  <p>For post-payment credit notes the sum of the refund, credit
                  and outside of Stripe amounts must equal the credit note
                  total.</p>


                  <p>You may issue multiple credit notes for an invoice. Each
                  credit note will increment the invoice’s
                  <code>pre_payment_credit_notes_amount</code>

                  or <code>post_payment_credit_notes_amount</code> depending on
                  its <code>status</code> at the time of credit note
                  creation.</p>
                tags:
                  - V1
                  - Credit_notes
            /v1/credit_notes/preview:
              get:
                description: <p>Get a preview of a credit note without creating it.</p>
                tags:
                  - V1
                  - Credit_notes
                  - Preview
            /v1/credit_notes/preview/lines:
              get:
                description: >-
                  <p>When retrieving a credit note preview, you’ll get a
                  <strong>lines</strong> property containing the first handful
                  of those items. This URL you can retrieve the full (paginated)
                  list of line items.</p>
                tags:
                  - V1
                  - Credit_notes
                  - Preview
                  - Lines
            /v1/credit_notes/{credit_note}/lines:
              get:
                description: >-
                  <p>When retrieving a credit note, you’ll get a
                  <strong>lines</strong> property containing the the first
                  handful of those items. There is also a URL where you can
                  retrieve the full (paginated) list of line items.</p>
                tags:
                  - V1
                  - Credit_notes
                  - Preview
                  - Lines
                  - Credit_note
            /v1/credit_notes/{id}:
              get:
                description: >-
                  <p>Retrieves the credit note object with the given
                  identifier.</p>
                tags:
                  - V1
                  - Credit_notes
                  - Preview
                  - Lines
                  - Credit_note
                  - Id
              post:
                description: <p>Updates an existing credit note.</p>
                tags:
                  - V1
                  - Credit_notes
                  - Preview
                  - Lines
                  - Credit_note
                  - Id
            /v1/credit_notes/{id}/void:
              post:
                description: >-
                  <p>Marks a credit note as void. Learn more about <a
                  href="/docs/billing/invoices/credit-notes#voiding">voiding
                  credit note
                tags:
                  - V1
                  - Credit_notes
                  - Preview
                  - Lines
                  - Credit_note
                  - Id
                  - Vo
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/credit-notes-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/credit-notes-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-customers-api
    name: Stripe Customers API
    description: >-
      This object represents a customer of your business. Use it to create
      recurring charges and track payments that belong to the same customer.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/customers
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/customers
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Customers API
          paths:
            /v1/customers:
              get:
                description: >-
                  <p>Returns a list of your customers. The customers are
                  returned sorted by creation date, with the most recent
                  customers appearing first.</p>
                tags:
                  - V1
                  - Customers
              post:
                description: <p>Creates a new customer object.</p>
                tags:
                  - V1
                  - Customers
            /v1/customers/search:
              get:
                description: >-
                  <p>Search for customers you’ve previously created using
                  Stripe’s <a href="/docs/search#search-query-language">Search
                  Query Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Customers
                  - Search
            /v1/customers/{customer}:
              delete:
                description: >-
                  <p>Permanently deletes a customer. It cannot be undone. Also
                  immediately cancels any active subscriptions on the
                  customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
              get:
                description: <p>Retrieves a Customer object.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
              post:
                description: >-
                  <p>Updates the specified customer by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unchanged. For example, if you pass the
                  <strong>source</strong> parameter, that becomes the customer’s
                  active source (e.g., a card) to be used for all charges in the
                  future. When you update a customer to a new valid card source
                  by passing the <strong>source</strong> parameter: for each of
                  the customer’s current subscriptions, if the subscription
                  bills automatically and is in the <code>past_due</code> state,
                  then the latest open invoice for the subscription with
                  automatic collection enabled will be retried. This retry will
                  not count as an automatic retry, and will not affect the next
                  regularly scheduled payment for the invoice. Changing the
                  <strong>default_source</strong> for a customer will not
                  trigger this behavior.</p>


                  <p>This request accepts mostly the same arguments as the
                  customer creation call.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
            /v1/customers/{customer}/balance_transactions:
              get:
                description: >-
                  <p>Returns a list of transactions that updated the customer’s
                  <a href="/docs/billing/customer/balance">balances</a>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
              post:
                description: >-
                  <p>Creates an immutable transaction that updates the
                  customer’s credit <a
                  href="/docs/billing/customer/balance">balance</a>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
            /v1/customers/{customer}/balance_transactions/{transaction}:
              get:
                description: >-
                  <p>Retrieves a specific customer balance transaction that
                  updated the customer’s <a
                  href="/docs/billing/customer/balance">balances</a>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
              post:
                description: >-
                  <p>Most credit balance transaction fields are immutable, but
                  you may update its <code>description</code> and
                  <code>metadata</code>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
            /v1/customers/{customer}/bank_accounts:
              get:
                description: >-
                  <p>You can see a list of the bank accounts belonging to a
                  Customer. Note that the 10 most recent sources are always
                  available by default on the Customer. If you need more than
                  those 10, you can use this API method and the
                  <code>limit</code> and <code>starting_after</code> parameters
                  to page through additional bank accounts.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
              post:
                description: >-
                  <p>When you create a new credit card, you must specify a
                  customer or recipient on which to create it.</p>


                  <p>If the card’s owner has no default card, then the new card
                  will become the default.

                  However, if the owner already has a default, then it will not
                  change.

                  To change the default, you should <a
                  href="/docs/api#update_customer">update the customer</a> to
                  have a new <code>default_source</code>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
            /v1/customers/{customer}/bank_accounts/{id}:
              delete:
                description: <p>Delete a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
              get:
                description: >-
                  <p>By default, you can see the 10 most recent sources stored
                  on a Customer directly on the object, but you can also
                  retrieve details about a specific bank account stored on the
                  Stripe account.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
              post:
                description: <p>Update a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
            /v1/customers/{customer}/bank_accounts/{id}/verify:
              post:
                description: <p>Verify a specified bank account for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
            /v1/customers/{customer}/cards:
              get:
                description: >-
                  <p>You can see a list of the cards belonging to a customer.

                  Note that the 10 most recent sources are always available on
                  the <code>Customer</code> object.

                  If you need more than those 10, you can use this API method
                  and the <code>limit</code> and <code>starting_after</code>
                  parameters to page through additional cards.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
              post:
                description: >-
                  <p>When you create a new credit card, you must specify a
                  customer or recipient on which to create it.</p>


                  <p>If the card’s owner has no default card, then the new card
                  will become the default.

                  However, if the owner already has a default, then it will not
                  change.

                  To change the default, you should <a
                  href="/docs/api#update_customer">update the customer</a> to
                  have a new <code>default_source</code>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
            /v1/customers/{customer}/cards/{id}:
              delete:
                description: <p>Delete a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
              get:
                description: >-
                  <p>You can always see the 10 most recent cards directly on a
                  customer; this method lets you retrieve details about a
                  specific card stored on the customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
              post:
                description: <p>Update a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
            /v1/customers/{customer}/cash_balance:
              get:
                description: <p>Retrieves a customer’s cash balance.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
              post:
                description: <p>Changes the settings on a customer’s cash balance.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
            /v1/customers/{customer}/cash_balance_transactions:
              get:
                description: >-
                  <p>Returns a list of transactions that modified the customer’s
                  <a href="/docs/payments/customer-balance">cash
                  balance</a>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
            /v1/customers/{customer}/cash_balance_transactions/{transaction}:
              get:
                description: >-
                  <p>Retrieves a specific cash balance transaction, which
                  updated the customer’s <a
                  href="/docs/payments/customer-balance">cash balance</a>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
            /v1/customers/{customer}/discount:
              delete:
                description: <p>Removes the currently applied discount on a customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
              get:
                description: ''
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
            /v1/customers/{customer}/funding_instructions:
              post:
                description: >-
                  <p>Retrieve funding instructions for a customer cash balance.
                  If funding instructions do not yet exist for the customer, new

                  funding instructions will be created. If funding instructions
                  have already been created for a given customer, the same

                  funding instructions will be retrieved. In other words, we
                  will return the same funding instructions each time.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
            /v1/customers/{customer}/payment_methods:
              get:
                description: <p>Returns a list of PaymentMethods for a given Customer</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
            /v1/customers/{customer}/payment_methods/{payment_method}:
              get:
                description: <p>Retrieves a PaymentMethod object for a given Customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
            /v1/customers/{customer}/sources:
              get:
                description: <p>List sources for a specified customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
              post:
                description: >-
                  <p>When you create a new credit card, you must specify a
                  customer or recipient on which to create it.</p>


                  <p>If the card’s owner has no default card, then the new card
                  will become the default.

                  However, if the owner already has a default, then it will not
                  change.

                  To change the default, you should <a
                  href="/docs/api#update_customer">update the customer</a> to
                  have a new <code>default_source</code>.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
            /v1/customers/{customer}/sources/{id}:
              delete:
                description: <p>Delete a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
              get:
                description: <p>Retrieve a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
              post:
                description: <p>Update a specified source for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
            /v1/customers/{customer}/sources/{id}/verify:
              post:
                description: <p>Verify a specified bank account for a given customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
            /v1/customers/{customer}/subscriptions:
              get:
                description: >-
                  <p>You can see a list of the customer’s active subscriptions.
                  Note that the 10 most recent active subscriptions are always
                  available by default on the customer object. If you need more
                  than those 10, you can use the limit and starting_after
                  parameters to page through additional subscriptions.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
              post:
                description: <p>Creates a new subscription on an existing customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
            /v1/customers/{customer}/subscriptions/{subscription_exposed_id}:
              delete:
                description: >-
                  <p>Cancels a customer’s subscription. If you set the
                  <code>at_period_end</code> parameter to <code>true</code>, the
                  subscription will remain active until the end of the period,
                  at which point it will be canceled and not renewed. Otherwise,
                  with the default <code>false</code> value, the subscription is
                  terminated immediately. In either case, the customer will not
                  be charged again for the subscription.</p>


                  <p>Note, however, that any pending invoice items that you’ve
                  created will still be charged for at the end of the period,
                  unless manually <a href="#delete_invoiceitem">deleted</a>. If
                  you’ve set the subscription to cancel at the end of the
                  period, any pending prorations will also be left in place and
                  collected at the end of the period. But if the subscription is
                  set to cancel immediately, pending prorations will be
                  removed.</p>


                  <p>By default, upon subscription cancellation, Stripe will
                  stop automatic collection of all finalized invoices for the
                  customer. This is intended to prevent unexpected payment
                  attempts after the customer has canceled a subscription.
                  However, you can resume automatic collection of the invoices
                  manually after subscription cancellation to have us proceed.
                  Or, you could check for unpaid invoices before allowing the
                  customer to cancel the subscription at all.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
              get:
                description: <p>Retrieves the subscription with the given ID.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
              post:
                description: >-
                  <p>Updates an existing subscription on a customer to match the
                  specified parameters. When changing plans or quantities, we
                  will optionally prorate the price we charge next month to make
                  up for any price changes. To preview how the proration will be
                  calculated, use the <a href="#upcoming_invoice">upcoming
                  invoice</a> endpoint.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
            /v1/customers/{customer}/subscriptions/{subscription_exposed_id}/discount:
              delete:
                description: <p>Removes the currently applied discount on a customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
              get:
                description: ''
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
            /v1/customers/{customer}/tax_ids:
              get:
                description: <p>Returns a list of tax IDs for a customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
                  - Tax_ids
              post:
                description: >-
                  <p>Creates a new <code>tax_id</code> object for a
                  customer.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
                  - Tax_ids
            /v1/customers/{customer}/tax_ids/{id}:
              delete:
                description: <p>Deletes an existing <code>tax_id</code> object.</p>
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
                  - Tax_ids
              get:
                description: >-
                  <p>Retrieves the <code>tax_id</code> object with the given
                  ident
                tags:
                  - V1
                  - Customers
                  - Search
                  - Customer
                  - Balance_transactions
                  - Transaction
                  - Bank_accounts
                  - Id
                  - Verify
                  - Cards
                  - Cash_balance
                  - Cash_balance_transactions
                  - Discount
                  - Funding_instructions
                  - Payment_methods
                  - Payment_method
                  - Sources
                  - Subscriptions
                  - Subscription_exposed_id
                  - Tax_i
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-response-get-200-schema-components-warn
              message: GET Response 200 Schema Components
            - code: invalid-ref
              message: '''#/components/schemas/deleted_payment_source'' does not exist'
            - code: openapi-operations-description-error
              message: Operation Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-type-error
              message: Schema Type
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/customers-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/customers-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-disputes-api
    name: Stripe Disputes API
    description: >-
      A dispute occurs when a customer questions your charge with their card
      issuer. When this happens, you have the opportunity to respond to the
      dispute with evidence that shows that the charge is legitimate.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/disputes
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/disputes
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Disputes API
          paths:
            /v1/disputes:
              get:
                description: <p>Returns a list of your disputes.</p>
                tags:
                  - V1
                  - Disputes
            /v1/disputes/{dispute}:
              get:
                description: <p>Retrieves the dispute with the given ID.</p>
                tags:
                  - V1
                  - Disputes
                  - Dispute
              post:
                description: >-
                  <p>When you get a dispute, contacting your customer is always
                  the best first step. If that doesn’t work, you can submit
                  evidence to help us resolve the dispute in your favor. You can
                  do this in your <a
                  href="https://dashboard.stripe.com/disputes">dashboard</a>,
                  but if you prefer, you can use the API to submit evidence
                  programmatically.</p>


                  <p>Depending on your dispute type, different evidence fields
                  will give you a better chance of winning your dispute. To
                  figure out which evidence fields to provide, see our <a
                  href="/docs/disputes/categories">guide to dispute
                  types</a>.</p>
                tags:
                  - V1
                  - Disputes
                  - Dispute
            /v1/disputes/{dispute}/close:
              post:
                description: >-
                  <p>Closing the dispute for a charge indicates that you do not
                  have any evidence to submit and are essentially dismissing the
                  dispute, acknowledging it as lost.</p>


                  <p>The status of the dispute will change from
                  <code>needs_response</code> to <code>lost</code>. <em>Closing
                  a dispute is irreversible
                tags:
                  - V1
                  - Disputes
                  - Dispute
                  - Clo
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/disputes-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/disputes-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-ephemeral-keys-api
    name: Stripe Ephemeral Keys API
    description: >-
      Stripe.js uses ephemeral keys to securely retrieve Card information from
      the Stripe API without publicly exposing your secret keys. You need to do
      some of the ephemeral key exchange on the server-side to set this up.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/issuing/elements
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/issuing/elements
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Ephemeral Keys API
          paths:
            /v1/ephemeral_keys:
              post:
                description: <p>Creates a short-lived API key for a given resource.</p>
                tags:
                  - V1
                  - Ephemeral_keys
            /v1/ephemeral_keys/{key}:
              delete:
                description: <p>Invalidates a short-lived API key for a given res
                tags:
                  - V1
                  - Ephemeral_keys
                  - K
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
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
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/ephemeral-keys-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/ephemeral-keys-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-events-api
    name: Stripe Events API
    description: >-
      Events are our way of letting you know when something interesting happens
      in your account. When an interesting event occurs, we create a new Event
      object.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/events
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/events
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Events API
          paths:
            /v1/events:
              get:
                description: >-
                  <p>List events, going back up to 30 days. Each event data is
                  rendered according to Stripe API version at its creation time,
                  specified in <a href="/docs/api/events/object">event
                  object</a> <code>api_version</code> attribute (not according
                  to your current Stripe API version or
                  <code>Stripe-Version</code> header).</p>
                tags:
                  - V1
                  - Events
            /v1/events/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an event. Supply the unique
                  identifier of the event, which you might have received in a we
                tags:
                  - V1
                  - Events
                  - null
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/events-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/events-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-exchange-rates-api
    name: Stripe Exchange Rates API
    description: >-
      Stripe supports processing charges in 135+ currencies allowing you to
      present prices in a customer’s native currency. Doing so can improve sales
      and help customers avoid conversion costs. In order to present prices in
      your customer’s currency, you need to specify the presentment currency
      when creating a PaymentIntent or a charge.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/currencies/conversions
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/currencies/conversions
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Exchange Rates API
          paths:
            /v1/exchange_rates:
              get:
                description: >-
                  <p>Returns a list of objects that contain the rates at which
                  foreign currencies are converted to one another. Only shows
                  the currencies for which Stripe supports.</p>
                tags:
                  - V1
                  - Exchange_rates
            /v1/exchange_rates/{rate_id}:
              get:
                description: >-
                  <p>Retrieves the exchange rates from the given currency to
                  every supported cur
                tags:
                  - V1
                  - Exchange_rates
                  - Rate_
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/exchange-rates-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/exchange-rates-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-files-api
    name: Stripe Files API
    description: >-
      This object represents files hosted on Stripe’s servers. You can upload
      files with the create file request (for example, when uploading dispute
      evidence). Stripe also creates files independently (for example, the
      results of a Sigma scheduled query).
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/files
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/files
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Files API
          paths:
            /v1/files:
              get:
                description: >-
                  <p>Returns a list of the files that your account has access
                  to. Stripe sorts and returns the files by their creation
                  dates, placing the most recently created files at the top.</p>
                tags:
                  - V1
                  - Files
              post:
                description: >-
                  <p>To upload a file to Stripe, you need to send a request of
                  type <code>multipart/form-data</code>. Include the file you
                  want to upload in the request, and the parameters for creating
                  a file.</p>


                  <p>All of Stripe’s officially supported Client libraries
                  support sending <code>multipart/form-data</code>.</p>
                tags:
                  - V1
                  - Files
            /v1/files/{file}:
              get:
                description: >-
                  <p>Retrieves the details of an existing file object. After you
                  supply a unique file ID, Stripe returns the corresponding file
                  object. Learn how to <a
                  href="/docs/file-upload#download-file-contents">access file
                  content
                tags:
                  - V1
                  - Files
                  - Fi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/files-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/files-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-financial-connections-api
    name: Stripe Financial Connections API
    description: >-
      Financial Connections lets your users securely share their financial data
      by linking their financial accounts to your business. Use Financial
      Connections to access user-permissioned account data such as tokenized
      account and routing numbers, balances, ownerships details, and
      transactions.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/financial-connections
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/financial-connections
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Financial Connections API
          paths:
            /v1/financial_connections/accounts:
              get:
                description: >-
                  <p>Returns a list of Financial Connections
                  <code>Account</code> objects.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
            /v1/financial_connections/accounts/{account}:
              get:
                description: >-
                  <p>Retrieves the details of an Financial Connections
                  <code>Account</code>.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
            /v1/financial_connections/accounts/{account}/disconnect:
              post:
                description: >-
                  <p>Disables your access to a Financial Connections
                  <code>Account</code>. You will no longer be able to access
                  data associated with the account (e.g. balances,
                  transactions).</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
            /v1/financial_connections/accounts/{account}/owners:
              get:
                description: <p>Lists all owners for a given <code>Account</code></p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
            /v1/financial_connections/accounts/{account}/refresh:
              post:
                description: >-
                  <p>Refreshes the data associated with a Financial Connections
                  <code>Account</code>.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
            /v1/financial_connections/accounts/{account}/subscribe:
              post:
                description: >-
                  <p>Subscribes to periodic refreshes of data associated with a
                  Financial Connections <code>Account</code>.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
            /v1/financial_connections/accounts/{account}/unsubscribe:
              post:
                description: >-
                  <p>Unsubscribes from periodic refreshes of data associated
                  with a Financial Connections <code>Account</code>.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
                  - Unsubscribe
            /v1/financial_connections/sessions:
              post:
                description: >-
                  <p>To launch the Financial Connections authorization flow,
                  create a <code>Session</code>. The session’s
                  <code>client_secret</code> can be used to launch the flow
                  using Stripe.js.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
                  - Unsubscribe
                  - Sessions
            /v1/financial_connections/sessions/{session}:
              get:
                description: >-
                  <p>Retrieves the details of a Financial Connections
                  <code>Session</code></p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
                  - Unsubscribe
                  - Sessions
                  - Session
            /v1/financial_connections/transactions:
              get:
                description: >-
                  <p>Returns a list of Financial Connections
                  <code>Transaction</code> objects.</p>
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
                  - Unsubscribe
                  - Sessions
                  - Session
                  - Transactions
            /v1/financial_connections/transactions/{transaction}:
              get:
                description: >-
                  <p>Retrieves the details of a Financial Connections
                  <code>Transaction<
                tags:
                  - V1
                  - Financial_connections
                  - Accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refresh
                  - Subscribe
                  - Unsubscribe
                  - Sessions
                  - Session
                  - Transactions
                  - Transacti
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/financial-connections-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/financial-connections-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-identity-api
    name: Stripe Identity API
    description: >-
      Use Stripe Identity to confirm the identity of global users to prevent
      fraud, streamline risk operations, and increase trust and safety.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/identity
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/identity
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Identity API
          paths:
            /v1/identity/verification_reports:
              get:
                description: <p>List all verification reports.</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
            /v1/identity/verification_reports/{report}:
              get:
                description: <p>Retrieves an existing VerificationReport</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
            /v1/identity/verification_sessions:
              get:
                description: <p>Returns a list of VerificationSessions</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
              post:
                description: >-
                  <p>Creates a VerificationSession object.</p>


                  <p>After the VerificationSession is created, display a
                  verification modal using the session
                  <code>client_secret</code> or send your users to the session’s
                  <code>url</code>.</p>


                  <p>If your API key is in test mode, verification checks won’t
                  actually process, though everything else will occur as if in
                  live mode.</p>


                  <p>Related guide: <a
                  href="/docs/identity/verify-identity-documents">Verify your
                  users’ identity documents</a></p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
            /v1/identity/verification_sessions/{session}:
              get:
                description: >-
                  <p>Retrieves the details of a VerificationSession that was
                  previously created.</p>


                  <p>When the session status is <code>requires_input</code>, you
                  can use this method to retrieve a valid

                  <code>client_secret</code> or <code>url</code> to allow
                  re-submission.</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
                  - Session
              post:
                description: >-
                  <p>Updates a VerificationSession object.</p>


                  <p>When the session status is <code>requires_input</code>, you
                  can use this method to update the

                  verification check and options.</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
                  - Session
            /v1/identity/verification_sessions/{session}/cancel:
              post:
                description: >-
                  <p>A VerificationSession object can be canceled when it is in
                  <code>requires_input</code> <a
                  href="/docs/identity/how-sessions-work">status</a>.</p>


                  <p>Once canceled, future submission attempts are disabled.
                  This cannot be undone. <a
                  href="/docs/identity/verification-sessions#cancel">Learn
                  more</a>.</p>
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
                  - Session
                  - Cancel
            /v1/identity/verification_sessions/{session}/redact:
              post:
                description: >-
                  <p>Redact a VerificationSession to remove all collected
                  information from Stripe. This will redact

                  the VerificationSession and all objects related to it,
                  including VerificationReports, Events,

                  request logs, etc.</p>


                  <p>A VerificationSession object can be redacted when it is in
                  <code>requires_input</code> or <code>verified</code>

                  <a href="/docs/identity/how-sessions-work">status</a>.
                  Redacting a VerificationSession in
                  <code>requires_action</code>

                  state will automatically cancel it.</p>


                  <p>The redaction process may take up to four days. When the
                  redaction process is in progress, the

                  VerificationSession’s <code>redaction.status</code> field will
                  be set to <code>processing</code>; when the process is

                  finished, it will change to <code>redacted</code> and an
                  <code>identity.verification_session.redacted</code> event

                  will be emitted.</p>


                  <p>Redaction is irreversible. Redacted objects are still
                  accessible in the Stripe API, but all the

                  fields that contain personal data will be replaced by the
                  string <code>[redacted]</code> or a similar

                  placeholder. The <code>metadata</code> field will also be
                  erased. Redacted objects cannot be updated or

                  used for any purpose.</p>


                  <p><a href="/docs/identity/verification-sessions#redact">Learn
                  mor
                tags:
                  - V1
                  - Identity
                  - Verification_reports
                  - Report
                  - Verification_sessions
                  - Session
                  - Cancel
                  - Reda
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/identity-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/identity-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-invoice-api
    name: Stripe Invoice API
    description: >-
      Invoices are statements of amounts owed by a customer, and are either
      generated one-off, or generated periodically from a subscription.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/invoices
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/invoices
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Invoice API
          paths:
            /v1/invoiceitems:
              get:
                description: >-
                  <p>Returns a list of your invoice items. Invoice items are
                  returned sorted by creation date, with the most recently
                  created invoice items appearing first.</p>
                tags:
                  - V1
                  - Invoiceitems
              post:
                description: >-
                  <p>Creates an item to be added to a draft invoice (up to 250
                  items per invoice). If no invoice is specified, the item will
                  be on the next invoice created for the customer specified.</p>
                tags:
                  - V1
                  - Invoiceitems
            /v1/invoiceitems/{invoiceitem}:
              delete:
                description: >-
                  <p>Deletes an invoice item, removing it from an invoice.
                  Deleting invoice items is only possible when they’re not
                  attached to invoices, or if it’s attached to a draft
                  invoice.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
              get:
                description: <p>Retrieves the invoice item with the given ID.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
              post:
                description: >-
                  <p>Updates the amount or description of an invoice item on an
                  upcoming invoice. Updating an invoice item is only possible
                  before the invoice it’s attached to is closed.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
            /v1/invoices:
              get:
                description: >-
                  <p>You can list all invoices, or list the invoices for a
                  specific customer. The invoices are returned sorted by
                  creation date, with the most recently created invoices
                  appearing first.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
              post:
                description: >-
                  <p>This endpoint creates a draft invoice for a given customer.
                  The invoice remains a draft until you <a
                  href="#finalize_invoice">finalize</a> the invoice, which
                  allows you to <a href="#pay_invoice">pay</a> or <a
                  href="#send_invoice">send</a> the invoice to your
                  customers.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
            /v1/invoices/search:
              get:
                description: >-
                  <p>Search for invoices you’ve previously created using
                  Stripe’s <a href="/docs/search#search-query-language">Search
                  Query Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
            /v1/invoices/upcoming:
              get:
                description: >-
                  <p>At any time, you can preview the upcoming invoice for a
                  customer. This will show you all the charges that are pending,
                  including subscription renewal charges, invoice item charges,
                  etc. It will also show you any discounts that are applicable
                  to the invoice.</p>


                  <p>Note that when you are viewing an upcoming invoice, you are
                  simply viewing a preview – the invoice has not yet been
                  created. As such, the upcoming invoice will not show up in
                  invoice listing calls, and you cannot use the API to pay or
                  edit the invoice. If you want to change the amount that your
                  customer will be billed, you can add, remove, or update
                  pending invoice items, or update the customer’s discount.</p>


                  <p>You can preview the effects of updating a subscription,
                  including a preview of what proration will take place. To
                  ensure that the actual proration is calculated exactly the
                  same as the previewed proration, you should pass a
                  <code>proration_date</code> parameter when doing the actual
                  subscription update. The value passed in should be the same as
                  the <code>subscription_proration_date</code> returned on the
                  upcoming invoice resource. The recommended way to get only the
                  prorations being previewed is to consider only proration line
                  items where <code>period[start]</code> is equal to the
                  <code>subscription_proration_date</code> on the upcoming
                  invoice resource.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
            /v1/invoices/upcoming/lines:
              get:
                description: >-
                  <p>When retrieving an upcoming invoice, you’ll get a
                  <strong>lines</strong> property containing the total count of
                  line items and the first handful of those items. There is also
                  a URL where you can retrieve the full (paginated) list of line
                  items.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
            /v1/invoices/{invoice}:
              delete:
                description: >-
                  <p>Permanently deletes a one-off invoice draft. This cannot be
                  undone. Attempts to delete invoices that are no longer in a
                  draft state will fail; once an invoice has been finalized or
                  if an invoice is for a subscription, it must be <a
                  href="#void_invoice">voided</a>.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
              get:
                description: <p>Retrieves the invoice with the given ID.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
              post:
                description: >-
                  <p>Draft invoices are fully editable. Once an invoice is <a
                  href="/docs/billing/invoices/workflow#finalized">finalized</a>,

                  monetary values, as well as <code>collection_method</code>,
                  become uneditable.</p>


                  <p>If you would like to stop the Stripe Billing engine from
                  automatically finalizing, reattempting payments on,

                  sending reminders for, or <a
                  href="/docs/billing/invoices/reconciliation">automatically
                  reconciling</a> invoices, pass

                  <code>auto_advance=false</code>.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
            /v1/invoices/{invoice}/finalize:
              post:
                description: >-
                  <p>Stripe automatically finalizes drafts before sending and
                  attempting payment on invoices. However, if you’d like to
                  finalize a draft invoice manually, you can do so using this
                  method.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
            /v1/invoices/{invoice}/lines:
              get:
                description: >-
                  <p>When retrieving an invoice, you’ll get a
                  <strong>lines</strong> property containing the total count of
                  line items and the first handful of those items. There is also
                  a URL where you can retrieve the full (paginated) list of line
                  items.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
            /v1/invoices/{invoice}/lines/{line_item_id}:
              post:
                description: >-
                  <p>Updates an invoice’s line item. Some fields, such as
                  <code>tax_amounts</code>, only live on the invoice line item,

                  so they can only be updated through this endpoint. Other
                  fields, such as <code>amount</code>, live on both the invoice

                  item and the invoice line item, so updates on this endpoint
                  will propagate to the invoice item as well.

                  Updating an invoice’s line item is only possible before the
                  invoice is finalized.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
                  - Line_item_id
            /v1/invoices/{invoice}/mark_uncollectible:
              post:
                description: >-
                  <p>Marking an invoice as uncollectible is useful for keeping
                  track of bad debts that can be written off for accounting
                  purposes.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
                  - Line_item_id
                  - Mark_uncollectible
            /v1/invoices/{invoice}/pay:
              post:
                description: >-
                  <p>Stripe automatically creates and then attempts to collect
                  payment on invoices for customers on subscriptions according
                  to your <a
                  href="https://dashboard.stripe.com/account/billing/automatic">subscriptions
                  settings</a>. However, if you’d like to attempt payment on an
                  invoice out of the normal collection schedule or for some
                  other reason, you can do so.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
                  - Line_item_id
                  - Mark_uncollectible
                  - Pay
            /v1/invoices/{invoice}/send:
              post:
                description: >-
                  <p>Stripe will automatically send invoices to customers
                  according to your <a
                  href="https://dashboard.stripe.com/account/billing/automatic">subscriptions
                  settings</a>. However, if you’d like to manually send an
                  invoice to your customer out of the normal schedule, you can
                  do so. When sending invoices that have already been paid,
                  there will be no reference to the payment in the email.</p>


                  <p>Requests made in test-mode result in no emails being sent,
                  despite sending an <code>invoice.sent</code> event.</p>
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
                  - Line_item_id
                  - Mark_uncollectible
                  - Pay
                  - Send
            /v1/invoices/{invoice}/void:
              post:
                description: >-
                  <p>Mark a finalized invoice as void. This cannot be undone.
                  Voiding an invoice is similar to <a
                  href="#delete_invoice">deletion</a>, however it only applies
                  to finalized invoices and maintains a papertrail where the
                  invoice can still be 
                tags:
                  - V1
                  - Invoiceitems
                  - Invoiceitem
                  - Invoices
                  - Search
                  - Upcoming
                  - Lines
                  - Invoice
                  - Finalize
                  - Line_item_id
                  - Mark_uncollectible
                  - Pay
                  - Send
                  - Vo
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/invoice-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/invoice-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-issuing-api
    name: Stripe Issuing API
    description: >-
      An API for businesses to instantly create, manage, and distribute payment
      cards.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/issuing
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/issuing
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Issuing API
          paths:
            /v1/issuing/authorizations:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Authorization</code>
                  objects. The objects are sorted in descending order by
                  creation date, with the most recently created object appearing
                  first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
            /v1/issuing/authorizations/{authorization}:
              get:
                description: <p>Retrieves an Issuing <code>Authorization</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Authorization</code>
                  object by setting the values of the parameters passed. Any
                  parameters not provided will be left unchanged.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
            /v1/issuing/authorizations/{authorization}/approve:
              post:
                description: >-
                  <p>[Deprecated] Approves a pending Issuing
                  <code>Authorization</code> object. This request should be made
                  within the timeout window of the <a
                  href="/docs/issuing/controls/real-time-authorizations">real-time
                  authorization</a> flow. 

                  This method is deprecated. Instead, <a
                  href="/docs/issuing/controls/real-time-authorizations#authorization-handling">respond
                  directly to the webhook request to approve an
                  authorization</a>.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
            /v1/issuing/authorizations/{authorization}/decline:
              post:
                description: >-
                  <p>[Deprecated] Declines a pending Issuing
                  <code>Authorization</code> object. This request should be made
                  within the timeout window of the <a
                  href="/docs/issuing/controls/real-time-authorizations">real
                  time authorization</a> flow.

                  This method is deprecated. Instead, <a
                  href="/docs/issuing/controls/real-time-authorizations#authorization-handling">respond
                  directly to the webhook request to decline an
                  authorization</a>.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
            /v1/issuing/cardholders:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Cardholder</code> objects.
                  The objects are sorted in descending order by creation date,
                  with the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
              post:
                description: >-
                  <p>Creates a new Issuing <code>Cardholder</code> object that
                  can be issued cards.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
            /v1/issuing/cardholders/{cardholder}:
              get:
                description: <p>Retrieves an Issuing <code>Cardholder</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Cardholder</code>
                  object by setting the values of the parameters passed. Any
                  parameters not provided will be left unchanged.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
            /v1/issuing/cards:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Card</code> objects. The
                  objects are sorted in descending order by creation date, with
                  the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
              post:
                description: <p>Creates an Issuing <code>Card</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
            /v1/issuing/cards/{card}:
              get:
                description: <p>Retrieves an Issuing <code>Card</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Card</code> object by
                  setting the values of the parameters passed. Any parameters
                  not provided will be left unchanged.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
            /v1/issuing/disputes:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Dispute</code> objects. The
                  objects are sorted in descending order by creation date, with
                  the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
              post:
                description: >-
                  <p>Creates an Issuing <code>Dispute</code> object. Individual
                  pieces of evidence within the <code>evidence</code> object are
                  optional at this point. Stripe only validates that required
                  evidence is present during submission. Refer to <a
                  href="/docs/issuing/purchases/disputes#dispute-reasons-and-evidence">Dispute
                  reasons and evidence</a> for more details about evidence
                  requirements.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
            /v1/issuing/disputes/{dispute}:
              get:
                description: <p>Retrieves an Issuing <code>Dispute</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Dispute</code> object
                  by setting the values of the parameters passed. Any parameters
                  not provided will be left unchanged. Properties on the
                  <code>evidence</code> object can be unset by passing in an
                  empty string.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
            /v1/issuing/disputes/{dispute}/submit:
              post:
                description: >-
                  <p>Submits an Issuing <code>Dispute</code> to the card
                  network. Stripe validates that all evidence fields required
                  for the dispute’s reason are present. For more details, see <a
                  href="/docs/issuing/purchases/disputes#dispute-reasons-and-evidence">Dispute
                  reasons and evidence</a>.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
            /v1/issuing/settlements:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Settlement</code> objects.
                  The objects are sorted in descending order by creation date,
                  with the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
            /v1/issuing/settlements/{settlement}:
              get:
                description: <p>Retrieves an Issuing <code>Settlement</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Settlement</code>
                  object by setting the values of the parameters passed. Any
                  parameters not provided will be left unchanged.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
            /v1/issuing/tokens:
              get:
                description: >-
                  <p>Lists all Issuing <code>Token</code> objects for a given
                  card.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
            /v1/issuing/tokens/{token}:
              get:
                description: <p>Retrieves an Issuing <code>Token</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
                  - Token
              post:
                description: >-
                  <p>Attempts to update the specified Issuing <code>Token</code>
                  object to the status specified.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
                  - Token
            /v1/issuing/transactions:
              get:
                description: >-
                  <p>Returns a list of Issuing <code>Transaction</code> objects.
                  The objects are sorted in descending order by creation date,
                  with the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
                  - Token
                  - Transactions
            /v1/issuing/transactions/{transaction}:
              get:
                description: <p>Retrieves an Issuing <code>Transaction</code> object.</p>
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
                  - Token
                  - Transactions
                  - Transaction
              post:
                description: >-
                  <p>Updates the specified Issuing <code>Transaction</code>
                  object by setting the values of the parameters passed. Any
                  parameters not provided will be left unch
                tags:
                  - V1
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Approve
                  - Decline
                  - Cardholders
                  - Cardholder
                  - Cards
                  - Card
                  - Disputes
                  - Dispute
                  - Submit
                  - Settlements
                  - Settlement
                  - Tokens
                  - Token
                  - Transactions
                  - Transacti
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
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
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/issuing-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/issuing-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-link-api
    name: Stripe Link API
    description: >-
      You can use the Payment Links API to create a payment link that you can
      share with your customers. Stripe redirects customers who open this link
      to a Stripe-hosted payment page.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/payment-links/api
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/payment-links/api
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Link API
          paths:
            /v1/link_account_sessions:
              post:
                description: >-
                  <p>To launch the Financial Connections authorization flow,
                  create a <code>Session</code>. The session’s
                  <code>client_secret</code> can be used to launch the flow
                  using Stripe.js.</p>
                tags:
                  - V1
                  - Link_account_sessions
            /v1/link_account_sessions/{session}:
              get:
                description: >-
                  <p>Retrieves the details of a Financial Connections
                  <code>Session</code></p>
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
            /v1/linked_accounts:
              get:
                description: >-
                  <p>Returns a list of Financial Connections
                  <code>Account</code> objects.</p>
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
                  - Linked_accounts
            /v1/linked_accounts/{account}:
              get:
                description: >-
                  <p>Retrieves the details of an Financial Connections
                  <code>Account</code>.</p>
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
                  - Linked_accounts
                  - Account
            /v1/linked_accounts/{account}/disconnect:
              post:
                description: >-
                  <p>Disables your access to a Financial Connections
                  <code>Account</code>. You will no longer be able to access
                  data associated with the account (e.g. balances,
                  transactions).</p>
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
                  - Linked_accounts
                  - Account
                  - Disconnect
            /v1/linked_accounts/{account}/owners:
              get:
                description: <p>Lists all owners for a given <code>Account</code></p>
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
                  - Linked_accounts
                  - Account
                  - Disconnect
                  - Owners
            /v1/linked_accounts/{account}/refresh:
              post:
                description: >-
                  <p>Refreshes the data associated with a Financial Connections
                  <code>Account</
                tags:
                  - V1
                  - Link_account_sessions
                  - Session
                  - Linked_accounts
                  - Account
                  - Disconnect
                  - Owners
                  - Refre
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: invalid-ref
              message: >-
                '#/components/schemas/bank_connections_resource_accountholder'
                does not exist
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/link-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/link-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-payment-intents-api
    name: Stripe Payment Intents API
    description: >-
      A PaymentIntent guides you through the process of collecting a payment
      from your customer. We recommend that you create exactly one PaymentIntent
      for each order or customer session in your system. You can reference the
      PaymentIntent later to see the history of payment attempts for a
      particular session.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/payment_intents
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/payment_intents
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Payment Intents API
          paths:
            /v1/payment_intents:
              get:
                description: <p>Returns a list of PaymentIntents.</p>
                tags:
                  - V1
                  - Payment_intents
              post:
                description: >-
                  <p>Creates a PaymentIntent object.</p>


                  <p>After the PaymentIntent is created, attach a payment method
                  and <a href="/docs/api/payment_intents/confirm">confirm</a>

                  to continue the payment. Learn more about <a
                  href="/docs/payments/payment-intents">the available payment
                  flows

                  with the Payment Intents API</a>.</p>


                  <p>When you use <code>confirm=true</code> during creation,
                  it’s equivalent to creating

                  and confirming the PaymentIntent in the same call. You can use
                  any parameters

                  available in the <a
                  href="/docs/api/payment_intents/confirm">confirm API</a> when
                  you supply

                  <code>confirm=true</code>.</p>
                tags:
                  - V1
                  - Payment_intents
            /v1/payment_intents/search:
              get:
                description: >-
                  <p>Search for PaymentIntents you’ve previously created using
                  Stripe’s <a href="/docs/search#search-query-language">Search
                  Query Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
            /v1/payment_intents/{intent}:
              get:
                description: >-
                  <p>Retrieves the details of a PaymentIntent that has
                  previously been created. </p>


                  <p>You can retrieve a PaymentIntent client-side using a
                  publishable key when the <code>client_secret</code> is in the
                  query string. </p>


                  <p>If you retrieve a PaymentIntent with a publishable key, it
                  only returns a subset of properties. Refer to the <a
                  href="#payment_intent_object">payment intent</a> object
                  reference for more details.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
              post:
                description: >-
                  <p>Updates properties on a PaymentIntent object without
                  confirming.</p>


                  <p>Depending on which properties you update, you might need to
                  confirm the

                  PaymentIntent again. For example, updating the
                  <code>payment_method</code>

                  always requires you to confirm the PaymentIntent again. If you
                  prefer to

                  update and confirm at the same time, we recommend updating
                  properties through

                  the <a href="/docs/api/payment_intents/confirm">confirm
                  API</a> instead.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
            /v1/payment_intents/{intent}/apply_customer_balance:
              post:
                description: >-
                  <p>Manually reconcile the remaining amount for a
                  <code>customer_balance</code> PaymentIntent.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
            /v1/payment_intents/{intent}/cancel:
              post:
                description: >-
                  <p>You can cancel a PaymentIntent object when it’s in one of
                  these statuses: <code>requires_payment_method</code>,
                  <code>requires_capture</code>,
                  <code>requires_confirmation</code>,
                  <code>requires_action</code> or, <a
                  href="/docs/payments/intents">in rare cases</a>,
                  <code>processing</code>. </p>


                  <p>After it’s canceled, no additional charges are made by the
                  PaymentIntent and any operations on the PaymentIntent fail
                  with an error. For PaymentIntents with a <code>status</code>
                  of <code>requires_capture</code>, the remaining
                  <code>amount_capturable</code> is automatically refunded. </p>


                  <p>You can’t cancel the PaymentIntent for a Checkout Session.
                  <a href="/docs/api/checkout/sessions/expire">Expire the
                  Checkout Session</a> instead.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
                  - Cancel
            /v1/payment_intents/{intent}/capture:
              post:
                description: >-
                  <p>Capture the funds of an existing uncaptured PaymentIntent
                  when its status is <code>requires_capture</code>.</p>


                  <p>Uncaptured PaymentIntents are cancelled a set number of
                  days (7 by default) after their creation.</p>


                  <p>Learn more about <a
                  href="/docs/payments/capture-later">separate authorization and
                  capture</a>.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
                  - Cancel
                  - Capture
            /v1/payment_intents/{intent}/confirm:
              post:
                description: >-
                  <p>Confirm that your customer intends to pay with current or
                  provided

                  payment method. Upon confirmation, the PaymentIntent will
                  attempt to initiate

                  a payment.

                  If the selected payment method requires additional
                  authentication steps, the

                  PaymentIntent will transition to the
                  <code>requires_action</code> status and

                  suggest additional actions via <code>next_action</code>. If
                  payment fails,

                  the PaymentIntent transitions to the
                  <code>requires_payment_method</code> status or the

                  <code>canceled</code> status if the confirmation limit is
                  reached. If

                  payment succeeds, the PaymentIntent will transition to the
                  <code>succeeded</code>

                  status (or <code>requires_capture</code>, if
                  <code>capture_method</code> is set to <code>manual</code>).

                  If the <code>confirmation_method</code> is
                  <code>automatic</code>, payment may be attempted

                  using our <a
                  href="/docs/stripe-js/reference#stripe-handle-card-payment">client
                  SDKs</a>

                  and the PaymentIntent’s <a
                  href="#payment_intent_object-client_secret">client_secret</a>.

                  After <code>next_action</code>s are handled by the client, no
                  additional

                  confirmation is required to complete the payment.

                  If the <code>confirmation_method</code> is
                  <code>manual</code>, all payment attempts must be

                  initiated using a secret key.

                  If any actions are required for the payment, the PaymentIntent
                  will

                  return to the <code>requires_confirmation</code> state

                  after those actions are completed. Your server needs to then

                  explicitly re-confirm the PaymentIntent to initiate the next
                  payment

                  attempt. Read the <a
                  href="/docs/payments/payment-intents/web-manual">expanded
                  documentation</a>

                  to learn more about manual confirmation.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
                  - Cancel
                  - Capture
                  - Confirm
            /v1/payment_intents/{intent}/increment_authorization:
              post:
                description: >-
                  <p>Perform an incremental authorization on an eligible

                  <a href="/docs/api/payment_intents/object">PaymentIntent</a>.
                  To be eligible, the

                  PaymentIntent’s status must be <code>requires_capture</code>
                  and

                  <a
                  href="/docs/api/charges/object#charge_object-payment_method_details-card_present-incremental_authorization_supported">incremental_authorization_supported</a>

                  must be <code>true</code>.</p>


                  <p>Incremental authorizations attempt to increase the
                  authorized amount on

                  your customer’s card to the new, higher <code>amount</code>
                  provided. Similar to the

                  initial authorization, incremental authorizations can be
                  declined. A

                  single PaymentIntent can call this endpoint multiple times to
                  further

                  increase the authorized amount.</p>


                  <p>If the incremental authorization succeeds, the
                  PaymentIntent object

                  returns with the updated

                  <a
                  href="/docs/api/payment_intents/object#payment_intent_object-amount">amount</a>.

                  If the incremental authorization fails, a

                  <a href="/docs/error-codes#card-declined">card_declined</a>
                  error returns, and no other

                  fields on the PaymentIntent or Charge update. The
                  PaymentIntent

                  object remains capturable for the previously authorized
                  amount.</p>


                  <p>Each PaymentIntent can have a maximum of 10 incremental
                  authorization attempts, including declines.

                  After it’s captured, a PaymentIntent can no longer be
                  incremented.</p>


                  <p>Learn more about <a
                  href="/docs/terminal/features/incremental-authorizations">incremental
                  authorizations</a>.</p>
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
                  - Cancel
                  - Capture
                  - Confirm
                  - Increment_authorization
            /v1/payment_intents/{intent}/verify_microdeposits:
              post:
                description: <p>Verifies microdeposits on a PaymentIntent o
                tags:
                  - V1
                  - Payment_intents
                  - Search
                  - Intent
                  - Apply_customer_balance
                  - Cancel
                  - Capture
                  - Confirm
                  - Increment_authorization
                  - Verify_microdeposi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payment-intents-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payment-intents-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-payment-links-api
    name: Stripe Payment Links API
    description: >-
      A payment link is a shareable URL that will take your customers to a
      hosted payment page. A payment link can be shared and used multiple times.
      When a customer opens a payment link it will open a new checkout session
      to render the payment page. You can use checkout session events to track
      payments through payment links.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/payment_links/payment_links
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/payment_links/payment_links
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Payment Links API
          paths:
            /v1/payment_links:
              get:
                description: <p>Returns a list of your payment links.</p>
                tags:
                  - V1
                  - Payment_links
              post:
                description: <p>Creates a payment link.</p>
                tags:
                  - V1
                  - Payment_links
            /v1/payment_links/{payment_link}:
              get:
                description: <p>Retrieve a payment link.</p>
                tags:
                  - V1
                  - Payment_links
                  - Payment_link
              post:
                description: <p>Updates a payment link.</p>
                tags:
                  - V1
                  - Payment_links
                  - Payment_link
            /v1/payment_links/{payment_link}/line_items:
              get:
                description: >-
                  <p>When retrieving a payment link, there is an includable
                  <strong>line_items</strong> property containing the first
                  handful of those items. There is also a URL where you can
                  retrieve the full (paginated) list of line 
                tags:
                  - V1
                  - Payment_links
                  - Payment_link
                  - Line_ite
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payment-links-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payment-links-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-payment-method-api
    name: Stripe Payment Method API
    description: >-
      The Payment Methods API allows you to accept a variety of payment methods
      through a single API. A PaymentMethod object contains the payment method
      details to create payments.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/payments/payment-methods
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/payments/payment-methods
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Payment Method API
          paths:
            /v1/payment_method_configurations:
              get:
                description: <p>List payment method configurations</p>
                tags:
                  - V1
                  - Payment_method_configurations
              post:
                description: <p>Creates a payment method configuration</p>
                tags:
                  - V1
                  - Payment_method_configurations
            /v1/payment_method_configurations/{configuration}:
              get:
                description: <p>Retrieve payment method configuration</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
              post:
                description: <p>Update payment method configuration</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
            /v1/payment_method_domains:
              get:
                description: <p>Lists the details of existing payment method domains.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
              post:
                description: <p>Creates a payment method domain.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
            /v1/payment_method_domains/{payment_method_domain}:
              get:
                description: >-
                  <p>Retrieves the details of an existing payment method
                  domain.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
              post:
                description: <p>Updates an existing payment method domain.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
            /v1/payment_method_domains/{payment_method_domain}/validate:
              post:
                description: >-
                  <p>Some payment methods such as Apple Pay require additional
                  steps to verify a domain. If the requirements weren’t
                  satisfied when the domain was created, the payment method will
                  be inactive on the domain.

                  The payment method doesn’t appear in Elements for this domain
                  until it is active.</p>


                  <p>To activate a payment method on an existing payment method
                  domain, complete the required validation steps specific to the
                  payment method, and then validate the payment method domain
                  with this endpoint.</p>


                  <p>Related guides: <a
                  href="/docs/payments/payment-methods/pmd-registration">Payment
                  method domains</a>.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
            /v1/payment_methods:
              get:
                description: >-
                  <p>Returns a list of PaymentMethods for Treasury flows. If you
                  want to list the PaymentMethods attached to a Customer for
                  payments, you should use the <a
                  href="/docs/api/payment_methods/customer_list">List a
                  Customer’s PaymentMethods</a> API instead.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
              post:
                description: >-
                  <p>Creates a PaymentMethod object. Read the <a
                  href="/docs/stripe-js/reference#stripe-create-payment-method">Stripe.js
                  reference</a> to learn how to create PaymentMethods via
                  Stripe.js.</p>


                  <p>Instead of creating a PaymentMethod directly, we recommend
                  using the <a
                  href="/docs/payments/accept-a-payment">PaymentIntents</a> API
                  to accept a payment immediately or the <a
                  href="/docs/payments/save-and-reuse">SetupIntent</a> API to
                  collect payment method details ahead of a future payment.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
            /v1/payment_methods/{payment_method}:
              get:
                description: >-
                  <p>Retrieves a PaymentMethod object attached to the
                  StripeAccount. To retrieve a payment method attached to a
                  Customer, you should use <a
                  href="/docs/api/payment_methods/customer">Retrieve a
                  Customer’s PaymentMethods</a></p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
                  - Payment_method
              post:
                description: >-
                  <p>Updates a PaymentMethod object. A PaymentMethod must be
                  attached a customer to be updated.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
                  - Payment_method
            /v1/payment_methods/{payment_method}/attach:
              post:
                description: >-
                  <p>Attaches a PaymentMethod object to a Customer.</p>


                  <p>To attach a new PaymentMethod to a customer for future
                  payments, we recommend you use a <a
                  href="/docs/api/setup_intents">SetupIntent</a>

                  or a PaymentIntent with <a
                  href="/docs/api/payment_intents/create#create_payment_intent-setup_future_usage">setup_future_usage</a>.

                  These approaches will perform any necessary steps to set up
                  the PaymentMethod for future payments. Using the
                  <code>/v1/payment_methods/:id/attach</code>

                  endpoint without first using a SetupIntent or PaymentIntent
                  with <code>setup_future_usage</code> does not optimize the
                  PaymentMethod for

                  future use, which makes later declines and payment friction
                  more likely.

                  See <a
                  href="/docs/payments/payment-intents#future-usage">Optimizing
                  cards for future payments</a> for more information about
                  setting up

                  future payments.</p>


                  <p>To use this PaymentMethod as the default for invoice or
                  subscription payments,

                  set <a
                  href="/docs/api/customers/update#update_customer-invoice_settings-default_payment_method"><code>invoice_settings.default_payment_method</code></a>,

                  on the Customer to the PaymentMethod’s ID.</p>
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
                  - Payment_method
                  - Attach
            /v1/payment_methods/{payment_method}/detach:
              post:
                description: >-
                  <p>Detaches a PaymentMethod object from a Customer. After a
                  PaymentMethod is detached, it can no longer be used for a
                  payment or re-attached to a Cus
                tags:
                  - V1
                  - Payment_method_configurations
                  - Configuration
                  - Payment_method_domains
                  - Payment_method_domain
                  - Validate
                  - Payment_methods
                  - Payment_method
                  - Attach
                  - Deta
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payment-method-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payment-method-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-payouts-api
    name: Stripe Payouts API
    description: >-
      A Payout object is created when you receive funds from Stripe, or when you
      initiate a payout to either a bank account or debit card of a connected
      Stripe account. You can retrieve individual payouts, and list all payouts.
      Payouts are made on varying schedules, depending on your country and
      industry.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/payouts
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/payouts
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Payouts API
          paths:
            /v1/payouts:
              get:
                description: >-
                  <p>Returns a list of existing payouts sent to third-party bank
                  accounts or payouts that Stripe sent to you. The payouts
                  return in sorted order, with the most recently created payouts
                  appearing first.</p>
                tags:
                  - V1
                  - Payouts
              post:
                description: >-
                  <p>To send funds to your own bank account, create a new payout
                  object. Your <a href="#balance">Stripe balance</a> must cover
                  the payout amount. If it doesn’t, you receive an “Insufficient
                  Funds” error.</p>


                  <p>If your API key is in test mode, money won’t actually be
                  sent, though every other action occurs as if you’re in live
                  mode.</p>


                  <p>If you create a manual payout on a Stripe account that uses
                  multiple payment source types, you need to specify the source
                  type balance that the payout draws from. The <a
                  href="#balance_object">balance object</a> details available
                  and pending amounts by source type.</p>
                tags:
                  - V1
                  - Payouts
            /v1/payouts/{payout}:
              get:
                description: >-
                  <p>Retrieves the details of an existing payout. Supply the
                  unique payout ID from either a payout creation request or the
                  payout list. Stripe returns the corresponding payout
                  information.</p>
                tags:
                  - V1
                  - Payouts
                  - Payout
              post:
                description: >-
                  <p>Updates the specified payout by setting the values of the
                  parameters you pass. We don’t change parameters that you don’t
                  provide. This request only accepts the metadata as
                  arguments.</p>
                tags:
                  - V1
                  - Payouts
                  - Payout
            /v1/payouts/{payout}/cancel:
              post:
                description: >-
                  <p>You can cancel a previously created payout if it hasn’t
                  been paid out yet. Stripe refunds the funds to your available
                  balance. You can’t cancel automatic Stripe payouts.</p>
                tags:
                  - V1
                  - Payouts
                  - Payout
                  - Cancel
            /v1/payouts/{payout}/reverse:
              post:
                description: >-
                  <p>Reverses a payout by debiting the destination bank account.
                  At this time, you can only reverse payouts for connected
                  accounts to US bank accounts. If the payout is in the
                  <code>pending</code> status, use
                  <code>/v1/payouts/:id/cancel</code> instead.</p>


                  <p>By requesting a reversal through
                  <code>/v1/payouts/:id/reverse</code>, you confirm that the
                  authorized signatory of the selected bank account authorizes
                  the debit on the bank account and that no other authorization
                  is req
                tags:
                  - V1
                  - Payouts
                  - Payout
                  - Cancel
                  - Rever
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/payouts-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/payouts-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-plans-api
    name: Stripe Plans API
    description: >-
      You can now model subscriptions more flexibly using the Prices API. It
      replaces the Plans API and is backwards compatible to simplify your
      migration.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/plans
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/plans
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Plans API
          paths:
            /v1/plans:
              get:
                description: <p>Returns a list of your plans.</p>
                tags:
                  - V1
                  - Plans
              post:
                description: >-
                  <p>You can now model subscriptions more flexibly using the <a
                  href="#prices">Prices API</a>. It replaces the Plans API and
                  is backwards compatible to simplify your migration.</p>
                tags:
                  - V1
                  - Plans
            /v1/plans/{plan}:
              delete:
                description: >-
                  <p>Deleting plans means new subscribers can’t be added.
                  Existing subscribers aren’t affected.</p>
                tags:
                  - V1
                  - Plans
                  - Plan
              get:
                description: <p>Retrieves the plan with the given ID.</p>
                tags:
                  - V1
                  - Plans
                  - Plan
              post:
                description: >-
                  <p>Updates the specified plan by setting the values of the
                  parameters passed. Any parameters not provided are left
                  unchanged. By design, you cannot change a plan’s ID, amount,
                  currency, or billing 
                tags:
                  - V1
                  - Plans
                  - Pl
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/plans-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/plans-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-prices-api
    name: Stripe Prices API
    description: >-
      Prices define the unit cost, currency, and (optional) billing cycle for
      both recurring and one-time purchases of products. Products help you track
      inventory or provisioning, and prices help you track payment terms.
      Different physical goods or levels of service should be represented by
      products, and pricing options should be represented by prices. This
      approach lets you change prices without having to change your provisioning
      scheme.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/prices
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/prices
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Prices API
          paths:
            /v1/prices:
              get:
                description: >-
                  <p>Returns a list of your active prices, excluding <a
                  href="/docs/products-prices/pricing-models#inline-pricing">inline
                  prices</a>. For the list of inactive prices, set
                  <code>active</code> to false.</p>
                tags:
                  - V1
                  - Prices
              post:
                description: >-
                  <p>Creates a new price for an existing product. The price can
                  be recurring or one-time.</p>
                tags:
                  - V1
                  - Prices
            /v1/prices/search:
              get:
                description: >-
                  <p>Search for prices you’ve previously created using Stripe’s
                  <a href="/docs/search#search-query-language">Search Query
                  Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Prices
                  - Search
            /v1/prices/{price}:
              get:
                description: <p>Retrieves the price with the given ID.</p>
                tags:
                  - V1
                  - Prices
                  - Search
                  - Price
              post:
                description: >-
                  <p>Updates the specified price by setting the values of the
                  parameters passed. Any parameters not provided are left unch
                tags:
                  - V1
                  - Prices
                  - Search
                  - Pri
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/prices-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/prices-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-products-api
    name: Stripe Products API
    description: >-
      Products describe the specific goods or services you offer to your
      customers. For example, you might offer a Standard and Premium version of
      your goods or service; each version would be a separate Product. They can
      be used in conjunction with Prices to configure pricing in Payment Links,
      Checkout, and Subscriptions.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/products
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/products
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Products API
          paths:
            /v1/products:
              get:
                description: >-
                  <p>Returns a list of your products. The products are returned
                  sorted by creation date, with the most recently created
                  products appearing first.</p>
                tags:
                  - V1
                  - Products
              post:
                description: <p>Creates a new product object.</p>
                tags:
                  - V1
                  - Products
            /v1/products/search:
              get:
                description: >-
                  <p>Search for products you’ve previously created using
                  Stripe’s <a href="/docs/search#search-query-language">Search
                  Query Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Products
                  - Search
            /v1/products/{id}:
              delete:
                description: >-
                  <p>Delete a product. Deleting a product is only possible if it
                  has no prices associated with it. Additionally, deleting a
                  product with <code>type=good</code> is only possible if it has
                  no SKUs associated with it.</p>
                tags:
                  - V1
                  - Products
                  - Search
                  - Id
              get:
                description: >-
                  <p>Retrieves the details of an existing product. Supply the
                  unique product ID from either a product creation request or
                  the product list, and Stripe will return the corresponding
                  product information.</p>
                tags:
                  - V1
                  - Products
                  - Search
                  - Id
              post:
                description: >-
                  <p>Updates the specific product by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unch
                tags:
                  - V1
                  - Products
                  - Search
                  - null
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/products-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/products-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-promotion-codes-api
    name: Stripe Promotion Codes API
    description: >-
      A Promotion Code represents a customer-redeemable code for a coupon. It
      can be used to create multiple codes for a single coupon.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/promotion_codes
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/promotion_codes
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Promotion Codes API
          paths:
            /v1/promotion_codes:
              get:
                description: <p>Returns a list of your promotion codes.</p>
                tags:
                  - V1
                  - Promotion_codes
              post:
                description: >-
                  <p>A promotion code points to a coupon. You can optionally
                  restrict the code to a specific customer, redemption limit,
                  and expiration date.</p>
                tags:
                  - V1
                  - Promotion_codes
            /v1/promotion_codes/{promotion_code}:
              get:
                description: >-
                  <p>Retrieves the promotion code with the given ID. In order to
                  retrieve a promotion code by the customer-facing
                  <code>code</code> use <a
                  href="/docs/api/promotion_codes/list">list</a> with the
                  desired <code>code</code>.</p>
                tags:
                  - V1
                  - Promotion_codes
                  - Promotion_code
              post:
                description: >-
                  <p>Updates the specified promotion code by setting the values
                  of the parameters passed. Most fields are, by design, not edi
                tags:
                  - V1
                  - Promotion_codes
                  - Promotion_co
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/promotion-codes-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/promotion-codes-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-quotes-api
    name: Stripe Quotes API
    description: >-
      A Quote is a way to model prices that you’d like to provide to a customer.
      Once accepted, it will automatically create an invoice, subscription or
      subscription schedule.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/quotes
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/quotes
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Quotes API
          paths:
            /v1/quotes:
              get:
                description: <p>Returns a list of your quotes.</p>
                tags:
                  - V1
                  - Quotes
              post:
                description: >-
                  <p>A quote models prices and services for a customer. Default
                  options for <code>header</code>, <code>description</code>,
                  <code>footer</code>, and <code>expires_at</code> can be set in
                  the dashboard via the <a
                  href="https://dashboard.stripe.com/settings/billing/quote">quote
                  template</a>.</p>
                tags:
                  - V1
                  - Quotes
            /v1/quotes/{quote}:
              get:
                description: <p>Retrieves the quote with the given ID.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
              post:
                description: <p>A quote models prices and services for a customer.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
            /v1/quotes/{quote}/accept:
              post:
                description: <p>Accepts the specified quote.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
            /v1/quotes/{quote}/cancel:
              post:
                description: <p>Cancels the quote.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
                  - Cancel
            /v1/quotes/{quote}/computed_upfront_line_items:
              get:
                description: >-
                  <p>When retrieving a quote, there is an includable <a
                  href="https://stripe.com/docs/api/quotes/object#quote_object-computed-upfront-line_items"><strong>computed.upfront.line_items</strong></a>
                  property containing the first handful of those items. There is
                  also a URL where you can retrieve the full (paginated) list of
                  upfront line items.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
                  - Cancel
                  - Computed_upfront_line_items
            /v1/quotes/{quote}/finalize:
              post:
                description: <p>Finalizes the quote.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
                  - Cancel
                  - Computed_upfront_line_items
                  - Finalize
            /v1/quotes/{quote}/line_items:
              get:
                description: >-
                  <p>When retrieving a quote, there is an includable
                  <strong>line_items</strong> property containing the first
                  handful of those items. There is also a URL where you can
                  retrieve the full (paginated) list of line items.</p>
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
                  - Cancel
                  - Computed_upfront_line_items
                  - Finalize
                  - Line_items
            /v1/quotes/{quote}/pdf:
              get:
                description: <p>Download the PDF for a finalized
                tags:
                  - V1
                  - Quotes
                  - Quote
                  - Accept
                  - Cancel
                  - Computed_upfront_line_items
                  - Finalize
                  - Line_items
                  - P
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-response-get-200-media-type-error
              message: JSON Media Type GET
            - code: openapi-response-get-200-schema-components-warn
              message: GET Response 200 Schema Components
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/quotes-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/quotes-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-radar-api
    name: Stripe Radar API
    description: >-
      Stripe Radar provides real-time fraud protection and requires no
      additional development time. Fraud professionals can add Radar for Fraud
      Teams to customize protection and get deeper insights.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/radar
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/radar
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Radar API
          paths:
            /v1/radar/early_fraud_warnings:
              get:
                description: <p>Returns a list of early fraud warnings.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
            /v1/radar/early_fraud_warnings/{early_fraud_warning}:
              get:
                description: >-
                  <p>Retrieves the details of an early fraud warning that has
                  previously been created. </p>


                  <p>Please refer to the <a
                  href="#early_fraud_warning_object">early fraud warning</a>
                  object reference for more details.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
            /v1/radar/value_list_items:
              get:
                description: >-
                  <p>Returns a list of <code>ValueListItem</code> objects. The
                  objects are sorted in descending order by creation date, with
                  the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
              post:
                description: >-
                  <p>Creates a new <code>ValueListItem</code> object, which is
                  added to the specified parent value list.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
            /v1/radar/value_list_items/{item}:
              delete:
                description: >-
                  <p>Deletes a <code>ValueListItem</code> object, removing it
                  from its parent value list.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
              get:
                description: <p>Retrieves a <code>ValueListItem</code> object.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
            /v1/radar/value_lists:
              get:
                description: >-
                  <p>Returns a list of <code>ValueList</code> objects. The
                  objects are sorted in descending order by creation date, with
                  the most recently created object appearing first.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
                  - Value_lists
              post:
                description: >-
                  <p>Creates a new <code>ValueList</code> object, which can then
                  be referenced in rules.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
                  - Value_lists
            /v1/radar/value_lists/{value_list}:
              delete:
                description: >-
                  <p>Deletes a <code>ValueList</code> object, also deleting any
                  items contained within the value list. To be deleted, a value
                  list must not be referenced in any rules.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
                  - Value_lists
                  - Value_list
              get:
                description: <p>Retrieves a <code>ValueList</code> object.</p>
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
                  - Value_lists
                  - Value_list
              post:
                description: >-
                  <p>Updates a <code>ValueList</code> object by setting the
                  values of the parameters passed. Any parameters not provided
                  will be left unchanged. Note that <code>item_type</code> is
                  immu
                tags:
                  - V1
                  - Radar
                  - Early_fraud_warnings
                  - Early_fraud_warning
                  - Value_list_items
                  - Item
                  - Value_lists
                  - Value_li
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/radar-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/radar-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-refunds-api
    name: Stripe Refunds API
    description: >-
      Refund objects allow you to refund a previously created charge that isn’t
      refunded yet. Funds are refunded to the credit or debit card that’s
      initially charged.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/refunds
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/refunds
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Refunds API
          paths:
            /v1/refunds:
              get:
                description: >-
                  <p>Returns a list of all refunds you created. We return the
                  refunds in sorted order, with the most recent refunds
                  appearing first The 10 most recent refunds are always
                  available by default on the Charge object.</p>
                tags:
                  - V1
                  - Refunds
              post:
                description: >-
                  <p>When you create a new refund, you must specify a Charge or
                  a PaymentIntent object on which to create it.</p>


                  <p>Creating a new refund will refund a charge that has
                  previously been created but not yet refunded.

                  Funds will be refunded to the credit or debit card that was
                  originally charged.</p>


                  <p>You can optionally refund only part of a charge.

                  You can do so multiple times, until the entire charge has been
                  refunded.</p>


                  <p>Once entirely refunded, a charge can’t be refunded again.

                  This method will raise an error when called on an
                  already-refunded charge,

                  or when trying to refund more money than is left on a
                  charge.</p>
                tags:
                  - V1
                  - Refunds
            /v1/refunds/{refund}:
              get:
                description: <p>Retrieves the details of an existing refund.</p>
                tags:
                  - V1
                  - Refunds
                  - Refund
              post:
                description: >-
                  <p>Updates the refund that you specify by setting the values
                  of the passed parameters. Any parameters that you don’t
                  provide remain unchanged.</p>


                  <p>This request only accepts <code>metadata</code> as an
                  argument.</p>
                tags:
                  - V1
                  - Refunds
                  - Refund
            /v1/refunds/{refund}/cancel:
              post:
                description: >-
                  <p>Cancels a refund with a status of
                  <code>requires_action</code>.</p>


                  <p>You can’t cancel refunds in other states. Only refunds for
                  payment methods that require customer action can enter the
                  <code>requires_action</code> 
                tags:
                  - V1
                  - Refunds
                  - Refund
                  - Canc
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/refunds-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/refunds-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-reporting-api
    name: Stripe Reporting API
    description: >-
      The financial reports in the Dashboard provide downloadable reports in CSV
      format for a variety of accounting and reconciliation tasks. These reports
      are also available through the API, so you can schedule them to run
      automatically or run them whenever you need to receive the associated
      report files for accounting purposes.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/reports/api
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/reports/api
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Reporting API
          paths:
            /v1/reporting/report_runs:
              get:
                description: >-
                  <p>Returns a list of Report Runs, with the most recent
                  appearing first.</p>
                tags:
                  - V1
                  - Reporting
                  - Report_runs
              post:
                description: >-
                  <p>Creates a new object and begin running the report. (Certain
                  report types require a <a
                  href="https://stripe.com/docs/keys#test-live-modes">live-mode
                  API key</a>.)</p>
                tags:
                  - V1
                  - Reporting
                  - Report_runs
            /v1/reporting/report_runs/{report_run}:
              get:
                description: <p>Retrieves the details of an existing Report Run.</p>
                tags:
                  - V1
                  - Reporting
                  - Report_runs
                  - Report_run
            /v1/reporting/report_types:
              get:
                description: <p>Returns a full list of Report Types.</p>
                tags:
                  - V1
                  - Reporting
                  - Report_runs
                  - Report_run
                  - Report_types
            /v1/reporting/report_types/{report_type}:
              get:
                description: >-
                  <p>Retrieves the details of a Report Type. (Certain report
                  types require a <a
                  href="https://stripe.com/docs/keys#test-live-modes">live-mode
                  API key
                tags:
                  - V1
                  - Reporting
                  - Report_runs
                  - Report_run
                  - Report_types
                  - Report_ty
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/reporting-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/reporting-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-reviews-api
    name: Stripe Reviews API
    description: >-
      Reviews can be used to supplement automated fraud detection with human
      expertise.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/radar/reviews
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/radar/reviews
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Reviews API
          paths:
            /v1/reviews:
              get:
                description: >-
                  <p>Returns a list of <code>Review</code> objects that have
                  <code>open</code> set to <code>true</code>. The objects are
                  sorted in descending order by creation date, with the most
                  recently created object appearing first.</p>
                tags:
                  - V1
                  - Reviews
            /v1/reviews/{review}:
              get:
                description: <p>Retrieves a <code>Review</code> object.</p>
                tags:
                  - V1
                  - Reviews
                  - Review
            /v1/reviews/{review}/approve:
              post:
                description: >-
                  <p>Approves a <code>Review</code> object, closing it and
                  removing it from the list of re
                tags:
                  - V1
                  - Reviews
                  - Review
                  - Appro
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/reviews-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/reviews-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-setup-api
    name: Stripe Setup API
    description: >-
      Use the Setup Intents API to set up a payment method for future payments.
      It’s similar to a payment, but no charge is created. Set up a payment
      method for future payments now.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/payments/setup-intents
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/payments/setup-intents
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Setup API
          paths:
            /v1/setup_attempts:
              get:
                description: >-
                  <p>Returns a list of SetupAttempts that associate with a
                  provided SetupIntent.</p>
                tags:
                  - V1
                  - Setup_attempts
            /v1/setup_intents:
              get:
                description: <p>Returns a list of SetupIntents.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
              post:
                description: >-
                  <p>Creates a SetupIntent object.</p>


                  <p>After you create the SetupIntent, attach a payment method
                  and <a href="/docs/api/setup_intents/confirm">confirm</a>

                  it to collect any required permissions to charge the payment
                  method later.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
            /v1/setup_intents/{intent}:
              get:
                description: >-
                  <p>Retrieves the details of a SetupIntent that has previously
                  been created. </p>


                  <p>Client-side retrieval using a publishable key is allowed
                  when the <code>client_secret</code> is provided in the query
                  string. </p>


                  <p>When retrieved with a publishable key, only a subset of
                  properties will be returned. Please refer to the <a
                  href="#setup_intent_object">SetupIntent</a> object reference
                  for more details.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
                  - Intent
              post:
                description: <p>Updates a SetupIntent object.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
                  - Intent
            /v1/setup_intents/{intent}/cancel:
              post:
                description: >-
                  <p>You can cancel a SetupIntent object when it’s in one of
                  these statuses: <code>requires_payment_method</code>,
                  <code>requires_confirmation</code>, or
                  <code>requires_action</code>. </p>


                  <p>After you cancel it, setup is abandoned and any operations
                  on the SetupIntent fail with an error.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
                  - Intent
                  - Cancel
            /v1/setup_intents/{intent}/confirm:
              post:
                description: >-
                  <p>Confirm that your customer intends to set up the current or

                  provided payment method. For example, you would confirm a
                  SetupIntent

                  when a customer hits the “Save” button on a payment method
                  management

                  page on your website.</p>


                  <p>If the selected payment method does not require any
                  additional

                  steps from the customer, the SetupIntent will transition to
                  the

                  <code>succeeded</code> status.</p>


                  <p>Otherwise, it will transition to the
                  <code>requires_action</code> status and

                  suggest additional actions via <code>next_action</code>. If
                  setup fails,

                  the SetupIntent will transition to the

                  <code>requires_payment_method</code> status or the
                  <code>canceled</code> status if the

                  confirmation limit is reached.</p>
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
                  - Intent
                  - Cancel
                  - Confirm
            /v1/setup_intents/{intent}/verify_microdeposits:
              post:
                description: <p>Verifies microdeposits on a SetupIntent o
                tags:
                  - V1
                  - Setup_attempts
                  - Setup_intents
                  - Intent
                  - Cancel
                  - Confirm
                  - Verify_microdeposi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/setup-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/setup-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-shipping-rates-api
    name: Stripe Shipping Rates API
    description: >-
      Shipping rates describe the price of shipping presented to your customers
      and applied to a purchase.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/shipping_rates
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/shipping_rates
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Shipping Rates API
          paths:
            /v1/shipping_rates:
              get:
                description: <p>Returns a list of your shipping rates.</p>
                tags:
                  - V1
                  - Shipping_rates
              post:
                description: <p>Creates a new shipping rate object.</p>
                tags:
                  - V1
                  - Shipping_rates
            /v1/shipping_rates/{shipping_rate_token}:
              get:
                description: <p>Returns the shipping rate object with the given ID.</p>
                tags:
                  - V1
                  - Shipping_rates
                  - Shipping_rate_token
              post:
                description: <p>Updates an existing shipping rate o
                tags:
                  - V1
                  - Shipping_rates
                  - Shipping_rate_tok
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/shipping-rates-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/shipping-rates-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-sigma-api
    name: Stripe Sigma API
    description: >-
      If you have scheduled a Sigma query, you’ll receive a
      sigma.scheduled_query_run.created webhook each time the query runs. The
      webhook contains a ScheduledQueryRun object, which you can use to retrieve
      the query results.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/sigma/scheduled_queries
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/sigma/scheduled_queries
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Sigma API
          paths:
            /v1/sigma/scheduled_query_runs:
              get:
                description: <p>Returns a list of scheduled query runs.</p>
                tags:
                  - V1
                  - Sigma
                  - Scheduled_query_runs
            /v1/sigma/scheduled_query_runs/{scheduled_query_run}:
              get:
                description: <p>Retrieves the details of an scheduled que
                tags:
                  - V1
                  - Sigma
                  - Scheduled_query_runs
                  - Scheduled_query_r
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/sigma-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/sigma-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-sources-api
    name: Stripe Sources API
    description: >-
      Source objects allow you to accept a variety of payment methods. They
      represent a customer’s payment instrument, and can be used with the Stripe
      API just like a Card object once chargeable, they can be charged, or can
      be attached to customers.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/sources
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/sources
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Sources API
          paths:
            /v1/sources:
              post:
                description: <p>Creates a new source object.</p>
                tags:
                  - V1
                  - Sources
            /v1/sources/{source}:
              get:
                description: >-
                  <p>Retrieves an existing source object. Supply the unique
                  source ID from a source creation request and Stripe will
                  return the corresponding up-to-date source object
                  information.</p>
                tags:
                  - V1
                  - Sources
                  - Source
              post:
                description: >-
                  <p>Updates the specified source by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unchanged.</p>


                  <p>This request accepts the <code>metadata</code> and
                  <code>owner</code> as arguments. It is also possible to update
                  type specific information for selected payment methods. Please
                  refer to our <a href="/docs/sources">payment method guides</a>
                  for more detail.</p>
                tags:
                  - V1
                  - Sources
                  - Source
            /v1/sources/{source}/mandate_notifications/{mandate_notification}:
              get:
                description: <p>Retrieves a new Source MandateNotification.</p>
                tags:
                  - V1
                  - Sources
                  - Source
                  - Mandate_notifications
                  - Mandate_notification
            /v1/sources/{source}/source_transactions:
              get:
                description: <p>List source transactions for a given source.</p>
                tags:
                  - V1
                  - Sources
                  - Source
                  - Mandate_notifications
                  - Mandate_notification
                  - Source_transactions
            /v1/sources/{source}/source_transactions/{source_transaction}:
              get:
                description: >-
                  <p>Retrieve an existing source transaction object. Supply the
                  unique source ID from a source creation request and the source
                  transaction ID and Stripe will return the corresponding
                  up-to-date source object information.</p>
                tags:
                  - V1
                  - Sources
                  - Source
                  - Mandate_notifications
                  - Mandate_notification
                  - Source_transactions
                  - Source_transaction
            /v1/sources/{source}/verify:
              post:
                description: <p>Verify a given s
                tags:
                  - V1
                  - Sources
                  - Source
                  - Mandate_notifications
                  - Mandate_notification
                  - Source_transactions
                  - Source_transaction
                  - Veri
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: >-
                '#/components/schemas/source_type_ach_credit_transfer' does not
                exist
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/sources-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/sources-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-subscription-api
    name: Stripe Subscription API
    description: Subscriptions allow you to charge a customer on a recurring basis.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/subscriptions
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/subscriptions
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Subscription API
          paths:
            /v1/subscription_items:
              get:
                description: >-
                  <p>Returns a list of your subscription items for a given
                  subscription.</p>
                tags:
                  - V1
                  - Subscription_items
              post:
                description: >-
                  <p>Adds a new item to an existing subscription. No existing
                  items will be changed or replaced.</p>
                tags:
                  - V1
                  - Subscription_items
            /v1/subscription_items/{item}:
              delete:
                description: >-
                  <p>Deletes an item from the subscription. Removing a
                  subscription item from a subscription will not cancel the
                  subscription.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
              get:
                description: <p>Retrieves the subscription item with the given ID.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
              post:
                description: >-
                  <p>Updates the plan or quantity of an item on a current
                  subscription.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
            /v1/subscription_items/{subscription_item}/usage_record_summaries:
              get:
                description: >-
                  <p>For the specified subscription item, returns a list of
                  summary objects. Each object in the list provides usage
                  information that’s been summarized from multiple usage records
                  and over a subscription billing period (e.g., 15 usage records
                  in the month of September).</p>


                  <p>The list is sorted in reverse-chronological order (newest
                  first). The first list item represents the most current usage
                  period that hasn’t ended yet. Since new usage records can
                  still be added, the returned summary information for the
                  subscription item’s ID should be seen as unstable until the
                  subscription billing period ends.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
            /v1/subscription_items/{subscription_item}/usage_records:
              post:
                description: >-
                  <p>Creates a usage record for a specified subscription item
                  and date, and fills it with a quantity.</p>


                  <p>Usage records provide <code>quantity</code> information
                  that Stripe uses to track how much a customer is using your
                  service. With usage information and the pricing model set up
                  by the <a
                  href="https://stripe.com/docs/billing/subscriptions/metered-billing">metered
                  billing</a> plan, Stripe helps you send accurate invoices to
                  your customers.</p>


                  <p>The default calculation for usage is to add up all the
                  <code>quantity</code> values of the usage records within a
                  billing period. You can change this default behavior with the
                  billing plan’s <code>aggregate_usage</code> <a
                  href="/docs/api/plans/create#create_plan-aggregate_usage">parameter</a>.
                  When there is more than one usage record with the same
                  timestamp, Stripe adds the <code>quantity</code> values
                  together. In most cases, this is the desired resolution,
                  however, you can change this behavior with the
                  <code>action</code> parameter.</p>


                  <p>The default pricing model for metered billing is <a
                  href="/docs/api/plans/object#plan_object-billing_scheme">per-unit
                  pricing</a>. For finer granularity, you can configure metered
                  billing to have a <a
                  href="https://stripe.com/docs/billing/subscriptions/tiers">tiered
                  pricing</a> model.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
            /v1/subscription_schedules:
              get:
                description: <p>Retrieves the list of your subscription schedules.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
              post:
                description: >-
                  <p>Creates a new subscription schedule object. Each customer
                  can have up to 500 active or scheduled subscriptions.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
            /v1/subscription_schedules/{schedule}:
              get:
                description: >-
                  <p>Retrieves the details of an existing subscription schedule.
                  You only need to supply the unique subscription schedule
                  identifier that was returned upon subscription schedule
                  creation.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
              post:
                description: <p>Updates an existing subscription schedule.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
            /v1/subscription_schedules/{schedule}/cancel:
              post:
                description: >-
                  <p>Cancels a subscription schedule and its associated
                  subscription immediately (if the subscription schedule has an
                  active subscription). A subscription schedule can only be
                  canceled if its status is <code>not_started</code> or
                  <code>active</code>.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
            /v1/subscription_schedules/{schedule}/release:
              post:
                description: >-
                  <p>Releases the subscription schedule immediately, which will
                  stop scheduling of its phases, but leave any existing
                  subscription in place. A schedule can only be released if its
                  status is <code>not_started</code> or <code>active</code>. If
                  the subscription schedule is currently associated with a
                  subscription, releasing it will remove its
                  <code>subscription</code> property and set the subscription’s
                  ID to the <code>released_subscription</code> property.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
            /v1/subscriptions:
              get:
                description: >-
                  <p>By default, returns a list of subscriptions that have not
                  been canceled. In order to list canceled subscriptions,
                  specify <code>status=canceled</code>.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
              post:
                description: >-
                  <p>Creates a new subscription on an existing customer. Each
                  customer can have up to 500 active or scheduled
                  subscriptions.</p>


                  <p>When you create a subscription with
                  <code>collection_method=charge_automatically</code>, the first
                  invoice is finalized as part of the request.

                  The <code>payment_behavior</code> parameter determines the
                  exact behavior of the initial payment.</p>


                  <p>To start subscriptions where the first invoice always
                  begins in a <code>draft</code> status, use <a
                  href="/docs/billing/subscriptions/subscription-schedules#managing">subscription
                  schedules</a> instead.

                  Schedules provide the flexibility to model more complex
                  billing configurations that change over time.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
            /v1/subscriptions/search:
              get:
                description: >-
                  <p>Search for subscriptions you’ve previously created using
                  Stripe’s <a href="/docs/search#search-query-language">Search
                  Query Language</a>.

                  Don’t use search in read-after-write flows where strict
                  consistency is necessary. Under normal operating

                  conditions, data is searchable in less than a minute.
                  Occasionally, propagation of new or updated data can be up

                  to an hour behind during outages. Search functionality is not
                  available to merchants in India.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
            /v1/subscriptions/{subscription_exposed_id}:
              delete:
                description: >-
                  <p>Cancels a customer’s subscription immediately. The customer
                  will not be charged again for the subscription.</p>


                  <p>Note, however, that any pending invoice items that you’ve
                  created will still be charged for at the end of the period,
                  unless manually <a href="#delete_invoiceitem">deleted</a>. If
                  you’ve set the subscription to cancel at the end of the
                  period, any pending prorations will also be left in place and
                  collected at the end of the period. But if the subscription is
                  set to cancel immediately, pending prorations will be
                  removed.</p>


                  <p>By default, upon subscription cancellation, Stripe will
                  stop automatic collection of all finalized invoices for the
                  customer. This is intended to prevent unexpected payment
                  attempts after the customer has canceled a subscription.
                  However, you can resume automatic collection of the invoices
                  manually after subscription cancellation to have us proceed.
                  Or, you could check for unpaid invoices before allowing the
                  customer to cancel the subscription at all.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
                  - Subscription_exposed_id
              get:
                description: <p>Retrieves the subscription with the given ID.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
                  - Subscription_exposed_id
              post:
                description: >-
                  <p>Updates an existing subscription to match the specified
                  parameters.

                  When changing prices or quantities, we optionally prorate the
                  price we charge next month to make up for any price changes.

                  To preview how the proration is calculated, use the <a
                  href="/docs/api/invoices/upcoming">upcoming invoice</a>
                  endpoint.</p>


                  <p>By default, we prorate subscription changes. For example,
                  if a customer signs up on May 1 for a <currency>100</currency>
                  price, they’ll be billed <currency>100</currency> immediately.
                  If on May 15 they switch to a <currency>200</currency> price,
                  then on June 1 they’ll be billed <currency>250</currency>
                  (<currency>200</currency> for a renewal of her subscription,
                  plus a <currency>50</currency> prorating adjustment for half
                  of the previous month’s <currency>100</currency> difference).
                  Similarly, a downgrade generates a credit that is applied to
                  the next invoice. We also prorate when you make quantity
                  changes.</p>


                  <p>Switching prices does not normally change the billing date
                  or generate an immediate charge unless:</p>


                  <ul>

                  <li>The billing interval is changed (for example, from monthly
                  to yearly).</li>

                  <li>The subscription moves from free to paid, or paid to
                  free.</li>

                  <li>A trial starts or ends.</li>

                  </ul>


                  <p>In these cases, we apply a credit for the unused time on
                  the previous price, immediately charge the customer using the
                  new price, and reset the billing date.</p>


                  <p>If you want to charge for an upgrade immediately, pass
                  <code>proration_behavior</code> as <code>always_invoice</code>
                  to create prorations, automatically invoice the customer for
                  those proration adjustments, and attempt to collect payment.
                  If you pass <code>create_prorations</code>, the prorations are
                  created but not automatically invoiced. If you want to bill
                  the customer for the prorations before the subscription’s
                  renewal date, you need to manually <a
                  href="/docs/api/invoices/create">invoice the customer</a>.</p>


                  <p>If you don’t want to prorate, set the
                  <code>proration_behavior</code> option to <code>none</code>.
                  With this option, the customer is billed
                  <currency>100</currency> on May 1 and <currency>200</currency>
                  on June 1. Similarly, if you set
                  <code>proration_behavior</code> to <code>none</code> when
                  switching between different billing intervals (for example,
                  from monthly to yearly), we don’t generate any credits for the
                  old subscription’s unused time. We still reset the billing
                  date and bill immediately for the new subscription.</p>


                  <p>Updating the quantity on a subscription many times in an
                  hour may result in <a href="/docs/rate-limits">rate
                  limiting</a>. If you need to bill for a frequently changing
                  quantity, consider integrating <a
                  href="/docs/billing/subscriptions/usage-based">usage-based
                  billing</a> instead.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
                  - Subscription_exposed_id
            /v1/subscriptions/{subscription_exposed_id}/discount:
              delete:
                description: >-
                  <p>Removes the currently applied discount on a
                  subscription.</p>
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
                  - Subscription_exposed_id
                  - Discount
            /v1/subscriptions/{subscription}/resume:
              post:
                description: >-
                  <p>Initiates resumption of a paused subscription, optionally
                  resetting the billing cycle anchor and creating prorations. If
                  a resumption invoice is generated, it must be paid or marked
                  uncollectible before the subscription will be unpaused. If
                  payment succeeds the subscription will become
                  <code>active</code>, and if payment fails the subscription
                  will be <code>past_due</code>. The resumption invoice will
                  void automatically if not paid by the expiration
                tags:
                  - V1
                  - Subscription_items
                  - Item
                  - Subscription_item
                  - Usage_record_summaries
                  - Usage_records
                  - Subscription_schedules
                  - Schedule
                  - Cancel
                  - Release
                  - Subscriptions
                  - Search
                  - Subscription_exposed_id
                  - Discount
                  - Subscription
                  - Resu
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/subscription-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/subscription-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-tax-api
    name: Stripe Tax API
    description: >-
      Automate sales tax, VAT, and GST compliance on all your transactions—low
      or no code integrations available.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/tax
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/tax
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Tax API
          paths:
            /v1/tax/calculations:
              post:
                description: >-
                  <p>Calculates tax based on input and returns a Tax
                  <code>Calculation</code> object.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
            /v1/tax/calculations/{calculation}/line_items:
              get:
                description: >-
                  <p>Retrieves the line items of a persisted tax calculation as
                  a collection.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
            /v1/tax/registrations:
              get:
                description: >-
                  <p>Returns a list of Tax <code>Registration</code>
                  objects.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
              post:
                description: <p>Creates a new Tax <code>Registration</code> object.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
            /v1/tax/registrations/{id}:
              post:
                description: >-
                  <p>Updates an existing Tax <code>Registration</code>
                  object.</p>


                  <p>A registration cannot be deleted after it has been created.
                  If you wish to end a registration you may do so by setting
                  <code>expires_at</code>.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
            /v1/tax/settings:
              get:
                description: <p>Retrieves Tax <code>Settings</code> for a merchant.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
              post:
                description: >-
                  <p>Updates Tax <code>Settings</code> parameters used in tax
                  calculations. All parameters are editable but none can be
                  removed once set.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
            /v1/tax/transactions/create_from_calculation:
              post:
                description: >-
                  <p>Creates a Tax <code>Transaction</code> from a
                  calculation.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
            /v1/tax/transactions/create_reversal:
              post:
                description: >-
                  <p>Partially or fully reverses a previously created
                  <code>Transaction</code>.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
            /v1/tax/transactions/{transaction}:
              get:
                description: <p>Retrieves a Tax <code>Transaction</code> object.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
            /v1/tax/transactions/{transaction}/line_items:
              get:
                description: >-
                  <p>Retrieves the line items of a committed standalone
                  transaction as a collection.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
            /v1/tax_codes:
              get:
                description: >-
                  <p>A list of <a
                  href="https://stripe.com/docs/tax/tax-categories">all tax
                  codes available</a> to add to Products in order to allow
                  specific tax calculations.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
            /v1/tax_codes/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an existing tax code. Supply the
                  unique tax code ID and Stripe will return the corresponding
                  tax code information.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
            /v1/tax_rates:
              get:
                description: >-
                  <p>Returns a list of your tax rates. Tax rates are returned
                  sorted by creation date, with the most recently created tax
                  rates appearing first.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
                  - Tax_rates
              post:
                description: <p>Creates a new tax rate.</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
                  - Tax_rates
            /v1/tax_rates/{tax_rate}:
              get:
                description: <p>Retrieves a tax rate with the given ID</p>
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
                  - Tax_rates
                  - Tax_rate
              post:
                description: <p>Updates an existing tax
                tags:
                  - V1
                  - Tax
                  - Calculations
                  - Calculation
                  - Line_items
                  - Registrations
                  - Id
                  - Settings
                  - Transactions
                  - Create_from_calculation
                  - Create_reversal
                  - Transaction
                  - Tax_codes
                  - Tax_rates
                  - Tax_ra
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
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
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: >-
                '#/components/schemas/tax_product_resource_customer_details'
                does not exist
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/tax-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/tax-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-terminal-api
    name: Stripe Terminal API
    description: >-
      Use Stripe Terminal to accept in-person payments and extend Stripe
      payments to your point of sale.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/terminal
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/terminal
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Terminal API
          paths:
            /v1/terminal/configurations:
              get:
                description: <p>Returns a list of <code>Configuration</code> objects.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
              post:
                description: <p>Creates a new <code>Configuration</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
            /v1/terminal/configurations/{configuration}:
              delete:
                description: <p>Deletes a <code>Configuration</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
              get:
                description: <p>Retrieves a <code>Configuration</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
              post:
                description: <p>Updates a new <code>Configuration</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
            /v1/terminal/connection_tokens:
              post:
                description: >-
                  <p>To connect to a reader the Stripe Terminal SDK needs to
                  retrieve a short-lived connection token from Stripe, proxied
                  through your server. On your backend, add an endpoint that
                  creates and returns a connection token.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
            /v1/terminal/locations:
              get:
                description: <p>Returns a list of <code>Location</code> objects.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
              post:
                description: >-
                  <p>Creates a new <code>Location</code> object.

                  For further details, including which address fields are
                  required in each country, see the <a
                  href="/docs/terminal/fleet/locations">Manage locations</a>
                  guide.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
            /v1/terminal/locations/{location}:
              delete:
                description: <p>Deletes a <code>Location</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
              get:
                description: <p>Retrieves a <code>Location</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
              post:
                description: >-
                  <p>Updates a <code>Location</code> object by setting the
                  values of the parameters passed. Any parameters not provided
                  will be left unchanged.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
            /v1/terminal/readers:
              get:
                description: <p>Returns a list of <code>Reader</code> objects.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
              post:
                description: <p>Creates a new <code>Reader</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
            /v1/terminal/readers/{reader}:
              delete:
                description: <p>Deletes a <code>Reader</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
              get:
                description: <p>Retrieves a <code>Reader</code> object.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
              post:
                description: >-
                  <p>Updates a <code>Reader</code> object by setting the values
                  of the parameters passed. Any parameters not provided will be
                  left unchanged.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
            /v1/terminal/readers/{reader}/cancel_action:
              post:
                description: <p>Cancels the current reader action.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
                  - Cancel_action
            /v1/terminal/readers/{reader}/process_payment_intent:
              post:
                description: <p>Initiates a payment flow on a Reader.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
                  - Cancel_action
                  - Process_payment_intent
            /v1/terminal/readers/{reader}/process_setup_intent:
              post:
                description: <p>Initiates a setup intent flow on a Reader.</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
                  - Cancel_action
                  - Process_payment_intent
                  - Process_setup_intent
            /v1/terminal/readers/{reader}/refund_payment:
              post:
                description: <p>Initiates a refund on a Reader</p>
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
                  - Cancel_action
                  - Process_payment_intent
                  - Process_setup_intent
                  - Refund_payment
            /v1/terminal/readers/{reader}/set_reader_display:
              post:
                description: <p>Sets reader display to show cart de
                tags:
                  - V1
                  - Terminal
                  - Configurations
                  - Configuration
                  - Connection_tokens
                  - Locations
                  - Location
                  - Readers
                  - Reader
                  - Cancel_action
                  - Process_payment_intent
                  - Process_setup_intent
                  - Refund_payment
                  - Set_reader_displ
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: openapi-request-body-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-request-body-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-request-body-schema-properties-format-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-request-body-schema-properties-names-pascal-case-error
              message: Request Body Schema Property Names Pascal Case
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-response-get-200-schema-components-warn
              message: GET Response 200 Schema Components
            - code: openapi-request-body-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/terminal-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/terminal-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-test-helpers-api
    name: Stripe Test Helpers API
    description: >-
      Stripe provides a number of resources for testing your integration. Make
      sure to test the following use cases before launch, and use our Postman
      collection to make the testing process simpler.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/implementation-guides/billing/testing
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/implementation-guides/billing/testing
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Test Helpers API
          paths:
            /v1/test_helpers/customers/{customer}/fund_cash_balance:
              post:
                description: <p>Create an incoming testmode bank transfer</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
            /v1/test_helpers/issuing/authorizations:
              post:
                description: <p>Create a test-mode authorization.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
            /v1/test_helpers/issuing/authorizations/{authorization}/capture:
              post:
                description: <p>Capture a test-mode authorization.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
            /v1/test_helpers/issuing/authorizations/{authorization}/expire:
              post:
                description: <p>Expire a test-mode Authorization.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
            /v1/test_helpers/issuing/authorizations/{authorization}/increment:
              post:
                description: <p>Increment a test-mode Authorization.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
            /v1/test_helpers/issuing/authorizations/{authorization}/reverse:
              post:
                description: <p>Reverse a test-mode Authorization.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
            /v1/test_helpers/issuing/cards/{card}/shipping/deliver:
              post:
                description: >-
                  <p>Updates the shipping status of the specified Issuing
                  <code>Card</code> object to <code>delivered</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
            /v1/test_helpers/issuing/cards/{card}/shipping/fail:
              post:
                description: >-
                  <p>Updates the shipping status of the specified Issuing
                  <code>Card</code> object to <code>failure</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
            /v1/test_helpers/issuing/cards/{card}/shipping/return:
              post:
                description: >-
                  <p>Updates the shipping status of the specified Issuing
                  <code>Card</code> object to <code>returned</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
            /v1/test_helpers/issuing/cards/{card}/shipping/ship:
              post:
                description: >-
                  <p>Updates the shipping status of the specified Issuing
                  <code>Card</code> object to <code>shipped</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
            /v1/test_helpers/issuing/transactions/create_force_capture:
              post:
                description: >-
                  <p>Allows the user to capture an arbitrary amount, also known
                  as a forced capture.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
            /v1/test_helpers/issuing/transactions/create_unlinked_refund:
              post:
                description: >-
                  <p>Allows the user to refund an arbitrary amount, also known
                  as a unlinked refund.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
            /v1/test_helpers/issuing/transactions/{transaction}/refund:
              post:
                description: <p>Refund a test-mode Transaction.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
            /v1/test_helpers/refunds/{refund}/expire:
              post:
                description: >-
                  <p>Expire a refund with a status of
                  <code>requires_action</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
            /v1/test_helpers/terminal/readers/{reader}/present_payment_method:
              post:
                description: >-
                  <p>Presents a payment method on a simulated reader. Can be
                  used to simulate accepting a payment, saving a card or
                  refunding a transaction.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
            /v1/test_helpers/test_clocks:
              get:
                description: <p>Returns a list of your test clocks.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
              post:
                description: >-
                  <p>Creates a new test clock that can be attached to new
                  customers and quotes.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
            /v1/test_helpers/test_clocks/{test_clock}:
              delete:
                description: <p>Deletes a test clock.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
              get:
                description: <p>Retrieves a test clock.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
            /v1/test_helpers/test_clocks/{test_clock}/advance:
              post:
                description: >-
                  <p>Starts advancing a test clock to a specified time in the
                  future. Advancement is done when status changes to
                  <code>Ready</code>.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
            /v1/test_helpers/treasury/inbound_transfers/{id}/fail:
              post:
                description: >-
                  <p>Transitions a test mode created InboundTransfer to the
                  <code>failed</code> status. The InboundTransfer must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
            /v1/test_helpers/treasury/inbound_transfers/{id}/return:
              post:
                description: >-
                  <p>Marks the test mode InboundTransfer object as returned and
                  links the InboundTransfer to a ReceivedDebit. The
                  InboundTransfer must already be in the <code>succeeded</code>
                  state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
            /v1/test_helpers/treasury/inbound_transfers/{id}/succeed:
              post:
                description: >-
                  <p>Transitions a test mode created InboundTransfer to the
                  <code>succeeded</code> status. The InboundTransfer must
                  already be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
            /v1/test_helpers/treasury/outbound_payments/{id}/fail:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundPayment to the
                  <code>failed</code> status. The OutboundPayment must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
            /v1/test_helpers/treasury/outbound_payments/{id}/post:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundPayment to the
                  <code>posted</code> status. The OutboundPayment must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
            /v1/test_helpers/treasury/outbound_payments/{id}/return:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundPayment to the
                  <code>returned</code> status. The OutboundPayment must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
            /v1/test_helpers/treasury/outbound_transfers/{outbound_transfer}/fail:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundTransfer to the
                  <code>failed</code> status. The OutboundTransfer must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
                  - Outbound_transfers
                  - Outbound_transfer
            /v1/test_helpers/treasury/outbound_transfers/{outbound_transfer}/post:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundTransfer to the
                  <code>posted</code> status. The OutboundTransfer must already
                  be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
                  - Outbound_transfers
                  - Outbound_transfer
            /v1/test_helpers/treasury/outbound_transfers/{outbound_transfer}/return:
              post:
                description: >-
                  <p>Transitions a test mode created OutboundTransfer to the
                  <code>returned</code> status. The OutboundTransfer must
                  already be in the <code>processing</code> state.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
                  - Outbound_transfers
                  - Outbound_transfer
            /v1/test_helpers/treasury/received_credits:
              post:
                description: >-
                  <p>Use this endpoint to simulate a test mode ReceivedCredit
                  initiated by a third party. In live mode, you can’t directly
                  create ReceivedCredits initiated by third parties.</p>
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
            /v1/test_helpers/treasury/received_debits:
              post:
                description: >-
                  <p>Use this endpoint to simulate a test mode ReceivedDebit
                  initiated by a third party. In live mode, you can’t directly
                  create ReceivedDebits initiated by third pa
                tags:
                  - V1
                  - Test_helpers
                  - Customers
                  - Customer
                  - Fund_cash_balance
                  - Issuing
                  - Authorizations
                  - Authorization
                  - Capture
                  - Expire
                  - Increment
                  - Reverse
                  - Cards
                  - Card
                  - Shipping
                  - Deliver
                  - Fail
                  - Return
                  - Ship
                  - Transactions
                  - Create_force_capture
                  - Create_unlinked_refund
                  - Transaction
                  - Refund
                  - Refunds
                  - Terminal
                  - Readers
                  - Reader
                  - Present_payment_method
                  - Test_clocks
                  - Test_clock
                  - Advance
                  - Treasury
                  - Inbound_transfers
                  - Id
                  - Succeed
                  - Outbound_payments
                  - Post
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-schema-properties-names-camel-case-error
              message: Request Body Schema Property Names Camel Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-request-body-schema-properties-type-info
              message: Request Body Schema Properties Format
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: >-
                '#/components/schemas/customer_balance_resource_cash_balance_transaction_resource_adjusted_for_overdraft'
                does not exist
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/test-helpers-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/test-helpers-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-tokens-api
    name: Stripe Tokens API
    description: >-
      Tokenization is the process Stripe uses to collect sensitive card or bank
      account details, or personally identifiable information (PII), directly
      from your customers in a secure manner. A token representing this
      information is returned to your server to use. Use our recommended
      payments integrations to perform this process on the client-side. This
      guarantees that no sensitive card data touches your server, and allows
      your integration to operate in a PCI-compliant way.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/tokens
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/tokens
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Tokens API
          paths:
            /v1/tokens:
              post:
                description: >-
                  <p>Creates a single-use token that represents a bank account’s
                  details.

                  You can use this token with any API method in place of a bank
                  account dictionary. You can only use this token once. To do
                  so, attach it to a <a href="#accounts">Custom account</a>.</p>
                tags:
                  - V1
                  - Tokens
            /v1/tokens/{token}:
              get:
                description: <p>Retrieves the token with the giv
                tags:
                  - V1
                  - Tokens
                  - Tok
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/bank_account'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/tokens-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/tokens-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-topups-api
    name: Stripe Topups API
    description: >-
      To top up your Stripe balance, you create a top-up object. You can
      retrieve individual top-ups, as well as list all top-ups. Top-ups are
      identified by a unique, random ID.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/topups
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/topups
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Topups API
          paths:
            /v1/topups:
              get:
                description: <p>Returns a list of top-ups.</p>
                tags:
                  - V1
                  - Topups
              post:
                description: <p>Top up the balance of an account</p>
                tags:
                  - V1
                  - Topups
            /v1/topups/{topup}:
              get:
                description: >-
                  <p>Retrieves the details of a top-up that has previously been
                  created. Supply the unique top-up ID that was returned from
                  your previous request, and Stripe will return the
                  corresponding top-up information.</p>
                tags:
                  - V1
                  - Topups
                  - Topup
              post:
                description: >-
                  <p>Updates the metadata of a top-up. Other top-up details are
                  not editable by design.</p>
                tags:
                  - V1
                  - Topups
                  - Topup
            /v1/topups/{topup}/cancel:
              post:
                description: <p>Cancels a top-up. Only pending top-ups can be can
                tags:
                  - V1
                  - Topups
                  - Topup
                  - Canc
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/topups-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/topups-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-transfers-api
    name: Stripe Transfers API
    description: >-
      A Transfer object is created when you move funds between Stripe accounts
      as part of Connect.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/transfers
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/transfers
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Transfers API
          paths:
            /v1/transfers:
              get:
                description: >-
                  <p>Returns a list of existing transfers sent to connected
                  accounts. The transfers are returned in sorted order, with the
                  most recently created transfers appearing first.</p>
                tags:
                  - V1
                  - Transfers
              post:
                description: >-
                  <p>To send funds from your Stripe account to a connected
                  account, you create a new transfer object. Your <a
                  href="#balance">Stripe balance</a> must be able to cover the
                  transfer amount, or you’ll receive an “Insufficient Funds”
                  error.</p>
                tags:
                  - V1
                  - Transfers
            /v1/transfers/{id}/reversals:
              get:
                description: >-
                  <p>You can see a list of the reversals belonging to a specific
                  transfer. Note that the 10 most recent reversals are always
                  available by default on the transfer object. If you need more
                  than those 10, you can use this API method and the
                  <code>limit</code> and <code>starting_after</code> parameters
                  to page through additional reversals.</p>
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
              post:
                description: >-
                  <p>When you create a new reversal, you must specify a transfer
                  to create it on.</p>


                  <p>When reversing transfers, you can optionally reverse part
                  of the transfer. You can do so as many times as you wish until
                  the entire transfer has been reversed.</p>


                  <p>Once entirely reversed, a transfer can’t be reversed again.
                  This method will return an error when called on an
                  already-reversed transfer, or when trying to reverse more
                  money than is left on a transfer.</p>
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
            /v1/transfers/{transfer}:
              get:
                description: >-
                  <p>Retrieves the details of an existing transfer. Supply the
                  unique transfer ID from either a transfer creation request or
                  the transfer list, and Stripe will return the corresponding
                  transfer information.</p>
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
                  - Transfer
              post:
                description: >-
                  <p>Updates the specified transfer by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unchanged.</p>


                  <p>This request accepts only metadata as an argument.</p>
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
                  - Transfer
            /v1/transfers/{transfer}/reversals/{id}:
              get:
                description: >-
                  <p>By default, you can see the 10 most recent reversals stored
                  directly on the transfer object, but you can also retrieve
                  details about a specific reversal stored on the transfer.</p>
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
                  - Transfer
              post:
                description: >-
                  <p>Updates the specified reversal by setting the values of the
                  parameters passed. Any parameters not provided will be left
                  unchanged.</p>


                  <p>This request only accepts metadata and description as argu
                tags:
                  - V1
                  - Transfers
                  - Id
                  - Reversals
                  - Transf
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-in-info
              message: Parameters In
            - code: openapi-parameters-name-info
              message: Parameter Name
            - code: openapi-parameters-required-info
              message: Parameter has a required property.
            - code: openapi-parameters-schema-info
              message: Parameter Schema Type
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-schema-type-info
              message: Parameter Schema Type
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/transfers-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/transfers-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-treasury-api
    name: Stripe Treasury API
    description: >-
      Stripe Treasury is a banking-as-a-service API that lets you embed
      financial services in your product. With Stripe’s API, you can enable
      businesses to hold funds, pay bills, earn yield, and manage their cash
      flow. Many users build Stripe Issuing in conjunction with Stripe Treasury
      to attach cards to spend funds in the account.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/treasury
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/treasury
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Treasury API
          paths:
            /v1/treasury/credit_reversals:
              get:
                description: <p>Returns a list of CreditReversals.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
              post:
                description: >-
                  <p>Reverses a ReceivedCredit and creates a CreditReversal
                  object.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
            /v1/treasury/credit_reversals/{credit_reversal}:
              get:
                description: >-
                  <p>Retrieves the details of an existing CreditReversal by
                  passing the unique CreditReversal ID from either the
                  CreditReversal creation request or CreditReversal list</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
            /v1/treasury/debit_reversals:
              get:
                description: <p>Returns a list of DebitReversals.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
              post:
                description: >-
                  <p>Reverses a ReceivedDebit and creates a DebitReversal
                  object.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
            /v1/treasury/debit_reversals/{debit_reversal}:
              get:
                description: <p>Retrieves a DebitReversal object.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
            /v1/treasury/financial_accounts:
              get:
                description: <p>Returns a list of FinancialAccounts.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
              post:
                description: >-
                  <p>Creates a new FinancialAccount. For now, each connected
                  account can only have one FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
            /v1/treasury/financial_accounts/{financial_account}:
              get:
                description: <p>Retrieves the details of a FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
              post:
                description: <p>Updates the details of a FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
            /v1/treasury/financial_accounts/{financial_account}/features:
              get:
                description: >-
                  <p>Retrieves Features information associated with the
                  FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
              post:
                description: >-
                  <p>Updates the Features associated with a
                  FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
            /v1/treasury/inbound_transfers:
              get:
                description: >-
                  <p>Returns a list of InboundTransfers sent from the specified
                  FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
              post:
                description: <p>Creates an InboundTransfer.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
            /v1/treasury/inbound_transfers/{id}:
              get:
                description: <p>Retrieves the details of an existing InboundTransfer.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
            /v1/treasury/inbound_transfers/{inbound_transfer}/cancel:
              post:
                description: <p>Cancels an InboundTransfer.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
            /v1/treasury/outbound_payments:
              get:
                description: >-
                  <p>Returns a list of OutboundPayments sent from the specified
                  FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
              post:
                description: <p>Creates an OutboundPayment.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
            /v1/treasury/outbound_payments/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an existing OutboundPayment by
                  passing the unique OutboundPayment ID from either the
                  OutboundPayment creation request or OutboundPayment list.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
            /v1/treasury/outbound_payments/{id}/cancel:
              post:
                description: <p>Cancel an OutboundPayment.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
            /v1/treasury/outbound_transfers:
              get:
                description: >-
                  <p>Returns a list of OutboundTransfers sent from the specified
                  FinancialAccount.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
              post:
                description: <p>Creates an OutboundTransfer.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
            /v1/treasury/outbound_transfers/{outbound_transfer}:
              get:
                description: >-
                  <p>Retrieves the details of an existing OutboundTransfer by
                  passing the unique OutboundTransfer ID from either the
                  OutboundTransfer creation request or OutboundTransfer
                  list.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
            /v1/treasury/outbound_transfers/{outbound_transfer}/cancel:
              post:
                description: >-
                  <p>An OutboundTransfer can be canceled if the funds have not
                  yet been paid out.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
            /v1/treasury/received_credits:
              get:
                description: <p>Returns a list of ReceivedCredits.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
            /v1/treasury/received_credits/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an existing ReceivedCredit by
                  passing the unique ReceivedCredit ID from the ReceivedCredit
                  list.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
            /v1/treasury/received_debits:
              get:
                description: <p>Returns a list of ReceivedDebits.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
            /v1/treasury/received_debits/{id}:
              get:
                description: >-
                  <p>Retrieves the details of an existing ReceivedDebit by
                  passing the unique ReceivedDebit ID from the ReceivedDebit
                  list</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
            /v1/treasury/transaction_entries:
              get:
                description: <p>Retrieves a list of TransactionEntry objects.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
                  - Transaction_entries
            /v1/treasury/transaction_entries/{id}:
              get:
                description: <p>Retrieves a TransactionEntry object.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
                  - Transaction_entries
            /v1/treasury/transactions:
              get:
                description: <p>Retrieves a list of Transaction objects.</p>
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
                  - Transaction_entries
                  - Transactions
            /v1/treasury/transactions/{id}:
              get:
                description: <p>Retrieves the details of an existing Transa
                tags:
                  - V1
                  - Treasury
                  - Credit_reversals
                  - Credit_reversal
                  - Debit_reversals
                  - Debit_reversal
                  - Financial_accounts
                  - Financial_account
                  - Features
                  - Inbound_transfers
                  - Id
                  - Inbound_transfer
                  - Cancel
                  - Outbound_payments
                  - Outbound_transfers
                  - Outbound_transfer
                  - Received_credits
                  - Received_debits
                  - Transaction_entries
                  - Transactio
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-schema-type-error
              message: Parameter Schema Type
            - code: openapi-parameters-schema-anyof-info
              message: Parameter Schema AnyOf
            - code: openapi-request-body-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-names-length-error
              message: Schema Properties Name Length
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-x-expansion-resources-info
              message: Schema Properties X Expansion Resources
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-properties-x-expandableFields-info
              message: Schema Properties X Expansion Fields
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/treasury-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/treasury-openapi-api-evangelist-ratings.yml
  - aid: stripe:stripe-webhook-api
    name: Stripe Webhook API
    description: >-
      You can configure webhook endpoints via the API to be notified about
      events that happen in your Stripe account or connected accounts.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://stripe.com/docs/api/webhook_endpoints
    baseURL: https://api.stripe.com
    tags: []
    properties:
      - type: OpenAPI
        url: https://stripe.com/docs/api/webhook_endpoints
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            title: Stripe Webhook API
          paths:
            /v1/webhook_endpoints:
              get:
                description: <p>Returns a list of your webhook endpoints.</p>
                tags:
                  - V1
                  - Webhook_endpoints
              post:
                description: >-
                  <p>A webhook endpoint must have a <code>url</code> and a list
                  of <code>enabled_events</code>. You may optionally specify the
                  Boolean <code>connect</code> parameter. If set to true, then a
                  Connect webhook endpoint that notifies the specified
                  <code>url</code> about events from all connected accounts is
                  created; otherwise an account webhook endpoint that notifies
                  the specified <code>url</code> only about events from your
                  account is created. You can also create webhook endpoints in
                  the <a
                  href="https://dashboard.stripe.com/account/webhooks">webhooks
                  settings</a> section of the Dashboard.</p>
                tags:
                  - V1
                  - Webhook_endpoints
            /v1/webhook_endpoints/{webhook_endpoint}:
              delete:
                description: >-
                  <p>You can also delete webhook endpoints via the <a
                  href="https://dashboard.stripe.com/account/webhooks">webhook
                  endpoint management</a> page of the Stripe dashboard.</p>
                tags:
                  - V1
                  - Webhook_endpoints
                  - Webhook_endpoint
              get:
                description: <p>Retrieves the webhook endpoint with the given ID.</p>
                tags:
                  - V1
                  - Webhook_endpoints
                  - Webhook_endpoint
              post:
                description: >-
                  <p>Updates the webhook endpoint. You may edit the
                  <code>url</code>, the list of <code>enabled_events</code>, and
                  the status of your end
                tags:
                  - V1
                  - Webhook_endpoints
                  - Webhook_endpoi
      - type: API Evangelist Ratings
        data:
          weekNumber: 12
          rules:
            - code: openapi-external-docs-error
              message: External Docs
            - code: openapi-tags-object-error
              message: Tag Object
            - code: openapi-openapi-version-300-info
              message: 3.0.0 Version of OpenAPI
            - code: openapi-openapi-version-310-info
              message: 3.1.0 Version of OpenAPI
            - code: openapi-info-license-error
              message: License Object
            - code: openapi-info-title-info
              message: Info Title
            - code: openapi-info-title-upper-case-info
              message: Info Title Upper Case
            - code: openapi-info-description-info
              message: Info Description
            - code: openapi-info-contact-info
              message: Contact Object
            - code: openapi-info-contact-email-info
              message: Contact Email
            - code: openapi-info-contact-name-info
              message: Contact Name
            - code: openapi-info-contact-url-info
              message: Contact URL
            - code: openapi-info-terms-of-service-info
              message: Terms of Service
            - code: openapi-info-version-info
              message: Info Version
            - code: openapi-no-api-in-path-error
              message: No API in Path
            - code: openapi-no-path-trailing-slash-info
              message: Path Trailing Slash
            - code: openapi-path-description-warn
              message: Path Description
            - code: openapi-operation-security-definitions-error
              message: Operation Security Definition
            - code: openapi-operations-summary-error
              message: Operation Summary
            - code: openapi-operations-tags-error
              message: Operation Tags
            - code: openapi-operations-description-info
              message: Operation Description
            - code: openapi-operations-operation-ids-camel-case-error
              message: Operation ID Camel Case
            - code: openapi-operations-operation-ids-info
              message: Operation ID.
            - code: openapi-parameters-description-info
              message: Parameter Description
            - code: openapi-parameters-query-names-camel-case-error
              message: Parameter Query Name Camel Case
            - code: openapi-parameters-query-names-snake-case-error
              message: Parameter Query Name Snake Case
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
            - code: openapi-no-request-body-on-get-error
              message: GET Request Body
            - code: openapi-request-body-have-content-info
              message: Request Body Content
            - code: >-
                openapi-request-body-have-application-x-www-form-url-encoded-info
              message: Request Body Application X WWW Form URL Encoded
            - code: openapi-request-body-have-schema-info
              message: Request Body Schema
            - code: openapi-request-body-have-schema-properties-warn
              message: Request Body Schema Components
            - code: openapi-request-body-have-schema-required-info
              message: Request Body Schema Required
            - code: openapi-request-body-have-schema-required-warn
              message: Request Body Schema Required
            - code: openapi-request-body-schema-ref-warn
              message: Request Body Schema Ref
            - code: openapi-response-get-400-status-code-warn
              message: 400 Status Code for GET Responses
            - code: openapi-response-get-404-status-code-warn
              message: 404 Status Code for GET Responses
            - code: openapi-response-get-500-status-code-error
              message: 500 Status Code for GET Responses
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
            - code: openapi-response-get-default-status-code-info
              message: Response Has Default Status Code
            - code: openapi-response-get-default-content-info
              message: Default Content
            - code: openapi-response-get-default-media-type-info
              message: JSON Media Type Default
            - code: openapi-response-get-default-media-type-schema-info
              message: Schema Default
            - code: openapi-response-get-default-schema-ref-warn
              message: Default Response Schema Ref
            - code: openapi-operations-description-length-error
              message: Operation Description Length
            - code: openapi-request-body-on-post-info
              message: Request Body POST
            - code: openapi-request-body-content-on-post-info
              message: Request Body Content POST
            - code: openapi-request-body-json-media-type-on-post-error
              message: JSON Media Type POST
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
            - code: openapi-request-body-schema-properties-nullable-error
              message: Request Body Schema Properties Format
            - code: openapi-request-body-schema-properties-type-error
              message: Request Body Schema Properties Type
            - code: openapi-response-post-201-status-code-error
              message: POST 201 Status Code
            - code: openapi-response-post-400-status-code-warn
              message: 400 Status Code for POST Responses
            - code: openapi-response-post-404-status-code-warn
              message: 404 Status Code for POST Responses
            - code: openapi-response-post-500-status-code-error
              message: 500 Status Code for POST Responses
            - code: openapi-parameters-description-error
              message: Parameter Description
            - code: openapi-parameters-path-names-camel-case-error
              message: Parameter Path Name Camel Case
            - code: openapi-parameters-required-error
              message: Parameters MUST have a required property.
            - code: openapi-no-request-body-on-delete-error
              message: DELETE Request Body
            - code: openapi-response-delete-204-status-code-error
              message: DELETE 204 Status Code
            - code: openapi-response-delete-400-status-code-warn
              message: 400 Status Code for DELETE Responses
            - code: openapi-response-delete-404-status-code-error
              message: 404 Status Code for DELETE Responses
            - code: openapi-response-delete-500-status-code-error
              message: 500 Status Code for DELETE Responses
            - code: openapi-schema-names-pascal-case-warn
              message: Schema Name Pascal Case
            - code: openapi-schema-description-info
              message: Schemas has a description.
            - code: openapi-schema-properties-format-error
              message: Schema Properties Format
            - code: openapi-schema-properties-names-pascal-case-error
              message: Schema Property Names Pascal Case
            - code: openapi-schema-properties-nullable-error
              message: Schema Properties Format
            - code: openapi-schema-properties-type-error
              message: Schema Properties Type
            - code: invalid-ref
              message: '''#/components/schemas/api_errors'' does not exist'
            - code: openapi-schema-properties-pii-info
              message: Schema PII
            - code: openapi-schema-type-info
              message: Schema Type
            - code: openapi-schema-names-camel-case-warn
              message: Schema Name Camel Case
            - code: openapi-schema-description-length-error
              message: Description needs to be less than 250 characters.
            - code: openapi-schema-properties-names-camel-case-error
              message: Schema Property Names Camel Case
            - code: openapi-schema-properties-descriptions-error
              message: Schema Description
            - code: openapi-schema-properties-descriptions-info
              message: Schema Description
            - code: openapi-schema-properties-nullable-info
              message: Schema Properties Nullable
            - code: openapi-schema-properties-type-info
              message: Schema Properties Format
            - code: openapi-schema-properties-enum-info
              message: Schema Property Enum
            - code: openapi-schema-properties-enum-casing-error
              message: Schema Property Enum Casing
            - code: openapi-schema-x-expandableFields-info
              message: Schema X Expansion Fields
            - code: openapi-schema-description-error
              message: Schema SHOULD have a description.
            - code: openapi-schema-names-length-error
              message: Schema Name Length
            - code: openapi-schema-names-snake-case-warn
              message: Schema Name Snake Case
            - code: openapi-schema-properties-anyof-info
              message: Schema Properties AnyOf
            - code: openapi-schema-properties-descriptions-length-error
              message: Schema Description Length
            - code: openapi-security-schemes-info
              message: Security Scheme
    overlays:
      - type: APIs.io Search
        url: overlays/webhook-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/webhook-openapi-api-evangelist-ratings.yml
common:
  - type: Sign Up
    url: https://dashboard.stripe.com/register
  - type: Authentication
    url: https://stripe.com/docs/api/authentication
  - type: Blog
    url: https://stripe.com/blog
  - type: Status
    url: https://status.stripe.com/
  - type: Change Log
    url: https://stripe.com/docs/upgrades#api-versions
  - type: Terms of Service
    url: https://stripe.com/privacy
  - type: Support
    url: https://support.stripe.com/
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
maintainers:
  - FN: APIs.json
    email: info@apis.io
---