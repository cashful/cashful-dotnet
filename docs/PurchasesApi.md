# Cashful.Sdk.Api.PurchasesApi

All URIs are relative to *http://localhost:9000*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreatePurchase**](PurchasesApi.md#createpurchase) | **POST** /api/canary/purchases | Buy with Cash Balance |

<a id="createpurchase"></a>
# **CreatePurchase**
> PurchaseResponseDto CreatePurchase (CreatePurchaseDto createPurchaseDto)

Buy with Cash Balance

(Wallet-Enabling) Spends a product using the CustomerBalance as the source. Atomically debits the CustomerBalance and credits the MerchantBalance.

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
    public class CreatePurchaseExample
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
            var apiInstance = new PurchasesApi(httpClient, config, httpClientHandler);
            var createPurchaseDto = new CreatePurchaseDto(); // CreatePurchaseDto | Purchase details

            try
            {
                // Buy with Cash Balance
                PurchaseResponseDto result = apiInstance.CreatePurchase(createPurchaseDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PurchasesApi.CreatePurchase: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePurchaseWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Buy with Cash Balance
    ApiResponse<PurchaseResponseDto> response = apiInstance.CreatePurchaseWithHttpInfo(createPurchaseDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PurchasesApi.CreatePurchaseWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPurchaseDto** | [**CreatePurchaseDto**](CreatePurchaseDto.md) | Purchase details |  |

### Return type

[**PurchaseResponseDto**](PurchaseResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Purchase created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **402** | Insufficient customer balance |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

