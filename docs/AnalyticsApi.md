# Cashful.Sdk.Api.AnalyticsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAnalytics**](AnalyticsApi.md#getanalytics) | **GET** /api/canary/analytics | Get Analytics |
| [**GetAnalyticsSummary**](AnalyticsApi.md#getanalyticssummary) | **GET** /api/canary/analytics/summary | Get Analytics Summary |

<a id="getanalytics"></a>
# **GetAnalytics**
> AnalyticsResponseDto GetAnalytics (string merchantId)

Get Analytics

Retrieves transaction volume and customer growth metrics for the merchant.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cashful.Sdk.Api;
using Cashful.Sdk.Client;
using Cashful.Sdk.Model;

namespace Example
{
    public class GetAnalyticsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var merchantId = merchant_123;  // string | The unique identifier of the merchant

            try
            {
                // Get Analytics
                AnalyticsResponseDto result = apiInstance.GetAnalytics(merchantId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetAnalytics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetAnalyticsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Analytics
    ApiResponse<AnalyticsResponseDto> response = apiInstance.GetAnalyticsWithHttpInfo(merchantId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetAnalyticsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The unique identifier of the merchant |  |

### Return type

[**AnalyticsResponseDto**](AnalyticsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved analytics |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getanalyticssummary"></a>
# **GetAnalyticsSummary**
> AnalyticsSummaryDto GetAnalyticsSummary (string merchantId)

Get Analytics Summary

Retrieves a quick summary of key metrics for the merchant.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cashful.Sdk.Api;
using Cashful.Sdk.Client;
using Cashful.Sdk.Model;

namespace Example
{
    public class GetAnalyticsSummaryExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var merchantId = merchant_123;  // string | The unique identifier of the merchant

            try
            {
                // Get Analytics Summary
                AnalyticsSummaryDto result = apiInstance.GetAnalyticsSummary(merchantId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetAnalyticsSummary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetAnalyticsSummaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Analytics Summary
    ApiResponse<AnalyticsSummaryDto> response = apiInstance.GetAnalyticsSummaryWithHttpInfo(merchantId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetAnalyticsSummaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The unique identifier of the merchant |  |

### Return type

[**AnalyticsSummaryDto**](AnalyticsSummaryDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved analytics summary |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

