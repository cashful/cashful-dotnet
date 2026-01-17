# Cashful.Sdk.Model.CreatePaymentLinkDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**ProductId** | **string** | The unique identifier of the product | [optional] 
**CustomerId** | **string** | The unique identifier of the customer | [optional] 
**Amount** | **decimal** | The amount in the smallest currency unit | [optional] 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Mode** | **string** | The payment mode (e.g., &#39;payment&#39; or &#39;subscription&#39;) | 
**SuccessUrl** | **string** | The URL to redirect to on successful payment | 
**CancelUrl** | **string** | The URL to redirect to if customer cancels | 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

