# Cashful.Sdk.Model.PaymentMethodResponseDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique payment method identifier | 
**CustomerId** | **string** | Customer ID this payment method belongs to | 
**Type** | **string** | Payment method type (e.g., card, mobile_money) | 
**Provider** | **string** | Payment provider name (e.g., iveri, mpesa) | 
**Brand** | **string** | Card brand (e.g., Visa, Mastercard) | [optional] 
**Last4** | **string** | Last 4 digits of card number | [optional] 
**ExpiryMonth** | **decimal** | Card expiry month (1-12) | [optional] 
**ExpiryYear** | **decimal** | Card expiry year | [optional] 
**PhoneNumber** | **string** | Phone number for mobile money | [optional] 
**IsDefault** | **bool** | Whether this is the default payment method | 
**CreatedAt** | **DateTimeOffset** | When the payment method was created | 
**UpdatedAt** | **DateTimeOffset** | When the payment method was last updated | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

