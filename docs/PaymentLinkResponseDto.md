# Cashful.Model.PaymentLinkResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Name** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**MerchantId** | **string** |  | 
**Url** | **string** |  | 
**LineItems** | [**List&lt;LineItemDto&gt;**](LineItemDto.md) |  | [optional] 
**CustomerId** | **string** |  | [optional] 
**TotalAmount** | **decimal** |  | 
**Currency** | **string** |  | 
**Mode** | **string** |  | 
**Active** | **bool** |  | 
**SuccessUrl** | **string** |  | 
**CancelUrl** | **string** |  | 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | 
**HostedCheckoutConfig** | [**HostedCheckoutConfigDto**](HostedCheckoutConfigDto.md) | Configuration for the hosted checkout page | [optional] 
**CreatedAt** | **DateTimeOffset** |  | 
**UpdatedAt** | **DateTimeOffset** |  | 
**DeletedAt** | **DateTimeOffset** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

