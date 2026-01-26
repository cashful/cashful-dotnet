# Cashful.Model.CreatePaymentLinkDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | The name of the payment link | [optional] 
**Description** | **string** | A description of the payment link | [optional] 
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**LineItems** | [**List&lt;LineItemDto&gt;**](LineItemDto.md) | Array of line items for the checkout | [optional] 
**CustomerId** | **string** | The unique identifier of the customer | [optional] 
**TotalAmount** | **decimal** | The total amount in the smallest currency unit | 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Mode** | **string** | The payment mode (e.g., &#39;payment&#39; or &#39;subscription&#39;) | 
**SuccessUrl** | **string** | The URL to redirect to on successful payment | 
**CancelUrl** | **string** | The URL to redirect to if customer cancels | 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | 
**HostedCheckoutConfig** | [**HostedCheckoutConfigDto**](HostedCheckoutConfigDto.md) | Configuration for the hosted checkout page | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

