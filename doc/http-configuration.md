
# HttpConfiguration

The following parameters are configurable for the HttpConfiguration:

## Properties

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| timeout | `float64` | Timeout in seconds.<br>*Default*: `0` | `WithTimeout` | `Timeout()` |
| transport | `httpRoundTripper` | Establishes network connection and caches them for reuse.<br>*Default*: `http.DefaultTransport` | `WithTransport` | `Transport()` |
| retryConfiguration | [`e2ELanguageSelectApiRetryConfiguration`](../doc/retry-configuration.md) | Configurations to retry requests.<br>*Default*: `e2ELanguageSelectApi.DefaultRetryConfiguration()` | `WithRetryConfiguration` | `RetryConfiguration()` |

The httpConfiguration can be initialized as follows:

```go
package main

import (
    "e2ELanguageSelectApi"
    "net/http"
)

func main() {
    httpConfiguration := e2ELanguageSelectApi.CreateHttpConfiguration(
        e2ELanguageSelectApi.WithTimeout(0),
        e2ELanguageSelectApi.WithTransport(http.DefaultTransport),
        e2ELanguageSelectApi.WithRetryConfiguration(e2ELanguageSelectApi.DefaultRetryConfiguration()),
    )
}
```

