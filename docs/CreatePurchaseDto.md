# Cashful.Model.CreatePurchaseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**CustomerId** | **string** | The unique identifier of the customer | 
**ProductId** | **string** | The unique identifier of the product | 
**Amount** | **decimal** | The amount in the smallest currency unit | 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Quantity** | **decimal** | The quantity of items in the purchase | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

