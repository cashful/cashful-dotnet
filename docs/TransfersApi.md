# Cashful.Api.TransfersApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransfer**](TransfersApi.md#createtransfer) | **POST** /api/canary/transfers | Create P2P Transfer |
| [**ListTransfers**](TransfersApi.md#listtransfers) | **GET** /api/canary/transfers | List Transfers |

<a id="createtransfer"></a>
# **CreateTransfer**
> TransferResponseDto CreateTransfer (CreateTransferDto createTransferDto)

Create P2P Transfer

(Wallet-Enabling) Moves funds from one CustomerBalance to another CustomerBalance. This is the P2P feature.

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
    public class CreateTransferExample
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
            var apiInstance = new TransfersApi(httpClient, config, httpClientHandler);
            var createTransferDto = new CreateTransferDto(); // CreateTransferDto | Transfer details

            try
            {
                // Create P2P Transfer
                TransferResponseDto result = apiInstance.CreateTransfer(createTransferDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TransfersApi.CreateTransfer: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateTransferWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create P2P Transfer
    ApiResponse<TransferResponseDto> response = apiInstance.CreateTransferWithHttpInfo(createTransferDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TransfersApi.CreateTransferWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createTransferDto** | [**CreateTransferDto**](CreateTransferDto.md) | Transfer details |  |

### Return type

[**TransferResponseDto**](TransferResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Transfer created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **402** | Insufficient sender balance |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listtransfers"></a>
# **ListTransfers**
> ListTransfersResponseDto ListTransfers (string merchantId, decimal? limit = null, decimal? offset = null)

List Transfers

Lists transfers for a specific merchant with pagination.

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
    public class ListTransfersExample
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
            var apiInstance = new TransfersApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | Filter by merchant ID
            var limit = 50;  // decimal? | Maximum number of items to return (optional) 
            var offset = 0;  // decimal? | Number of items to skip (optional) 

            try
            {
                // List Transfers
                ListTransfersResponseDto result = apiInstance.ListTransfers(merchantId, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TransfersApi.ListTransfers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListTransfersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Transfers
    ApiResponse<ListTransfersResponseDto> response = apiInstance.ListTransfersWithHttpInfo(merchantId, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TransfersApi.ListTransfersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | Filter by merchant ID |  |
| **limit** | **decimal?** | Maximum number of items to return | [optional]  |
| **offset** | **decimal?** | Number of items to skip | [optional]  |

### Return type

[**ListTransfersResponseDto**](ListTransfersResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved transfers |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

