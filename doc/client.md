
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpConfiguration | [`HttpConfiguration`](../doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| loggerConfiguration | [`LoggerConfiguration`](../doc/logger-configuration.md) | Represents the logger configurations for API calls |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

```go
package main

import (
    "e2ELanguageSelectApi"
    "e2ELanguageSelectApi/models"
)

func main() {
    client := e2ELanguageSelectApi.NewClient(
    e2ELanguageSelectApi.CreateConfiguration(
            e2ELanguageSelectApi.WithHttpConfiguration(
                e2ELanguageSelectApi.CreateHttpConfiguration(
                    e2ELanguageSelectApi.WithTimeout(0),
                ),
            ),
            e2ELanguageSelectApi.WithEnvironment(e2ELanguageSelectApi.PRODUCTION),
            e2ELanguageSelectApi.WithAuthorizationCodeAuthCredentials(
                e2ELanguageSelectApi.NewAuthorizationCodeAuthCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri",
                ).
                WithOAuthScopes([]models.OAuthScope{
        models.OAuthScope_CrmObjectsContactsRead,
    }),
            ),
            e2ELanguageSelectApi.WithLoggerConfiguration(
                e2ELanguageSelectApi.WithLevel("info"),
                e2ELanguageSelectApi.WithRequestConfiguration(
                    e2ELanguageSelectApi.WithRequestBody(true),
                ),
                e2ELanguageSelectApi.WithResponseConfiguration(
                    e2ELanguageSelectApi.WithResponseHeaders(true),
                ),
            ),
        ),
    )
}
```

## E2E Language Select API Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| ApiController() | Gets ApiController |
| OAuthAuthorizationController() | Gets OAuthAuthorizationController |

