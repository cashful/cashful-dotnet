# Cashful.Sdk.Api.PaymentLinksApi

All URIs are relative to *http://localhost:9000*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreatePaymentLink**](PaymentLinksApi.md#createpaymentlink) | **POST** /api/canary/payment-links | Create Payment Link |
| [**ListPaymentLinks**](PaymentLinksApi.md#listpaymentlinks) | **GET** /api/canary/payment-links | List Payment Links |
| [**RetrievePaymentLink**](PaymentLinksApi.md#retrievepaymentlink) | **GET** /api/canary/payment-links/{id} | Retrieve Payment Link |
| [**UpdatePaymentLink**](PaymentLinksApi.md#updatepaymentlink) | **PATCH** /api/canary/payment-links/{id} | Update Payment Link |

<a id="createpaymentlink"></a>
# **CreatePaymentLink**
> PaymentLinkResponseDto CreatePaymentLink (CreatePaymentLinkDto createPaymentLinkDto)

Create Payment Link

Creates a re-usable hosted link. Can be used for: (1) Selling a product, or (2) as a \"Pay-In\" link for a customer.

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
    public class CreatePaymentLinkExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "http://localhost:9000";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new PaymentLinksApi(httpClient, config, httpClientHandler);
            var createPaymentLinkDto = new CreatePaymentLinkDto(); // CreatePaymentLinkDto | Payment link details

            try
            {
                // Create Payment Link
                PaymentLinkResponseDto result = apiInstance.CreatePaymentLink(createPaymentLinkDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentLinksApi.CreatePaymentLink: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePaymentLinkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Payment Link
    ApiResponse<PaymentLinkResponseDto> response = apiInstance.CreatePaymentLinkWithHttpInfo(createPaymentLinkDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentLinksApi.CreatePaymentLinkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPaymentLinkDto** | [**CreatePaymentLinkDto**](CreatePaymentLinkDto.md) | Payment link details |  |

### Return type

[**PaymentLinkResponseDto**](PaymentLinkResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Payment link created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpaymentlinks"></a>
# **ListPaymentLinks**
> ListPaymentLinksResponseDto ListPaymentLinks (string merchantId, decimal? limit = null, decimal? offset = null, bool? active = null)

List Payment Links

Retrieves all payment links created by the merchant.

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
    public class ListPaymentLinksExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "http://localhost:9000";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new PaymentLinksApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 
            var active = true;  // bool? | Filter by active status (optional) 

            try
            {
                // List Payment Links
                ListPaymentLinksResponseDto result = apiInstance.ListPaymentLinks(merchantId, limit, offset, active);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentLinksApi.ListPaymentLinks: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPaymentLinksWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Payment Links
    ApiResponse<ListPaymentLinksResponseDto> response = apiInstance.ListPaymentLinksWithHttpInfo(merchantId, limit, offset, active);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentLinksApi.ListPaymentLinksWithHttpInfo: " + e.Message);
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
| **active** | **bool?** | Filter by active status | [optional]  |

### Return type

[**ListPaymentLinksResponseDto**](ListPaymentLinksResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved payment links |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retrievepaymentlink"></a>
# **RetrievePaymentLink**
> PaymentLinkResponseDto RetrievePaymentLink (string id)

Retrieve Payment Link

Retrieves a single payment link by ID.

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
    public class RetrievePaymentLinkExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "http://localhost:9000";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new PaymentLinksApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the payment link

            try
            {
                // Retrieve Payment Link
                PaymentLinkResponseDto result = apiInstance.RetrievePaymentLink(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentLinksApi.RetrievePaymentLink: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetrievePaymentLinkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retrieve Payment Link
    ApiResponse<PaymentLinkResponseDto> response = apiInstance.RetrievePaymentLinkWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentLinksApi.RetrievePaymentLinkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the payment link |  |

### Return type

[**PaymentLinkResponseDto**](PaymentLinkResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Payment link retrieved successfully |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatepaymentlink"></a>
# **UpdatePaymentLink**
> Object UpdatePaymentLink (string id, UpdatePaymentLinkDto updatePaymentLinkDto)

Update Payment Link

Updates a link's details, most commonly to set active: false.

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
    public class UpdatePaymentLinkExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "http://localhost:9000";
            // Configure Bearer token for authorization: bearer
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new PaymentLinksApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the payment link
            var updatePaymentLinkDto = new UpdatePaymentLinkDto(); // UpdatePaymentLinkDto | Payment link update details

            try
            {
                // Update Payment Link
                Object result = apiInstance.UpdatePaymentLink(id, updatePaymentLinkDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PaymentLinksApi.UpdatePaymentLink: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdatePaymentLinkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update Payment Link
    ApiResponse<Object> response = apiInstance.UpdatePaymentLinkWithHttpInfo(id, updatePaymentLinkDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PaymentLinksApi.UpdatePaymentLinkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the payment link |  |
| **updatePaymentLinkDto** | [**UpdatePaymentLinkDto**](UpdatePaymentLinkDto.md) | Payment link update details |  |

### Return type

**Object**

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Payment link updated successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

