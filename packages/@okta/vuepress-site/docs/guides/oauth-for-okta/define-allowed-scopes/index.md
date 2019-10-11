---
title: Define allowed scopes
---
When a request is sent to the Okta [Org Authorization Server](/docs/concepts/auth-servers), it validates all of the requested scopes in the OAuth2 authorize or token request against the app's grants collection. The scope is granted if it exists in the app's grants collection.

## Add grants using the Developer Console

> **Note:** Only the Super Admin role has permissions to grant scopes to an app.

1. From the Developer Console, click **Applications**, and then select the OpenID Connect (OIDC) or OAuth 2.0 app that you want to add grants to.
2. Select the **Okta API Scopes** tab and then click **Grant** for each of the scopes that you want to add to the application's grant collection.

    Alternatively, you can add grants using the `/grants` API. The following is an example request to create a grant for the `okta.users.read` scope.

    ```json
    POST /api/v1/apps/<client_id>/grants

    {
        "scopeId": "okta.users.read",
        "issuer": "https://{yourOktaDomain}"
    }
    ```

    > **Note:** You can find a list of available values for `scopeId` in the <GuideLink link="../scopes">Scopes & supported endpoints</GuideLink> section.

<NextSectionLink/>