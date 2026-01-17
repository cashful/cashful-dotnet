# Cashful.Sdk.Model.CheckoutSessionResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique identifier | 
**CreatedAt** | **DateTimeOffset** |  | 
**UpdatedAt** | **DateTimeOffset** |  | 
**DeletedAt** | **DateTimeOffset** |  | [optional] 
**MerchantId** | **string** |  | 
**CustomerId** | **string** |  | [optional] 
**SessionUrl** | **string** |  | 
**SuccessUrl** | **string** |  | 
**CancelUrl** | **string** |  | 
**LineItems** | [**List&lt;LineItemDto&gt;**](LineItemDto.md) |  | [optional] 
**TotalAmount** | **decimal** |  | [optional] 
**Currency** | **string** |  | 
**Mode** | **string** |  | [optional] 
**Status** | **string** |  | 
**ExpiresAt** | **DateTimeOffset** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

