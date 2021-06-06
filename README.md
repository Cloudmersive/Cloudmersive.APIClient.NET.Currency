# Cloudmersive.APIClient.NET.Currency - the C# library for the currencyapi

The currency APIs help you retrieve exchange rates and convert prices between currencies easily.

This C# SDK is for the [Cloudmersive Validate API](https://www.cloudmersive.com/validate-api):

- API version: v1
- SDK version: 3.0.3
- Build package: io.swagger.codegen.languages.CSharpClientCodegen

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

<a name="dependencies"></a>
## Dependencies
- [RestSharp](https://www.nuget.org/packages/RestSharp) - 105.1.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 7.0.0 or later
- [JsonSubTypes](https://www.nuget.org/packages/JsonSubTypes/) - 1.2.0 or later

The DLLs included in the package may not be the latest version. We recommend using [NuGet](https://docs.nuget.org/consume/installing-nuget) to obtain the latest version of the packages:
```
Install-Package RestSharp
Install-Package Newtonsoft.Json
Install-Package JsonSubTypes
```

NOTE: RestSharp versions greater than 105.1.0 have a bug which causes file uploads to fail. See [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742)

<a name="installation"></a>
## Installation
Run the following command to generate the DLL
- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using Cloudmersive.APIClient.NET.Currency.Api;
using Cloudmersive.APIClient.NET.Currency.Client;
using Cloudmersive.APIClient.NET.Currency.Model;
```
<a name="packaging"></a>
## Packaging

A `.nuspec` is included with the project. You can follow the Nuget quickstart to [create](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#create-the-package) and [publish](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#publish-the-package) packages.

This `.nuspec` uses placeholders from the `.csproj`, so build the `.csproj` directly:

```
nuget pack -Build -OutputDirectory out Cloudmersive.APIClient.NET.Currency.csproj
```

Then, publish to a [local feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/local-feeds) or [other host](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview) and consume the new package via Nuget as usual.

<a name="getting-started"></a>
## Getting Started

```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NET.Currency.Api;
using Cloudmersive.APIClient.NET.Currency.Client;
using Cloudmersive.APIClient.NET.Currency.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {

            // Configure API key authorization: Apikey
            Configuration.Default.ApiKey.Add("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.ApiKeyPrefix.Add("Apikey", "Bearer");

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

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.cloudmersive.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CurrencyExchangeApi* | [**CurrencyExchangeConvertCurrency**](docs/CurrencyExchangeApi.md#currencyexchangeconvertcurrency) | **POST** /currency/exchange-rates/convert/{source}/to/{destination} | Converts a price from the source currency into the destination currency
*CurrencyExchangeApi* | [**CurrencyExchangeGetAvailableCurrencies**](docs/CurrencyExchangeApi.md#currencyexchangegetavailablecurrencies) | **POST** /currency/exchange-rates/list-available | Get a list of available currencies and corresponding countries
*CurrencyExchangeApi* | [**CurrencyExchangeGetExchangeRate**](docs/CurrencyExchangeApi.md#currencyexchangegetexchangerate) | **POST** /currency/exchange-rates/get/{source}/to/{destination} | Gets the exchange rate from the source currency into the destination currency


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.AvailableCurrency](docs/AvailableCurrency.md)
 - [Model.AvailableCurrencyResponse](docs/AvailableCurrencyResponse.md)
 - [Model.ConvertedCurrencyResult](docs/ConvertedCurrencyResult.md)
 - [Model.ExchangeRateResult](docs/ExchangeRateResult.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="Apikey"></a>
### Apikey

- **Type**: API key
- **API key parameter name**: Apikey
- **Location**: HTTP header

