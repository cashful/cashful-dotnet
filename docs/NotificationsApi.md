# Cashful.Sdk.Api.NotificationsApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**SendEmail**](NotificationsApi.md#sendemail) | **POST** /api/canary/notifications/email | Send an email notification |
| [**SendMultiChannelNotification**](NotificationsApi.md#sendmultichannelnotification) | **POST** /api/canary/notifications/multi-channel | Send notifications via multiple channels |
| [**SendNotification**](NotificationsApi.md#sendnotification) | **POST** /api/canary/notifications/send | Send a notification via specified channel |
| [**SendSms**](NotificationsApi.md#sendsms) | **POST** /api/canary/notifications/sms | Send an SMS notification |

<a id="sendemail"></a>
# **SendEmail**
> SendEmail200Response SendEmail (SendEmailDto sendEmailDto)

Send an email notification

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
    public class SendEmailExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new NotificationsApi(httpClient, config, httpClientHandler);
            var sendEmailDto = new SendEmailDto(); // SendEmailDto | 

            try
            {
                // Send an email notification
                SendEmail200Response result = apiInstance.SendEmail(sendEmailDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotificationsApi.SendEmail: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendEmailWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send an email notification
    ApiResponse<SendEmail200Response> response = apiInstance.SendEmailWithHttpInfo(sendEmailDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotificationsApi.SendEmailWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **sendEmailDto** | [**SendEmailDto**](SendEmailDto.md) |  |  |

### Return type

[**SendEmail200Response**](SendEmail200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Email sent successfully |  -  |
| **400** | Bad request |  -  |
| **500** | Failed to send email |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendmultichannelnotification"></a>
# **SendMultiChannelNotification**
> SendMultiChannelNotification200Response SendMultiChannelNotification ()

Send notifications via multiple channels

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
    public class SendMultiChannelNotificationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new NotificationsApi(httpClient, config, httpClientHandler);

            try
            {
                // Send notifications via multiple channels
                SendMultiChannelNotification200Response result = apiInstance.SendMultiChannelNotification();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotificationsApi.SendMultiChannelNotification: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendMultiChannelNotificationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send notifications via multiple channels
    ApiResponse<SendMultiChannelNotification200Response> response = apiInstance.SendMultiChannelNotificationWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotificationsApi.SendMultiChannelNotificationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**SendMultiChannelNotification200Response**](SendMultiChannelNotification200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Notifications sent |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendnotification"></a>
# **SendNotification**
> void SendNotification (NotificationDto notificationDto)

Send a notification via specified channel

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
    public class SendNotificationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new NotificationsApi(httpClient, config, httpClientHandler);
            var notificationDto = new NotificationDto(); // NotificationDto | 

            try
            {
                // Send a notification via specified channel
                apiInstance.SendNotification(notificationDto);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotificationsApi.SendNotification: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendNotificationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send a notification via specified channel
    apiInstance.SendNotificationWithHttpInfo(notificationDto);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotificationsApi.SendNotificationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **notificationDto** | [**NotificationDto**](NotificationDto.md) |  |  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Notification sent successfully |  -  |
| **400** | Bad request |  -  |
| **500** | Failed to send notification |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendsms"></a>
# **SendSms**
> SendSms200Response SendSms (SendSmsDto sendSmsDto)

Send an SMS notification

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
    public class SendSmsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.cashful.africa";
            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new NotificationsApi(httpClient, config, httpClientHandler);
            var sendSmsDto = new SendSmsDto(); // SendSmsDto | 

            try
            {
                // Send an SMS notification
                SendSms200Response result = apiInstance.SendSms(sendSmsDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling NotificationsApi.SendSms: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendSmsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send an SMS notification
    ApiResponse<SendSms200Response> response = apiInstance.SendSmsWithHttpInfo(sendSmsDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling NotificationsApi.SendSmsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **sendSmsDto** | [**SendSmsDto**](SendSmsDto.md) |  |  |

### Return type

[**SendSms200Response**](SendSms200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | SMS sent successfully |  -  |
| **400** | Bad request |  -  |
| **500** | Failed to send SMS |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

