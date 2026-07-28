
# Crm V3 Objects Contacts Response

## Structure

`CrmV3ObjectsContactsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Results` | [`[]models.Contact`](../../doc/models/contact.md) | Optional | - |

## Example

```go
package main

import (
    "e2ELanguageSelectApi/models"
)

func main() {
    crmV3ObjectsContactsResponse := models.CrmV3ObjectsContactsResponse{
        Results:              []models.Contact{
            models.Contact{
                Id:                   models.ToPointer("id6"),
                Email:                models.ToPointer("email0"),
            },
        },
    }

}
```

