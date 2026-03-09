# Cashful.Model.InitiatePaymentResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**IveriParams** | [**IveriParamsDto**](IveriParamsDto.md) | Parameters to POST to iVeri 3DS endpoint (only in live mode) | [optional] 
**IVeri3dsEndpoint** | **string** | iVeri 3DS endpoint URL to POST the parameters to (only in live mode) | [optional] 
**SandboxMode** | **bool** | Whether sandbox mode is active | [optional] 
**Status** | **string** | Payment status (only in sandbox mode) | [optional] 
**PaymentIntentId** | **string** | Payment intent ID | [optional] 
**TransactionId** | **string** | Transaction ID (only in sandbox mode on success) | [optional] 
**AuthCode** | **string** | Authorization code (only in sandbox mode on success) | [optional] 
**Amount** | **decimal** | Payment amount in smallest currency unit | [optional] 
**Currency** | **string** | Currency code | [optional] 
**Reason** | **string** | Reason for failure (only in sandbox mode on failure) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

