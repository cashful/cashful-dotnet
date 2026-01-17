# Cashful.Sdk.Api.BalanceApi

All URIs are relative to *http://localhost:9000*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetBalanceHistory**](BalanceApi.md#getbalancehistory) | **GET** /api/canary/balance/history | List Merchant Balance History |
| [**GetMerchantBalance**](BalanceApi.md#getmerchantbalance) | **GET** /api/canary/balance | Get Merchant Balance |

<a id="getbalancehistory"></a>
# **GetBalanceHistory**
> BalanceHistoryResponseDto GetBalanceHistory (string merchantId, decimal? limit = null, decimal? offset = null, string? startDate = null, string? endDate = null, string? transactionType = null)

List Merchant Balance History

A full ledger of all transactions, fees, and payouts for the merchant's master account.

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
    public class GetBalanceHistoryExample
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
            var apiInstance = new BalanceApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 
            var startDate = "startDate_example";  // string? | Filter transactions from this date (ISO 8601 format) (optional) 
            var endDate = "endDate_example";  // string? | Filter transactions until this date (ISO 8601 format) (optional) 
            var transactionType = "transactionType_example";  // string? | Filter by transaction type (e.g., \"credit\", \"debit\", \"fee\", \"payout\") (optional) 

            try
            {
                // List Merchant Balance History
                BalanceHistoryResponseDto result = apiInstance.GetBalanceHistory(merchantId, limit, offset, startDate, endDate, transactionType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BalanceApi.GetBalanceHistory: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBalanceHistoryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Merchant Balance History
    ApiResponse<BalanceHistoryResponseDto> response = apiInstance.GetBalanceHistoryWithHttpInfo(merchantId, limit, offset, startDate, endDate, transactionType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BalanceApi.GetBalanceHistoryWithHttpInfo: " + e.Message);
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
| **startDate** | **string?** | Filter transactions from this date (ISO 8601 format) | [optional]  |
| **endDate** | **string?** | Filter transactions until this date (ISO 8601 format) | [optional]  |
| **transactionType** | **string?** | Filter by transaction type (e.g., \&quot;credit\&quot;, \&quot;debit\&quot;, \&quot;fee\&quot;, \&quot;payout\&quot;) | [optional]  |

### Return type

[**BalanceHistoryResponseDto**](BalanceHistoryResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved balance history |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getmerchantbalance"></a>
# **GetMerchantBalance**
> MerchantBalanceResponseDto GetMerchantBalance (string merchantId)

Get Merchant Balance

Retrieves the merchant's own master balance (their earnings) available for payouts.

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
    public class GetMerchantBalanceExample
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
            var apiInstance = new BalanceApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant whose balance is being requested.

            try
            {
                // Get Merchant Balance
                MerchantBalanceResponseDto result = apiInstance.GetMerchantBalance(merchantId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BalanceApi.GetMerchantBalance: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetMerchantBalanceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Merchant Balance
    ApiResponse<MerchantBalanceResponseDto> response = apiInstance.GetMerchantBalanceWithHttpInfo(merchantId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BalanceApi.GetMerchantBalanceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The ID of the merchant whose balance is being requested. |  |

### Return type

[**MerchantBalanceResponseDto**](MerchantBalanceResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved merchant balance |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

