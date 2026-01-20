# Cashful.Model.CreateTransferDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**FromCustomerId** | **string** | The unique identifier of the customer sending the transfer | 
**ToCustomerId** | **string** | The unique identifier of the customer receiving the transfer | 
**Amount** | **decimal** | The amount to transfer in the smallest currency unit | 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Description** | **string** | Optional description for the transfer | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

