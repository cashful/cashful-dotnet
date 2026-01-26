# Cashful.Model.UpdatePaymentLinkDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | The name of the payment link | [optional] 
**Description** | **string** | A description of the payment link | [optional] 
**Active** | **bool** | Whether the payment link is active | [optional] 
**TotalAmount** | **decimal** |  | [optional] 
**SuccessUrl** | **string** | The URL to redirect to on successful payment | [optional] 
**CancelUrl** | **string** | The URL to redirect to if customer cancels | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | 
**HostedCheckoutConfig** | [**HostedCheckoutConfigDto**](HostedCheckoutConfigDto.md) | Configuration for the hosted checkout page | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

