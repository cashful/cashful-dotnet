# Cashful.Sdk.Api.CustomersApi

All URIs are relative to *https://api.cashful.africa*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCustomer**](CustomersApi.md#createcustomer) | **POST** /api/canary/customers | Create Customer |
| [**GetCustomerBalance**](CustomersApi.md#getcustomerbalance) | **GET** /api/canary/customers/{id}/balance | Get Customer&#39;s Cash Balance |
| [**ListCustomerPaymentMethods**](CustomersApi.md#listcustomerpaymentmethods) | **GET** /api/canary/customers/{id}/payment-methods | List Customer&#39;s Payment Methods |
| [**ListCustomerTransactions**](CustomersApi.md#listcustomertransactions) | **GET** /api/canary/customers/{id}/transactions | List Customer&#39;s Cash Transactions |
| [**ListCustomers**](CustomersApi.md#listcustomers) | **GET** /api/canary/customers | List Customers |
| [**RetrieveCustomer**](CustomersApi.md#retrievecustomer) | **GET** /api/canary/customers/{id} | Retrieve Customer |
| [**UpdateCustomer**](CustomersApi.md#updatecustomer) | **PATCH** /api/canary/customers/{id} | Update Customer |

<a id="createcustomer"></a>
# **CreateCustomer**
> CustomerResponseDto CreateCustomer (CreateCustomerDto createCustomerDto)

Create Customer

Creates a new customer object. This also provisions their \"cash balance\" feature (starting at 0).

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
    public class CreateCustomerExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var createCustomerDto = new CreateCustomerDto(); // CreateCustomerDto | Customer details

            try
            {
                // Create Customer
                CustomerResponseDto result = apiInstance.CreateCustomer(createCustomerDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.CreateCustomer: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateCustomerWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create Customer
    ApiResponse<CustomerResponseDto> response = apiInstance.CreateCustomerWithHttpInfo(createCustomerDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.CreateCustomerWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCustomerDto** | [**CreateCustomerDto**](CreateCustomerDto.md) | Customer details |  |

### Return type

[**CustomerResponseDto**](CustomerResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Customer created successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **409** | Customer with this email already exists |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcustomerbalance"></a>
# **GetCustomerBalance**
> CustomerBalanceDto GetCustomerBalance (string id)

Get Customer's Cash Balance

Retrieves the real-time balance for a single customer's \"cash balance\" (the \"wallet-enabling\" feature).

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
    public class GetCustomerBalanceExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the customer

            try
            {
                // Get Customer's Cash Balance
                CustomerBalanceDto result = apiInstance.GetCustomerBalance(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.GetCustomerBalance: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetCustomerBalanceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Customer's Cash Balance
    ApiResponse<CustomerBalanceDto> response = apiInstance.GetCustomerBalanceWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.GetCustomerBalanceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the customer |  |

### Return type

[**CustomerBalanceDto**](CustomerBalanceDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved customer&#39;s cash balance |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcustomerpaymentmethods"></a>
# **ListCustomerPaymentMethods**
> ListCustomerPaymentMethodsResponseDto ListCustomerPaymentMethods (string id, decimal? limit = null, decimal? offset = null)

List Customer's Payment Methods

Shows all saved payment methods (cards, etc.) for a single customer.

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
    public class ListCustomerPaymentMethodsExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the customer
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 

            try
            {
                // List Customer's Payment Methods
                ListCustomerPaymentMethodsResponseDto result = apiInstance.ListCustomerPaymentMethods(id, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.ListCustomerPaymentMethods: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCustomerPaymentMethodsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Customer's Payment Methods
    ApiResponse<ListCustomerPaymentMethodsResponseDto> response = apiInstance.ListCustomerPaymentMethodsWithHttpInfo(id, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.ListCustomerPaymentMethodsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the customer |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional]  |
| **offset** | **decimal?** | Number of records to skip | [optional]  |

### Return type

[**ListCustomerPaymentMethodsResponseDto**](ListCustomerPaymentMethodsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved customer&#39;s payment methods |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcustomertransactions"></a>
# **ListCustomerTransactions**
> ListCustomerTransactionsResponseDto ListCustomerTransactions (string id, decimal? limit = null, decimal? offset = null)

List Customer's Cash Transactions

Provides the full transaction history for a single customer's \"cash balance\" (Pay-Ins, Purchases, Transfers).

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
    public class ListCustomerTransactionsExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the customer
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 

            try
            {
                // List Customer's Cash Transactions
                ListCustomerTransactionsResponseDto result = apiInstance.ListCustomerTransactions(id, limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.ListCustomerTransactions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCustomerTransactionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Customer's Cash Transactions
    ApiResponse<ListCustomerTransactionsResponseDto> response = apiInstance.ListCustomerTransactionsWithHttpInfo(id, limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.ListCustomerTransactionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the customer |  |
| **limit** | **decimal?** | Maximum number of records to return | [optional]  |
| **offset** | **decimal?** | Number of records to skip | [optional]  |

### Return type

[**ListCustomerTransactionsResponseDto**](ListCustomerTransactionsResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved customer transactions |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcustomers"></a>
# **ListCustomers**
> ListCustomersResponseDto ListCustomers (string merchantId, decimal? limit = null, decimal? offset = null, string? email = null, string? search = null)

List Customers

Retrieves a paginated list of all customers for the merchant.

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
    public class ListCustomersExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var merchantId = "merchantId_example";  // string | The ID of the merchant. This parameter is required.
            var limit = 8.14D;  // decimal? | Maximum number of records to return (optional) 
            var offset = 8.14D;  // decimal? | Number of records to skip (optional) 
            var email = "email_example";  // string? | Filter by email address (optional) 
            var search = "search_example";  // string? | Search across customer fields (optional) 

            try
            {
                // List Customers
                ListCustomersResponseDto result = apiInstance.ListCustomers(merchantId, limit, offset, email, search);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.ListCustomers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCustomersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Customers
    ApiResponse<ListCustomersResponseDto> response = apiInstance.ListCustomersWithHttpInfo(merchantId, limit, offset, email, search);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.ListCustomersWithHttpInfo: " + e.Message);
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
| **email** | **string?** | Filter by email address | [optional]  |
| **search** | **string?** | Search across customer fields | [optional]  |

### Return type

[**ListCustomersResponseDto**](ListCustomersResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved customers list |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retrievecustomer"></a>
# **RetrieveCustomer**
> CustomerResponseDto RetrieveCustomer (string id)

Retrieve Customer

Gets the details for a single customer.

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
    public class RetrieveCustomerExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the customer

            try
            {
                // Retrieve Customer
                CustomerResponseDto result = apiInstance.RetrieveCustomer(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.RetrieveCustomer: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetrieveCustomerWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retrieve Customer
    ApiResponse<CustomerResponseDto> response = apiInstance.RetrieveCustomerWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.RetrieveCustomerWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the customer |  |

### Return type

[**CustomerResponseDto**](CustomerResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully retrieved customer details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatecustomer"></a>
# **UpdateCustomer**
> CustomerResponseDto UpdateCustomer (string id, UpdateCustomerDto updateCustomerDto)

Update Customer

Updates a customer's details (e.g., email, metadata).

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
    public class UpdateCustomerExample
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
            var apiInstance = new CustomersApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | The unique identifier of the customer
            var updateCustomerDto = new UpdateCustomerDto(); // UpdateCustomerDto | Customer update details

            try
            {
                // Update Customer
                CustomerResponseDto result = apiInstance.UpdateCustomer(id, updateCustomerDto);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomersApi.UpdateCustomer: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateCustomerWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update Customer
    ApiResponse<CustomerResponseDto> response = apiInstance.UpdateCustomerWithHttpInfo(id, updateCustomerDto);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomersApi.UpdateCustomerWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | The unique identifier of the customer |  |
| **updateCustomerDto** | [**UpdateCustomerDto**](UpdateCustomerDto.md) | Customer update details |  |

### Return type

[**CustomerResponseDto**](CustomerResponseDto.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Customer updated successfully |  -  |
| **400** | Bad Request - Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **409** | Email already in use by another customer |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

