# Cashful.Sdk.Model.SocialSignInDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Provider** | **string** | The social provider to sign in with | 
**CallbackURL** | **string** | Callback URL to redirect to after the user has signed in | [optional] 
**NewUserCallbackURL** | **string** | Callback URL for new users | [optional] 
**ErrorCallbackURL** | **string** | Callback URL for errors | [optional] 
**DisableRedirect** | **bool** | Disable automatic redirection to the provider | [optional] 
**IdToken** | **Object** | ID token from provider | [optional] 
**Scopes** | **List&lt;string&gt;** | Array of scopes to request from the provider | [optional] 
**RequestSignUp** | **bool** | Explicitly request sign-up | [optional] 
**LoginHint** | **string** | Login hint for the authorization code request | [optional] 
**AdditionalData** | **string** | Additional data for the request | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

