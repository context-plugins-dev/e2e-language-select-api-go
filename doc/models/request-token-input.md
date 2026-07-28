
# Request Token Input

Input structure for the method RequestToken

## Structure

`RequestTokenInput`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Authorization` | `string` | Required | Authorization header in Basic auth format |
| `Code` | `string` | Required | Authorization Code |
| `RedirectUri` | `string` | Required | Redirect Uri |

## Example

```go
package main

import (
    "e2ELanguageSelectApi/models"
)

func main() {
    requestTokenInput := models.RequestTokenInput{
        Authorization:        "Authorization8",
        Code:                 "code8",
        RedirectUri:          "redirect_uri8",
    }

}
```

