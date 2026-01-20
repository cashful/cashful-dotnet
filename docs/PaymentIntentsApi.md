# Cashful.Api.PaymentIntentsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelPaymentIntent**](PaymentIntentsApi.md#cancelpaymentintent) | **POST** /api/canary/payment-intents/{id}/cancel | Cancel Payment Intent |
| [**ConfirmPaymentIntent**](PaymentIntentsApi.md#confirmpaymentintent) | **POST** /api/canary/payment-intents/{id}/confirm | Confirm Payment Intent |
| [**CreatePaymentIntent**](PaymentIntentsApi.md#createpaymentintent) | **POST** /api/canary/payment-intents | Create Payment Intent |
| [**ListPaymentIntents**](PaymentIntentsApi.md#listpaymentintents) | **GET** /api/canary/payment-intents | List Payment Intents |
| [**RetrievePaymentIntent**](PaymentIntentsApi.md#retrievepaymentintent) | **GET** /api/canary/payment-intents/{id} | Retrieve Payment Intent |

<a id="cancelpaymentintent"></a>
# **CancelPaymentIntent**
> PaymentIntentResponseDto CancelPaymentIntent (string id)

Cancel Payment Intent

Cancels a payment intent that has not yet succeeded or failed.

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
    public class CancelPaymentIntentExample
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
            var apiInstance = new PaymentIntentsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the payment intent

            try
            {
                // Cancel Payment Intent
                PaymentIntentResponseDto result = apiInstance.CancelPaymentIntent(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentIntentsApi.CancelPaymentIntent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CancelPaymentIntentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Cancel Payment Intent
    ApiResponse<PaymentIntentResponseDto> response = apiInstance.CancelPaymentIntentWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentIntentsApi.CancelPaymentIntentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the payment intent |  |

### Return type

[**PaymentIntentResponseDto**](PaymentIntentResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Payment intent canceled |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="confirmpaymentintent"></a>
# **ConfirmPaymentIntent**
> PaymentIntentResponseDto ConfirmPaymentIntent (string id)

Confirm Payment Intent

Confirms a payment intent that requires confirmation. This initiates the actual payment processing.

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
    public class ConfirmPaymentIntentExample
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
            var apiInstance = new PaymentIntentsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the payment intent

            try
            {
                // Confirm Payment Intent
                PaymentIntentResponseDto result = apiInstance.ConfirmPaymentIntent(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentIntentsApi.ConfirmPaymentIntent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConfirmPaymentIntentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Confirm Payment Intent
    ApiResponse<PaymentIntentResponseDto> response = apiInstance.ConfirmPaymentIntentWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentIntentsApi.ConfirmPaymentIntentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the payment intent |  |

### Return type

[**PaymentIntentResponseDto**](PaymentIntentResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Payment intent confirmed and processing |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createpaymentintent"></a>
# **CreatePaymentIntent**
> PaymentIntentResponseDto CreatePaymentIntent (CreatePaymentIntentDto createPaymentIntentDto)

Create Payment Intent

Creates a payment intent for off-session charges. Used for subscriptions, recurring billing, or server-to-server payments with saved cards.

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
    public class CreatePaymentIntentExample
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
            var apiInstance = new PaymentIntentsApi(httpClient, config, httpClientHandler);
            var createPaymentIntentDto = new CreatePaymentIntentDto(); // CreatePaymentIntentDto | Payment intent details

            try
            {
                // Create Payment Intent
                PaymentIntentResponseDto result = apiInstance.CreatePaymentIntent(createPaymentIntentDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentIntentsApi.CreatePaymentIntent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePaymentIntentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Payment Intent
    ApiResponse<PaymentIntentResponseDto> response = apiInstance.CreatePaymentIntentWithHttpInfo(createPaymentIntentDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentIntentsApi.CreatePaymentIntentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPaymentIntentDto** | [**CreatePaymentIntentDto**](CreatePaymentIntentDto.md) | Payment intent details |  |

### Return type

[**PaymentIntentResponseDto**](PaymentIntentResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Payment intent created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **402** | Payment declined |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpaymentintents"></a>
# **ListPaymentIntents**
> void ListPaymentIntents (string merchantId, decimal? limit = null, decimal? offset = null, string? status = null)

List Payment Intents

Lists payment intents for a specific merchant with pagination and filtering.

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
    public class ListPaymentIntentsExample
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
            var apiInstance = new PaymentIntentsApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | Filter by merchant ID
            var limit = 50MD;  // decimal? | Maximum number of records to return (optional)  (default to 50M)
            var offset = 0MD;  // decimal? | Number of records to skip (optional)  (default to 0M)
            var status = "initiation";  // string? | Filter by status (optional) 

            try
            {
                // List Payment Intents
                apiInstance.ListPaymentIntents(merchantId, limit, offset, status);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentIntentsApi.ListPaymentIntents: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPaymentIntentsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Payment Intents
    apiInstance.ListPaymentIntentsWithHttpInfo(merchantId, limit, offset, status);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentIntentsApi.ListPaymentIntentsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | Filter by merchant ID |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional] [default to 50M] |
| **offset** | **decimal?** | Number of records to skip | [optional] [default to 0M] |
| **status** | **string?** | Filter by status | [optional]  |

### Return type

void (empty response body)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved payment intents |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retrievepaymentintent"></a>
# **RetrievePaymentIntent**
> PaymentIntentResponseDto RetrievePaymentIntent (string id)

Retrieve Payment Intent

Retrieves the current state of a specific payment intent.

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
    public class RetrievePaymentIntentExample
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
            var apiInstance = new PaymentIntentsApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the payment intent

            try
            {
                // Retrieve Payment Intent
                PaymentIntentResponseDto result = apiInstance.RetrievePaymentIntent(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentIntentsApi.RetrievePaymentIntent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetrievePaymentIntentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retrieve Payment Intent
    ApiResponse<PaymentIntentResponseDto> response = apiInstance.RetrievePaymentIntentWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentIntentsApi.RetrievePaymentIntentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the payment intent |  |

### Return type

[**PaymentIntentResponseDto**](PaymentIntentResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved payment intent |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

