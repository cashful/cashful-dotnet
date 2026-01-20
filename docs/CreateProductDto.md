# Cashful.Model.CreateProductDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**Name** | **string** | The name of the product | 
**Description** | **string** | A description of the product | [optional] 
**Amount** | **decimal** | The price of the product in the smallest currency unit | [optional] 
**Currency** | **string** | The three-letter ISO 4217 currency code | 
**Active** | **bool** | Whether the product is active | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

