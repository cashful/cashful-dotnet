# Cashful.Model.CreateWebhookEndpointDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**MerchantId** | **string** | The ID of the merchant whose balance is being requested. If omitted, defaults to the authenticated merchant. | [optional] 
**Url** | **string** | The URL where webhook events will be sent | 
**Events** | **List&lt;string&gt;** | Array of event types to listen for | 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Optional custom metadata | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

