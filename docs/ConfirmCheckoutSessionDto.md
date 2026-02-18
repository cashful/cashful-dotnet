# Cashful.Model.ConfirmCheckoutSessionDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**EvervaultEncryptedCard** | [**EvervaultEncryptedCardDto**](EvervaultEncryptedCardDto.md) | Evervault encrypted card details | 
**MaskedPan** | **string** | Masked PAN for display purposes | [optional] 
**TokenizeCard** | **bool** | Whether to tokenize the card for future use | [optional] [default to false]
**FirstName** | **string** | Cardholder first name | [optional] 
**LastName** | **string** | Cardholder last name | [optional] 
**PhoneNumber** | **string** | Cardholder phone number | [optional] 
**PaymentDescription** | **string** | Payment description | [optional] 
**MerchantName** | **string** | Merchant name for display | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** | Additional metadata | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

