# Cashful.Sdk.Model.WebhookEndpointResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique identifier for the webhook endpoint | 
**MerchantId** | **string** | The merchant ID this webhook belongs to | 
**Url** | **string** | The URL where webhook events are sent | 
**Events** | **List&lt;string&gt;** | Array of event types subscribed to | 
**Active** | **bool** | Whether the webhook endpoint is active | 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Custom metadata attached to the webhook endpoint | [optional] 
**CreatedAt** | **DateTimeOffset** | When the webhook endpoint was created | 
**UpdatedAt** | **DateTimeOffset** | When the webhook endpoint was last updated | 
**DeletedAt** | **DateTimeOffset** | When the webhook endpoint was deleted (soft delete) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

