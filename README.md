# Org.OpenAPITools - the C# library for the Screenshot Capture API

Webseite-Herunterladen.de Screenshot Capture is a very simple but powerful screenshot API that anyone can easily use to create pixel-perfect website screenshots. It always uses a recent version of Chrome to ensure that all modern web features are fully supported and rendering is exactly as your customers would expect.

This C# SDK is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- SDK version: 1.0.0
- Build package: org.openapitools.codegen.languages.CSharpClientCodegen

## Frameworks supported


- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

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

## Installation

Run the following command to generate the DLL

- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:

```csharp
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

```


## Packaging

A `.nuspec` is included with the project. You can follow the Nuget quickstart to [create](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#create-the-package) and [publish](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#publish-the-package) packages.

This `.nuspec` uses placeholders from the `.csproj`, so build the `.csproj` directly:

```
nuget pack -Build -OutputDirectory out Org.OpenAPITools.csproj
```

Then, publish to a [local feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/local-feeds) or [other host](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview) and consume the new package via Nuget as usual.


## Getting Started

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class Example
    {
        public static void Main()
        {

            Configuration.Default.BasePath = "https://api.webseite-herunterladen.de/v1";
            var apiInstance = new ScreenshotApi(Configuration.Default);
            var token = token_example;  // string | A valid token is needed to make paid API calls. Tokens can be managed from your account.
            var hash = hash_example;  // string | The hash value is for authenticated requests. If you want to publish this URL, you should use the authenticated requests.
            var url = url_example;  // string | The URL of the website you want to capture. Please include the protocol (http:// or https://).
            var fileType = fileType_example;  // string | The image file format of the captured screenshot. Either png, jpeg or PDF with 72 dpi. (optional) 
            var ttl = 789;  // long? | Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days. (optional) 
            var invalidate = true;  // bool? | Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged. (optional) 
            var full = true;  // bool? | Set this parameter to true if you want to screenshot the whole web page in full size. (optional) 
            var lazyloadScroll = true;  // bool? | Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen. (optional)  (default to false)
            var delay = 789;  // long? | The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds. (optional) 
            var width = 789;  // long? | The width, in pixels, of the browser viewport to use. (optional)  (default to 1920)
            var height = 789;  // long? | The height, in pixels, of the browser viewport to use. Ignored if you set full to true. (optional)  (default to 1080)
            var quality = 789;  // long? | The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression. (optional)  (default to 90)
            var scale = 8.14;  // decimal? | The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced. (optional)  (default to 1.0M)
            var x = 789;  // long? | The starting point of a section screenshot on the X axis. (optional)  (default to 0)
            var y = 789;  // long? | The starting point of a section screenshot on the Y axis. (optional)  (default to 0)
            var redirect = true;  // bool? | If you set Redirect, the response will be a 302 redirect to the screenshot file in our CDN. (optional)  (default to false)
            var language = language_example;  // string | Sets the Accept-Language header on requests to the target URL so that you can take screenshots from a website with a specific language. (optional) 
            var randomUserAgent = true;  // bool? | Sets a random user agent header to emulate a different devices when taking screenshots. (optional)  (default to false)
            var userAgent = userAgent_example;  // string | Sets the user agent header to emulate a specific device when taking screenshots. (optional) 
            var headers = headers_example;  // string | A semicolon-separated list of header parameters to be used when capturing the screenshot. Each header should be passed as a key-value pair and multiple pairs should be separated by a semicolon. (optional) 
            var cookies = cookies_example;  // string | A semicolon-separated list of cookies to be used when capturing the screenshot. Each cookies should be passed as a key-value pair and multiple pairs should be separated by a semicolon. (optional) 
            var css = css_example;  // string | Inject your custom CSS. (optional) 
            var js = js_example;  // string | Inject your custom Javascript. (optional) 
            var wait = wait_example;  // string | Wait until the specified CSS selector matches an element present in the page before taking a screenshot. The process is canceled after 60 seconds. (optional) 
            var element = element_example;  // string | Takes a screenshot of the first element matched by the specified CSS selector. This is ignored if full is true. (This option cannot be used with the PDF export format.) (optional) 
            var timezone = timezone_example;  // string | The IANA time zone identifier used for this capture. (optional)  (default to "Europe/Berlin")
            var device = device_example;  // string | The device used in the emulation. (optional) 
            var latitude = 8.14;  // decimal? | The latitude used in the emulation of the geo-location. (optional)  (default to 0.0M)
            var longitude = 8.14;  // decimal? | The longitude used in the emulation of the geo-location. (optional)  (default to 0.0M)
            var accuracy = 8.14;  // decimal? | The accuracy in meters used in the emulation of the geo-location. (optional)  (default to 2.0M)
            var proxy = proxy_example;  // string | Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280 (optional) 
            var adblock = true;  // bool? | Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads. (optional)  (default to false)
            var hideCookieBanners = true;  // bool? | Prevent cookie banners and pop-ups from being displayed. The best possible result is tried. (optional)  (default to false)

            try
            {
                System.IO.Stream result = apiInstance.PlaceScreenshotOrderAuthenticated(token, hash, url, fileType, ttl, invalidate, full, lazyloadScroll, delay, width, height, quality, scale, x, y, redirect, language, randomUserAgent, userAgent, headers, cookies, css, js, wait, element, timezone, device, latitude, longitude, accuracy, proxy, adblock, hideCookieBanners);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ScreenshotApi.PlaceScreenshotOrderAuthenticated: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }

        }
    }
}
```

## Documentation for API Endpoints

All URIs are relative to *https://api.webseite-herunterladen.de/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ScreenshotApi* | [**PlaceScreenshotOrderAuthenticated**](docs/ScreenshotApi.md#placescreenshotorderauthenticated) | **GET** /capture/{token}/{hash} | 
*ScreenshotApi* | [**PlaceScreenshotOrderUnauthenticated**](docs/ScreenshotApi.md#placescreenshotorderunauthenticated) | **GET** /capture/{token} | 


## Documentation for Models

 - [Model.ErrorModel](docs/ErrorModel.md)


## Documentation for Authorization

All endpoints do not require authorization.
