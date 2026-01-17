# Cashful.Sdk.Model.CreatePaymentIntentDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**CustomerId** | **string** | The unique identifier of the customer. Optional for payment intents that don&#39;t require a customer. | [optional] 
**PaymentMethodId** | **string** | The unique identifier of the payment method. Optional if payment method will be collected later. | [optional] 
**Amount** | **decimal** | The amount to charge in the smallest currency unit (cents) | 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Mode** | **string** | The mode of the payment intent | [optional] [default to ModeEnum.Payment]
**Description** | **string** | Optional description for the payment | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | [optional] 
**IdempotencyKey** | **string** | A unique key to prevent duplicate charges. If not provided, one will be generated. | [optional] 
**ExpiresAt** | **DateTimeOffset** | When the payment intent expires. Defaults to 24 hours from creation. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

