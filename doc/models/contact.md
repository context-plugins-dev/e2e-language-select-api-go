
# Contact

## Structure

`Contact`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `*string` | Optional | - |
| `Email` | `*string` | Optional | - |

## Example

```go
package main

import (
    "e2ELanguageSelectApi/models"
)

func main() {
    contact := models.Contact{
        Id:                   models.ToPointer("id2"),
        Email:                models.ToPointer("email4"),
    }

}
```

