# Cashful.Api.EventsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateEvent**](EventsApi.md#createevent) | **POST** /api/canary/events | Create Event |
| [**ListEventTypes**](EventsApi.md#listeventtypes) | **GET** /api/canary/events/types | List Event Types |
| [**ListEvents**](EventsApi.md#listevents) | **GET** /api/canary/events | List Events |

<a id="createevent"></a>
# **CreateEvent**
> void CreateEvent (CreateEventDto createEventDto)

Create Event

Records a new event and triggers associated webhooks.

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
    public class CreateEventExample
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
            var apiInstance = new EventsApi(httpClient, config, httpClientHandler);
            var createEventDto = new CreateEventDto(); // CreateEventDto | 

            try
            {
                // Create Event
                apiInstance.CreateEvent(createEventDto);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EventsApi.CreateEvent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateEventWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Event
    apiInstance.CreateEventWithHttpInfo(createEventDto);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EventsApi.CreateEventWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createEventDto** | [**CreateEventDto**](CreateEventDto.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Event successfully created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listeventtypes"></a>
# **ListEventTypes**
> ListEventTypesResponseDto ListEventTypes ()

List Event Types

Retrieves all available event types that can be sent or subscribed to.

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
    public class ListEventTypesExample
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
            var apiInstance = new EventsApi(httpClient, config, httpClientHandler);

            try
            {
                // List Event Types
                ListEventTypesResponseDto result = apiInstance.ListEventTypes();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EventsApi.ListEventTypes: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListEventTypesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Event Types
    ApiResponse<ListEventTypesResponseDto> response = apiInstance.ListEventTypesWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EventsApi.ListEventTypesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**ListEventTypesResponseDto**](ListEventTypesResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved event types |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listevents"></a>
# **ListEvents**
> ListEventsResponseDto ListEvents (string merchantId, decimal? limit = null, decimal? offset = null, string? filter = null, string? sort = null, string? order = null, string? type = null, string? status = null, string? startDate = null, string? endDate = null)

List Events

Retrieves a log of all API events for debugging and logging.

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
    public class ListEventsExample
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
            var apiInstance = new EventsApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant whose events are being requested. This parameter is required.
            var limit = 50;  // decimal? | Maximum number of records to return (optional) 
            var offset = 0;  // decimal? | Number of records to skip (optional) 
            var filter = {"ids":["prod_123","prod_456"]};  // string? | JSON string used for dynamic filtering (optional) 
            var sort = createdAt;  // string? | Field name to sort by (optional) 
            var order = DESC;  // string? | Sort direction (ASC or DESC) (optional) 
            var type = "type_example";  // string? | Filter by event type (optional) 
            var status = "pending";  // string? | Filter by event status (optional) 
            var startDate = "startDate_example";  // string? | Filter by start date (optional) 
            var endDate = "endDate_example";  // string? | Filter by end date (optional) 

            try
            {
                // List Events
                ListEventsResponseDto result = apiInstance.ListEvents(merchantId, limit, offset, filter, sort, order, type, status, startDate, endDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling EventsApi.ListEvents: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListEventsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Events
    ApiResponse<ListEventsResponseDto> response = apiInstance.ListEventsWithHttpInfo(merchantId, limit, offset, filter, sort, order, type, status, startDate, endDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling EventsApi.ListEventsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **merchantId** | **string** | The ID of the merchant whose events are being requested. This parameter is required. |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional]  |
| **offset** | **decimal?** | Number of records to skip | [optional]  |
| **filter** | **string?** | JSON string used for dynamic filtering | [optional]  |
| **sort** | **string?** | Field name to sort by | [optional]  |
| **order** | **string?** | Sort direction (ASC or DESC) | [optional]  |
| **type** | **string?** | Filter by event type | [optional]  |
| **status** | **string?** | Filter by event status | [optional]  |
| **startDate** | **string?** | Filter by start date | [optional]  |
| **endDate** | **string?** | Filter by end date | [optional]  |

### Return type

[**ListEventsResponseDto**](ListEventsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved events |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

