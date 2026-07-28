
# Refresh Token Input

Input structure for the method RefreshToken

## Structure

`RefreshTokenInput`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Authorization` | `string` | Required | Authorization header in Basic auth format |
| `RefreshToken` | `string` | Required | Refresh token |
| `Scope` | `*string` | Optional | Requested scopes as a space-delimited list. |

## Example

```go
package main

import (
    "e2ELanguageSelectApi/models"
)

func main() {
    refreshTokenInput := models.RefreshTokenInput{
        Authorization:        "Authorization8",
        RefreshToken:         "refresh_token0",
        Scope:                models.ToPointer("scope2"),
    }

}
```

