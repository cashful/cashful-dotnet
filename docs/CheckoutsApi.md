# Cashful.Api.CheckoutsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCheckoutSession**](CheckoutsApi.md#createcheckoutsession) | **POST** /api/canary/checkout/sessions | Create Hosted Checkout |
| [**ListCheckoutSessions**](CheckoutsApi.md#listcheckoutsessions) | **GET** /api/canary/checkout/sessions | List Checkout Sessions |
| [**RetrieveCheckoutSession**](CheckoutsApi.md#retrievecheckoutsession) | **GET** /api/canary/checkout/sessions/{id} | Retrieve Checkout Session |

<a id="createcheckoutsession"></a>
# **CreateCheckoutSession**
> CheckoutSessionResponseDto CreateCheckoutSession (CreateCheckoutSessionDto createCheckoutSessionDto)

Create Hosted Checkout

Creates a hosted payment page. Used for: (1) A standard e-commerce purchase, or (2) a \"Pay-In\" to fund a CustomerBalance.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cashful.Api;
using Cashful.Client;
using Cashful.Model;

namespace Example
{
    public class CreateCheckoutSessionExample
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
            var apiInstance = new CheckoutsApi(httpClient, config, httpClientHandler);
            var createCheckoutSessionDto = new CreateCheckoutSessionDto(); // CreateCheckoutSessionDto | Checkout session details

            try
            {
                // Create Hosted Checkout
                CheckoutSessionResponseDto result = apiInstance.CreateCheckoutSession(createCheckoutSessionDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CheckoutsApi.CreateCheckoutSession: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateCheckoutSessionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Hosted Checkout
    ApiResponse<CheckoutSessionResponseDto> response = apiInstance.CreateCheckoutSessionWithHttpInfo(createCheckoutSessionDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CheckoutsApi.CreateCheckoutSessionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCheckoutSessionDto** | [**CreateCheckoutSessionDto**](CreateCheckoutSessionDto.md) | Checkout session details |  |

### Return type

[**CheckoutSessionResponseDto**](CheckoutSessionResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Checkout session created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcheckoutsessions"></a>
# **ListCheckoutSessions**
> ListCheckoutSessionsResponseDto ListCheckoutSessions (string merchantId, decimal? limit = null, decimal? offset = null, string? status = null)

List Checkout Sessions

Lists checkout sessions

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cashful.Api;
using Cashful.Client;
using Cashful.Model;

namespace Example
{
    public class ListCheckoutSessionsExample
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
            var apiInstance = new CheckoutsApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant to filter checkout sessions
            var limit = 50;  // decimal? | Maximum number of records to return (optional) 
            var offset = 0;  // decimal? | Number of records to skip (optional) 
            var status = "status_example";  // string? | The status to filter checkout sessions (optional) 

            try
            {
                // List Checkout Sessions
                ListCheckoutSessionsResponseDto result = apiInstance.ListCheckoutSessions(merchantId, limit, offset, status);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CheckoutsApi.ListCheckoutSessions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCheckoutSessionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Checkout Sessions
    ApiResponse<ListCheckoutSessionsResponseDto> response = apiInstance.ListCheckoutSessionsWithHttpInfo(merchantId, limit, offset, status);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CheckoutsApi.ListCheckoutSessionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The ID of the merchant to filter checkout sessions |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional]  |
| **offset** | **decimal?** | Number of records to skip | [optional]  |
| **status** | **string?** | The status to filter checkout sessions | [optional]  |

### Return type

[**ListCheckoutSessionsResponseDto**](ListCheckoutSessionsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved checkout sessions |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retrievecheckoutsession"></a>
# **RetrieveCheckoutSession**
> CheckoutSessionResponseDto RetrieveCheckoutSession (string id)

Retrieve Checkout Session

Retrieves details of a specific checkout session

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Cashful.Api;
using Cashful.Client;
using Cashful.Model;

namespace Example
{
    public class RetrieveCheckoutSessionExample
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
            var apiInstance = new CheckoutsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the checkout session

            try
            {
                // Retrieve Checkout Session
                CheckoutSessionResponseDto result = apiInstance.RetrieveCheckoutSession(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CheckoutsApi.RetrieveCheckoutSession: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetrieveCheckoutSessionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retrieve Checkout Session
    ApiResponse<CheckoutSessionResponseDto> response = apiInstance.RetrieveCheckoutSessionWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CheckoutsApi.RetrieveCheckoutSessionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the checkout session |  |

### Return type

[**CheckoutSessionResponseDto**](CheckoutSessionResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved checkout session |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

