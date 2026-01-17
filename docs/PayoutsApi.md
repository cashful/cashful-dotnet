# Cashful.Sdk.Api.PayoutsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreatePayout**](PayoutsApi.md#createpayout) | **POST** /api/canary/payouts | Create Payout |
| [**ListPayouts**](PayoutsApi.md#listpayouts) | **GET** /api/canary/payouts | List Payouts |

<a id="createpayout"></a>
# **CreatePayout**
> PayoutResponseDto CreatePayout (CreatePayoutDto createPayoutDto)

Create Payout

Allows the merchant to move funds from their MerchantBalance (their earnings) to their external bank account.

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
    public class CreatePayoutExample
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
            var apiInstance = new PayoutsApi(httpClient, config, httpClientHandler);
            var createPayoutDto = new CreatePayoutDto(); // CreatePayoutDto | Payout details

            try
            {
                // Create Payout
                PayoutResponseDto result = apiInstance.CreatePayout(createPayoutDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PayoutsApi.CreatePayout: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePayoutWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Payout
    ApiResponse<PayoutResponseDto> response = apiInstance.CreatePayoutWithHttpInfo(createPayoutDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PayoutsApi.CreatePayoutWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPayoutDto** | [**CreatePayoutDto**](CreatePayoutDto.md) | Payout details |  |

### Return type

[**PayoutResponseDto**](PayoutResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Payout created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **402** | Insufficient merchant balance |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpayouts"></a>
# **ListPayouts**
> ListPayoutsResponseDto ListPayouts (string merchantId, decimal? limit = null, decimal? offset = null, string? status = null)

List Payouts

Retrieves a list of all historical and pending payouts for the merchant.

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
    public class ListPayoutsExample
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
            var apiInstance = new PayoutsApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 
            var status = "status_example";  // string? | Filter by status (optional) 

            try
            {
                // List Payouts
                ListPayoutsResponseDto result = apiInstance.ListPayouts(merchantId, limit, offset, status);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PayoutsApi.ListPayouts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPayoutsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Payouts
    ApiResponse<ListPayoutsResponseDto> response = apiInstance.ListPayoutsWithHttpInfo(merchantId, limit, offset, status);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PayoutsApi.ListPayoutsWithHttpInfo: " + e.Message);
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
| **status** | **string?** | Filter by status | [optional]  |

### Return type

[**ListPayoutsResponseDto**](ListPayoutsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved payouts |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

