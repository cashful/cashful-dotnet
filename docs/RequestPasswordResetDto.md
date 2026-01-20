# Cashful.Model.RequestPasswordResetDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Email** | **string** | The email address of user to send a password reset email to | 
**RedirectTo** | **string** | The URL to redirect user to reset their password. If token isn&#39;t valid or expired, it&#39;ll be redirected with a query parameter &#x60;?error&#x3D;INVALID_TOKEN&#x60;. If token is valid, it&#39;ll be redirected with a query parameter &#x60;?token&#x3D;VALID_TOKEN&#x60; | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

