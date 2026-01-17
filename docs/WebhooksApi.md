# Cashful.Sdk.Api.WebhooksApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWebhookEndpoint**](WebhooksApi.md#createwebhookendpoint) | **POST** /api/canary/webhook-endpoints | Create Webhook Endpoint |
| [**DeleteWebhookEndpoint**](WebhooksApi.md#deletewebhookendpoint) | **DELETE** /api/canary/webhook-endpoints/{id} | Delete Webhook Endpoint |
| [**ListWebhookEndpoints**](WebhooksApi.md#listwebhookendpoints) | **GET** /api/canary/webhook-endpoints | List Webhook Endpoints |

<a id="createwebhookendpoint"></a>
# **CreateWebhookEndpoint**
> WebhookEndpointResponseDto CreateWebhookEndpoint (CreateWebhookEndpointDto createWebhookEndpointDto)

Create Webhook Endpoint

Registers a URL to receive real-time events (e.g., checkout.session.completed, purchase.succeeded).

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
    public class CreateWebhookEndpointExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var createWebhookEndpointDto = new CreateWebhookEndpointDto(); // CreateWebhookEndpointDto | Webhook endpoint details

            try
            {
                // Create Webhook Endpoint
                WebhookEndpointResponseDto result = apiInstance.CreateWebhookEndpoint(createWebhookEndpointDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.CreateWebhookEndpoint: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWebhookEndpointWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Webhook Endpoint
    ApiResponse<WebhookEndpointResponseDto> response = apiInstance.CreateWebhookEndpointWithHttpInfo(createWebhookEndpointDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.CreateWebhookEndpointWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWebhookEndpointDto** | [**CreateWebhookEndpointDto**](CreateWebhookEndpointDto.md) | Webhook endpoint details |  |

### Return type

[**WebhookEndpointResponseDto**](WebhookEndpointResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Webhook endpoint created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewebhookendpoint"></a>
# **DeleteWebhookEndpoint**
> Object DeleteWebhookEndpoint (string id)

Delete Webhook Endpoint

Stops sending events to a specific URL.

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
    public class DeleteWebhookEndpointExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the webhook endpoint

            try
            {
                // Delete Webhook Endpoint
                Object result = apiInstance.DeleteWebhookEndpoint(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.DeleteWebhookEndpoint: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWebhookEndpointWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete Webhook Endpoint
    ApiResponse<Object> response = apiInstance.DeleteWebhookEndpointWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.DeleteWebhookEndpointWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the webhook endpoint |  |

### Return type

**Object**

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook endpoint successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwebhookendpoints"></a>
# **ListWebhookEndpoints**
> ListWebhookEndpointsResponseDto ListWebhookEndpoints (string merchantId, decimal? limit = null, decimal? offset = null)

List Webhook Endpoints

Lists all configured webhook endpoints.

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
    public class ListWebhookEndpointsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 

            try
            {
                // List Webhook Endpoints
                ListWebhookEndpointsResponseDto result = apiInstance.ListWebhookEndpoints(merchantId, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.ListWebhookEndpoints: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWebhookEndpointsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Webhook Endpoints
    ApiResponse<ListWebhookEndpointsResponseDto> response = apiInstance.ListWebhookEndpointsWithHttpInfo(merchantId, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.ListWebhookEndpointsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The ID of the merchant. This parameter is required. |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional]  |
| **offset** | **decimal?** | Number of records to skip | [optional]  |

### Return type

[**ListWebhookEndpointsResponseDto**](ListWebhookEndpointsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved webhook endpoints |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

