# Cashful.Sdk.Model.InitiatePaymentDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Amount** | **decimal** | Payment amount in the smallest currency unit (e.g., cents) | 
**Currency** | **string** | Three-letter ISO 4217 currency code | 
**MerchantId** | **string** | The unique identifier of the merchant | 
**EvervaultEncryptedCard** | [**EvervaultEncryptedCardDto**](EvervaultEncryptedCardDto.md) | Evervault encrypted card details | 
**PaymentIntentId** | **string** | Payment intent ID (generated if not provided) | [optional] 
**MaskedPan** | **string** | Masked PAN for display purposes | [optional] 
**TokenizeCard** | **bool** | Whether to tokenize the card for future use | [optional] [default to false]
**FirstName** | **string** | Cardholder first name | [optional] 
**LastName** | **string** | Cardholder last name | [optional] 
**PhoneNumber** | **string** | Cardholder phone number | [optional] 
**PaymentDescription** | **string** | Payment description | [optional] 
**MerchantName** | **string** | Merchant name for display | [optional] 
**Metadata** | **Object** | Additional metadata | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

