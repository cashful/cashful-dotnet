# Cashful.Model.PaymentIntentResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique payment intent ID | 
**MerchantId** | **string** | Merchant ID | 
**CustomerId** | **string** | Customer ID (if associated) | 
**PaymentMethodId** | **string** | Payment method ID (if attached) | 
**Amount** | **decimal** | Amount in smallest currency unit | 
**Currency** | **string** | Three-letter currency code | 
**Status** | **string** | Current status of the payment intent | 
**Mode** | **string** | Mode of the payment intent | 
**Description** | **string** | Description | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Custom metadata | [optional] 
**IdempotencyKey** | **string** | Unique idempotency key for this payment intent | 
**ExpiresAt** | **DateTimeOffset** | When the payment intent expires | 
**CreatedAt** | **DateTimeOffset** | Creation timestamp | 
**UpdatedAt** | **DateTimeOffset** | Last update timestamp | 
**DeletedAt** | **DateTimeOffset?** | Deletion timestamp (for soft deletes) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

