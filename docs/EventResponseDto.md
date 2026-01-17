# Cashful.Sdk.Model.EventResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique identifier for the event | 
**MerchantId** | **string** | ID of the merchant this event belongs to | 
**WebhookEndpointId** | **string** | ID of the webhook endpoint this event was sent to | 
**Type** | **string** | Event type name | 
**Data** | **Object** | Event data payload | 
**Status** | **string** | Current delivery status of the event | 
**Attempts** | **decimal** | Number of delivery attempts | 
**RelatedEntityId** | **string** | ID of the related entity | [optional] 
**RelatedEntityType** | **string** | Type of the related entity | [optional] 
**LastAttemptAt** | **DateTimeOffset** | Timestamp of the last delivery attempt | [optional] 
**NextRetryAt** | **DateTimeOffset** | Timestamp for the next retry attempt | [optional] 
**DeliveredAt** | **DateTimeOffset** | Timestamp when the event was successfully delivered | [optional] 
**CreatedAt** | **DateTimeOffset** | Timestamp when the event was created | 
**UpdatedAt** | **DateTimeOffset** | Timestamp when the event was last updated | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

