# Cloudmersive.APIClient.NET.Currency.Api.CurrencyExchangeApi

All URIs are relative to *https://api.cloudmersive.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CurrencyExchangeConvertCurrency**](CurrencyExchangeApi.md#currencyexchangeconvertcurrency) | **POST** /currency/exchange-rates/convert/{source}/to/{destination} | Converts a price from the source currency into the destination currency
[**CurrencyExchangeGetAvailableCurrencies**](CurrencyExchangeApi.md#currencyexchangegetavailablecurrencies) | **POST** /currency/exchange-rates/list-available | Get a list of available currencies and corresponding countries
[**CurrencyExchangeGetExchangeRate**](CurrencyExchangeApi.md#currencyexchangegetexchangerate) | **POST** /currency/exchange-rates/get/{source}/to/{destination} | Gets the exchange rate from the source currency into the destination currency


<a name="currencyexchangeconvertcurrency"></a>
# **CurrencyExchangeConvertCurrency**
> ConvertedCurrencyResult CurrencyExchangeConvertCurrency (string source, string destination, double? sourcePrice)

Converts a price from the source currency into the destination currency

Automatically converts the price in the source currency into the destination currency using the latest available currency exchange rate data.

### Example
```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NET.Currency.Api;
using Cloudmersive.APIClient.NET.Currency.Client;
using Cloudmersive.APIClient.NET.Currency.Model;

namespace Example
{
    public class CurrencyExchangeConvertCurrencyExample
    {
        public void main()
        {
            // Configure API key authorization: Apikey
            Configuration.Default.AddApiKey("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("Apikey", "Bearer");

            var apiInstance = new CurrencyExchangeApi();
            var source = source_example;  // string | Source currency three-digit code (ISO 4217), e.g. USD, EUR, etc.
            var destination = destination_example;  // string | Destination currency three-digit code (ISO 4217), e.g. USD, EUR, etc.
            var sourcePrice = 1.2;  // double? | Input price, such as 19.99 in source currency

            try
            {
                // Converts a price from the source currency into the destination currency
                ConvertedCurrencyResult result = apiInstance.CurrencyExchangeConvertCurrency(source, destination, sourcePrice);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling CurrencyExchangeApi.CurrencyExchangeConvertCurrency: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Source currency three-digit code (ISO 4217), e.g. USD, EUR, etc. | 
 **destination** | **string**| Destination currency three-digit code (ISO 4217), e.g. USD, EUR, etc. | 
 **sourcePrice** | **double?**| Input price, such as 19.99 in source currency | 

### Return type

[**ConvertedCurrencyResult**](ConvertedCurrencyResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: application/json, text/json
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="currencyexchangegetavailablecurrencies"></a>
# **CurrencyExchangeGetAvailableCurrencies**
> AvailableCurrencyResponse CurrencyExchangeGetAvailableCurrencies ()

Get a list of available currencies and corresponding countries

Enumerates available currencies and the countries that correspond to these currencies.

### Example
```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NET.Currency.Api;
using Cloudmersive.APIClient.NET.Currency.Client;
using Cloudmersive.APIClient.NET.Currency.Model;

namespace Example
{
    public class CurrencyExchangeGetAvailableCurrenciesExample
    {
        public void main()
        {
            // Configure API key authorization: Apikey
            Configuration.Default.AddApiKey("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("Apikey", "Bearer");

            var apiInstance = new CurrencyExchangeApi();

            try
            {
                // Get a list of available currencies and corresponding countries
                AvailableCurrencyResponse result = apiInstance.CurrencyExchangeGetAvailableCurrencies();
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling CurrencyExchangeApi.CurrencyExchangeGetAvailableCurrencies: " + e.Message );
            }
        }
    }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**AvailableCurrencyResponse**](AvailableCurrencyResponse.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="currencyexchangegetexchangerate"></a>
# **CurrencyExchangeGetExchangeRate**
> ExchangeRateResult CurrencyExchangeGetExchangeRate (string source, string destination)

Gets the exchange rate from the source currency into the destination currency

Automatically gets the exchange rate from the source currency into the destination currency using the latest available currency exchange rate data.

### Example
```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NET.Currency.Api;
using Cloudmersive.APIClient.NET.Currency.Client;
using Cloudmersive.APIClient.NET.Currency.Model;

namespace Example
{
    public class CurrencyExchangeGetExchangeRateExample
    {
        public void main()
        {
            // Configure API key authorization: Apikey
            Configuration.Default.AddApiKey("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("Apikey", "Bearer");

            var apiInstance = new CurrencyExchangeApi();
            var source = source_example;  // string | Source currency three-digit code (ISO 4217), e.g. USD, EUR, etc.
            var destination = destination_example;  // string | Destination currency three-digit code (ISO 4217), e.g. USD, EUR, etc.

            try
            {
                // Gets the exchange rate from the source currency into the destination currency
                ExchangeRateResult result = apiInstance.CurrencyExchangeGetExchangeRate(source, destination);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling CurrencyExchangeApi.CurrencyExchangeGetExchangeRate: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **source** | **string**| Source currency three-digit code (ISO 4217), e.g. USD, EUR, etc. | 
 **destination** | **string**| Destination currency three-digit code (ISO 4217), e.g. USD, EUR, etc. | 

### Return type

[**ExchangeRateResult**](ExchangeRateResult.md)

### Authorization

[Apikey](../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

