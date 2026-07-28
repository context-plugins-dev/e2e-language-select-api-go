
# Getting Started with E2E Language Select API

## Introduction

One-spec regression check for the crawler-minted APIMATIC-META.

### Requirements

The SDK requires **Go version 1.18 or above**.

## Building

### Install Dependencies

Resolve all the SDK dependencies, using the `go get` command.

## Installation

The following section explains how to use the e2ELanguageSelectApi library in a new project.

### 1. Add SDK as a Dependency to the Application

- Add the following lines to your application's `go.mod` file:

```go
replace e2ELanguageSelectApi => ".\\e2e-language-select-api-go_generic_lib" // local path to the SDK

require e2ELanguageSelectApi v0.0.0
```

- Resolve the dependencies in the updated `go.mod` file, using the `go get` command.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpConfiguration | [`HttpConfiguration`](doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| loggerConfiguration | [`LoggerConfiguration`](doc/logger-configuration.md) | Represents the logger configurations for API calls |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](doc/auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** Production |

## Authorization

This API uses the following authentication schemes.

* [`OAuth2 (OAuth 2 Authorization Code Grant)`](doc/auth/oauth-2-authorization-code-grant.md)

## List of APIs

* [API](doc/controllers/api.md)

## SDK Infrastructure

### Configuration

* [HttpConfiguration](doc/http-configuration.md)
* [LoggerConfiguration](doc/logger-configuration.md)
* [RequestLoggerConfiguration](doc/request-logger-configuration.md)
* [ResponseLoggerConfiguration](doc/response-logger-configuration.md)
* [RetryConfiguration](doc/retry-configuration.md)

### Utilities

* [ApiResponse](doc/api-response.md)

