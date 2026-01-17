# Cashful.Sdk.Model.DebitReturnResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** | Payment status after 3DS authentication | 
**MerchantReference** | **string** | Merchant reference for the payment | 
**PaymentIntentId** | **string** | Payment intent ID | [optional] 
**TransactionId** | **string** | Transaction ID if payment succeeded | [optional] 
**AuthCode** | **string** | Authorization code from payment gateway | [optional] 
**Reason** | **string** | Reason for failure if payment failed | [optional] 
**Amount** | **decimal** | Payment amount in smallest currency unit | [optional] 
**Currency** | **string** | Currency code | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

