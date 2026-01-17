# Cashful.Sdk.Api.StorageApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**StorageControllerConfirmUploadCanary**](StorageApi.md#storagecontrollerconfirmuploadcanary) | **POST** /api/canary/storage/confirm-upload | Confirm that a file upload was completed |
| [**StorageControllerDeleteCanary**](StorageApi.md#storagecontrollerdeletecanary) | **DELETE** /api/canary/storage/{id} | Delete a file |
| [**StorageControllerGetDownloadUrlCanary**](StorageApi.md#storagecontrollergetdownloadurlcanary) | **GET** /api/canary/storage/{id}/download-url | Get a presigned download URL for a file |
| [**StorageControllerListCanary**](StorageApi.md#storagecontrollerlistcanary) | **GET** /api/canary/storage | List files |
| [**StorageControllerRequestUploadUrlCanary**](StorageApi.md#storagecontrollerrequestuploadurlcanary) | **POST** /api/canary/storage/upload-url | Request a presigned URL for file upload |
| [**StorageControllerRetrieveCanary**](StorageApi.md#storagecontrollerretrievecanary) | **GET** /api/canary/storage/{id} | Get file details |

<a id="storagecontrollerconfirmuploadcanary"></a>
# **StorageControllerConfirmUploadCanary**
> FileDto StorageControllerConfirmUploadCanary (ConfirmUploadDto confirmUploadDto)

Confirm that a file upload was completed

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
    public class StorageControllerConfirmUploadCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var confirmUploadDto = new ConfirmUploadDto(); // ConfirmUploadDto | 

            try
            {
                // Confirm that a file upload was completed
                FileDto result = apiInstance.StorageControllerConfirmUploadCanary(confirmUploadDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerConfirmUploadCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerConfirmUploadCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Confirm that a file upload was completed
    ApiResponse<FileDto> response = apiInstance.StorageControllerConfirmUploadCanaryWithHttpInfo(confirmUploadDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerConfirmUploadCanaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **confirmUploadDto** | [**ConfirmUploadDto**](ConfirmUploadDto.md) |  |  |

### Return type

[**FileDto**](FileDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="storagecontrollerdeletecanary"></a>
# **StorageControllerDeleteCanary**
> void StorageControllerDeleteCanary (string id)

Delete a file

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
    public class StorageControllerDeleteCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | File ID

            try
            {
                // Delete a file
                apiInstance.StorageControllerDeleteCanary(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerDeleteCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerDeleteCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a file
    apiInstance.StorageControllerDeleteCanaryWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerDeleteCanaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | File ID |  |

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
| **200** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="storagecontrollergetdownloadurlcanary"></a>
# **StorageControllerGetDownloadUrlCanary**
> PresignedDownloadResponseDto StorageControllerGetDownloadUrlCanary (string id)

Get a presigned download URL for a file

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
    public class StorageControllerGetDownloadUrlCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | File ID

            try
            {
                // Get a presigned download URL for a file
                PresignedDownloadResponseDto result = apiInstance.StorageControllerGetDownloadUrlCanary(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerGetDownloadUrlCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerGetDownloadUrlCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get a presigned download URL for a file
    ApiResponse<PresignedDownloadResponseDto> response = apiInstance.StorageControllerGetDownloadUrlCanaryWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerGetDownloadUrlCanaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | File ID |  |

### Return type

[**PresignedDownloadResponseDto**](PresignedDownloadResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="storagecontrollerlistcanary"></a>
# **StorageControllerListCanary**
> ListFilesResponseDto StorageControllerListCanary (string merchantId, decimal? limit = null, decimal? offset = null, string? tag = null, string? status = null, string? relatedEntityId = null, string? relatedEntityType = null)

List files

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
    public class StorageControllerListCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 50;  // decimal? | Maximum number of records to return (optional) 
            var offset = 0;  // decimal? | Number of records to skip (optional) 
            var tag = "tag_example";  // string? | Filter by tag (optional) 
            var status = "pending";  // string? |  (optional) 
            var relatedEntityId = "relatedEntityId_example";  // string? |  (optional) 
            var relatedEntityType = "relatedEntityType_example";  // string? |  (optional) 

            try
            {
                // List files
                ListFilesResponseDto result = apiInstance.StorageControllerListCanary(merchantId, limit, offset, tag, status, relatedEntityId, relatedEntityType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerListCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerListCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List files
    ApiResponse<ListFilesResponseDto> response = apiInstance.StorageControllerListCanaryWithHttpInfo(merchantId, limit, offset, tag, status, relatedEntityId, relatedEntityType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerListCanaryWithHttpInfo: " + e.Message);
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
| **tag** | **string?** | Filter by tag | [optional]  |
| **status** | **string?** |  | [optional]  |
| **relatedEntityId** | **string?** |  | [optional]  |
| **relatedEntityType** | **string?** |  | [optional]  |

### Return type

[**ListFilesResponseDto**](ListFilesResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="storagecontrollerrequestuploadurlcanary"></a>
# **StorageControllerRequestUploadUrlCanary**
> PresignedUploadResponseDto StorageControllerRequestUploadUrlCanary (RequestUploadUrlDto requestUploadUrlDto)

Request a presigned URL for file upload

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
    public class StorageControllerRequestUploadUrlCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var requestUploadUrlDto = new RequestUploadUrlDto(); // RequestUploadUrlDto | 

            try
            {
                // Request a presigned URL for file upload
                PresignedUploadResponseDto result = apiInstance.StorageControllerRequestUploadUrlCanary(requestUploadUrlDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerRequestUploadUrlCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerRequestUploadUrlCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Request a presigned URL for file upload
    ApiResponse<PresignedUploadResponseDto> response = apiInstance.StorageControllerRequestUploadUrlCanaryWithHttpInfo(requestUploadUrlDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerRequestUploadUrlCanaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **requestUploadUrlDto** | [**RequestUploadUrlDto**](RequestUploadUrlDto.md) |  |  |

### Return type

[**PresignedUploadResponseDto**](PresignedUploadResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="storagecontrollerretrievecanary"></a>
# **StorageControllerRetrieveCanary**
> FileDto StorageControllerRetrieveCanary (string id)

Get file details

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
    public class StorageControllerRetrieveCanaryExample
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
            var apiInstance = new StorageApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | File ID

            try
            {
                // Get file details
                FileDto result = apiInstance.StorageControllerRetrieveCanary(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.StorageControllerRetrieveCanary: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the StorageControllerRetrieveCanaryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get file details
    ApiResponse<FileDto> response = apiInstance.StorageControllerRetrieveCanaryWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.StorageControllerRetrieveCanaryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | File ID |  |

### Return type

[**FileDto**](FileDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** |  |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

