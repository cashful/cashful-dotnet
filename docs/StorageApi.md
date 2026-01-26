# Cashful.Api.StorageApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ConfirmUpload**](StorageApi.md#confirmupload) | **POST** /api/canary/storage/confirm-upload | Confirm that a file upload was completed |
| [**DeleteFile**](StorageApi.md#deletefile) | **DELETE** /api/canary/storage/{id} | Delete a file |
| [**GetDownloadUrl**](StorageApi.md#getdownloadurl) | **GET** /api/canary/storage/{id}/download-url | Get a presigned download URL for a file |
| [**GetFileDetails**](StorageApi.md#getfiledetails) | **GET** /api/canary/storage/{id} | Get file details |
| [**ListFiles**](StorageApi.md#listfiles) | **GET** /api/canary/storage | List files |
| [**RequestUploadUrl**](StorageApi.md#requestuploadurl) | **POST** /api/canary/storage/upload-url | Request a presigned URL for file upload |

<a id="confirmupload"></a>
# **ConfirmUpload**
> FileDto ConfirmUpload (ConfirmUploadDto confirmUploadDto)

Confirm that a file upload was completed

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
    public class ConfirmUploadExample
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
                FileDto result = apiInstance.ConfirmUpload(confirmUploadDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.ConfirmUpload: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConfirmUploadWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Confirm that a file upload was completed
    ApiResponse<FileDto> response = apiInstance.ConfirmUploadWithHttpInfo(confirmUploadDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.ConfirmUploadWithHttpInfo: " + e.Message);
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

<a id="deletefile"></a>
# **DeleteFile**
> void DeleteFile (string id)

Delete a file

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
    public class DeleteFileExample
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
                apiInstance.DeleteFile(id);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.DeleteFile: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteFileWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a file
    apiInstance.DeleteFileWithHttpInfo(id);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.DeleteFileWithHttpInfo: " + e.Message);
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

<a id="getdownloadurl"></a>
# **GetDownloadUrl**
> PresignedDownloadResponseDto GetDownloadUrl (string id)

Get a presigned download URL for a file

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
    public class GetDownloadUrlExample
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
                PresignedDownloadResponseDto result = apiInstance.GetDownloadUrl(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.GetDownloadUrl: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetDownloadUrlWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get a presigned download URL for a file
    ApiResponse<PresignedDownloadResponseDto> response = apiInstance.GetDownloadUrlWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.GetDownloadUrlWithHttpInfo: " + e.Message);
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

<a id="getfiledetails"></a>
# **GetFileDetails**
> FileDto GetFileDetails (string id)

Get file details

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
    public class GetFileDetailsExample
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
                FileDto result = apiInstance.GetFileDetails(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.GetFileDetails: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetFileDetailsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get file details
    ApiResponse<FileDto> response = apiInstance.GetFileDetailsWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.GetFileDetailsWithHttpInfo: " + e.Message);
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

<a id="listfiles"></a>
# **ListFiles**
> ListFilesResponseDto ListFiles (decimal? limit = null, decimal? offset = null, string? tag = null, string? status = null, string? relatedEntityId = null, string? relatedEntityType = null)

List files

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
    public class ListFilesExample
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
            var limit = 50;  // decimal? | Maximum number of records to return (optional) 
            var offset = 0;  // decimal? | Number of records to skip (optional) 
            var tag = "tag_example";  // string? | Filter by tag (optional) 
            var status = "pending";  // string? |  (optional) 
            var relatedEntityId = "relatedEntityId_example";  // string? |  (optional) 
            var relatedEntityType = "relatedEntityType_example";  // string? |  (optional) 

            try
            {
                // List files
                ListFilesResponseDto result = apiInstance.ListFiles(limit, offset, tag, status, relatedEntityId, relatedEntityType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.ListFiles: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListFilesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List files
    ApiResponse<ListFilesResponseDto> response = apiInstance.ListFilesWithHttpInfo(limit, offset, tag, status, relatedEntityId, relatedEntityType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.ListFilesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
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

<a id="requestuploadurl"></a>
# **RequestUploadUrl**
> PresignedUploadResponseDto RequestUploadUrl (RequestUploadUrlDto requestUploadUrlDto)

Request a presigned URL for file upload

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
    public class RequestUploadUrlExample
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
                PresignedUploadResponseDto result = apiInstance.RequestUploadUrl(requestUploadUrlDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling StorageApi.RequestUploadUrl: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RequestUploadUrlWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Request a presigned URL for file upload
    ApiResponse<PresignedUploadResponseDto> response = apiInstance.RequestUploadUrlWithHttpInfo(requestUploadUrlDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling StorageApi.RequestUploadUrlWithHttpInfo: " + e.Message);
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

