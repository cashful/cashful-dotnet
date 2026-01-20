# Cashful.Model.CreateCheckoutSessionDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**CustomerId** | **string** | The unique identifier of the customer | [optional] 
**ProductId** | **string** | The unique identifier of the product | [optional] 
**SuccessUrl** | **string** | The URL to redirect to on successful payment | 
**CancelUrl** | **string** | The URL to redirect to if customer cancels | 
**LineItems** | [**List&lt;LineItemDto&gt;**](LineItemDto.md) | Array of line items for the checkout | [optional] 
**TotalAmount** | **decimal** | The total amount in the smallest currency unit | [optional] 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Mode** | **string** | The checkout mode (e.g., &#39;payment&#39;) | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

