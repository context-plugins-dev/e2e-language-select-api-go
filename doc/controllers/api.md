# API

```go
apiController := client.ApiController()
```

## Class Name

`ApiController`


# List Contacts

```go
ListContacts(
    ctx context.Context) (
    models.ApiResponse[models.CrmV3ObjectsContactsResponse],
    error)
```

## Authentication

This endpoint requires [OAuth2](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [models.CrmV3ObjectsContactsResponse](../../doc/models/crm-v3-objects-contacts-response.md).

## Example Usage

```go
ctx := context.Background()

apiResponse, err := apiController.ListContacts(ctx)
if err != nil {
    log.Fatalln(err)
} else {
    // Printing the result and response
    fmt.Println(apiResponse.Data)
    fmt.Println(apiResponse.Response.StatusCode)
}
```

