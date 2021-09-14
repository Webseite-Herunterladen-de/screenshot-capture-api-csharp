# IO.Swagger.Api.ScreenshotApi

All URIs are relative to *https://api.webseite-herunterladen.de/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CaptureScreenshotAuthenticated**](ScreenshotApi.md#capturescreenshotauthenticated) | **GET** /capture/{token}/{hash} | 
[**CaptureScreenshotUnauthenticated**](ScreenshotApi.md#capturescreenshotunauthenticated) | **GET** /capture/{token} | 

<a name="capturescreenshotauthenticated"></a>
# **CaptureScreenshotAuthenticated**
> byte[] CaptureScreenshotAuthenticated (string token, string hash, string url, string fileType = null, long? ttl = null, bool? invalidate = null, bool? full = null, bool? lazyloadScroll = null, long? delay = null, long? width = null, long? height = null, long? quality = null, decimal? scale = null, long? x = null, long? y = null, bool? redirect = null, string language = null, bool? randomUserAgent = null, string userAgent = null, string headers = null, string cookies = null, string css = null, string js = null, string wait = null, string element = null, string timezone = null, string device = null, decimal? latitude = null, decimal? longitude = null, decimal? accuracy = null, string proxy = null, bool? adblock = null, bool? hideCookieBanners = null)



Webseite-Herunterladen.de Screenshot Capture is a very simple but powerful screenshot API that anyone can easily use to create pixel-perfect website screenshots. It always uses a recent version of Chrome to ensure that all modern web features are fully supported and rendering is exactly as your customers would expect.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class CaptureScreenshotAuthenticatedExample
    {
        public void main()
        {
            var apiInstance = new ScreenshotApi();
            var token = token_example;  // string | A valid token is needed to make paid API calls. Tokens can be managed from your account.
            var hash = hash_example;  // string | The hash value is for authenticated requests. If you want to publish this URL, you should use the authenticated requests.
            var url = url_example;  // string | The URL of the website you want to capture. Please include the protocol (http:// or https://).
            var fileType = fileType_example;  // string | The image file format of the captured screenshot. Either png, jpeg, webp or PDF with 72 dpi. (optional)  (default to png)
            var ttl = 789;  // long? | Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days. (optional) 
            var invalidate = true;  // bool? | Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged. (optional) 
            var full = true;  // bool? | Set this parameter to true if you want to screenshot the whole web page in full size. (optional) 
            var lazyloadScroll = true;  // bool? | Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen. (optional)  (default to false)
            var delay = 789;  // long? | The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds. (optional) 
            var width = 789;  // long? | The width, in pixels, of the browser viewport to use. (optional)  (default to 1920)
            var height = 789;  // long? | The height, in pixels, of the browser viewport to use. Ignored if you set full to true. (optional)  (default to 1080)
            var quality = 789;  // long? | The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression. (optional)  (default to 90)
            var scale = 1.2;  // decimal? | The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced. (optional)  (default to 1.0)
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
            var timezone = timezone_example;  // string | The IANA time zone identifier used for this capture. (optional)  (default to Europe/Berlin)
            var device = device_example;  // string | The device used in the emulation. (optional) 
            var latitude = 1.2;  // decimal? | The latitude used in the emulation of the geo-location. (optional)  (default to 0.0)
            var longitude = 1.2;  // decimal? | The longitude used in the emulation of the geo-location. (optional)  (default to 0.0)
            var accuracy = 1.2;  // decimal? | The accuracy in meters used in the emulation of the geo-location. (optional)  (default to 2.0)
            var proxy = proxy_example;  // string | Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280 (optional) 
            var adblock = true;  // bool? | Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads. (optional)  (default to false)
            var hideCookieBanners = true;  // bool? | Prevent cookie banners and pop-ups from being displayed. The best possible result is tried. (optional)  (default to false)

            try
            {
                byte[] result = apiInstance.CaptureScreenshotAuthenticated(token, hash, url, fileType, ttl, invalidate, full, lazyloadScroll, delay, width, height, quality, scale, x, y, redirect, language, randomUserAgent, userAgent, headers, cookies, css, js, wait, element, timezone, device, latitude, longitude, accuracy, proxy, adblock, hideCookieBanners);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling ScreenshotApi.CaptureScreenshotAuthenticated: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**| A valid token is needed to make paid API calls. Tokens can be managed from your account. | 
 **hash** | **string**| The hash value is for authenticated requests. If you want to publish this URL, you should use the authenticated requests. | 
 **url** | **string**| The URL of the website you want to capture. Please include the protocol (http:// or https://). | 
 **fileType** | **string**| The image file format of the captured screenshot. Either png, jpeg, webp or PDF with 72 dpi. | [optional] [default to png]
 **ttl** | **long?**| Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days. | [optional] 
 **invalidate** | **bool?**| Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged. | [optional] 
 **full** | **bool?**| Set this parameter to true if you want to screenshot the whole web page in full size. | [optional] 
 **lazyloadScroll** | **bool?**| Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen. | [optional] [default to false]
 **delay** | **long?**| The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds. | [optional] 
 **width** | **long?**| The width, in pixels, of the browser viewport to use. | [optional] [default to 1920]
 **height** | **long?**| The height, in pixels, of the browser viewport to use. Ignored if you set full to true. | [optional] [default to 1080]
 **quality** | **long?**| The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression. | [optional] [default to 90]
 **scale** | **decimal?**| The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced. | [optional] [default to 1.0]
 **x** | **long?**| The starting point of a section screenshot on the X axis. | [optional] [default to 0]
 **y** | **long?**| The starting point of a section screenshot on the Y axis. | [optional] [default to 0]
 **redirect** | **bool?**| If you set Redirect, the response will be a 302 redirect to the screenshot file in our CDN. | [optional] [default to false]
 **language** | **string**| Sets the Accept-Language header on requests to the target URL so that you can take screenshots from a website with a specific language. | [optional] 
 **randomUserAgent** | **bool?**| Sets a random user agent header to emulate a different devices when taking screenshots. | [optional] [default to false]
 **userAgent** | **string**| Sets the user agent header to emulate a specific device when taking screenshots. | [optional] 
 **headers** | **string**| A semicolon-separated list of header parameters to be used when capturing the screenshot. Each header should be passed as a key-value pair and multiple pairs should be separated by a semicolon. | [optional] 
 **cookies** | **string**| A semicolon-separated list of cookies to be used when capturing the screenshot. Each cookies should be passed as a key-value pair and multiple pairs should be separated by a semicolon. | [optional] 
 **css** | **string**| Inject your custom CSS. | [optional] 
 **js** | **string**| Inject your custom Javascript. | [optional] 
 **wait** | **string**| Wait until the specified CSS selector matches an element present in the page before taking a screenshot. The process is canceled after 60 seconds. | [optional] 
 **element** | **string**| Takes a screenshot of the first element matched by the specified CSS selector. This is ignored if full is true. (This option cannot be used with the PDF export format.) | [optional] 
 **timezone** | **string**| The IANA time zone identifier used for this capture. | [optional] [default to Europe/Berlin]
 **device** | **string**| The device used in the emulation. | [optional] 
 **latitude** | **decimal?**| The latitude used in the emulation of the geo-location. | [optional] [default to 0.0]
 **longitude** | **decimal?**| The longitude used in the emulation of the geo-location. | [optional] [default to 0.0]
 **accuracy** | **decimal?**| The accuracy in meters used in the emulation of the geo-location. | [optional] [default to 2.0]
 **proxy** | **string**| Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280 | [optional] 
 **adblock** | **bool?**| Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads. | [optional] [default to false]
 **hideCookieBanners** | **bool?**| Prevent cookie banners and pop-ups from being displayed. The best possible result is tried. | [optional] [default to false]

### Return type

**byte[]**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/pdf, image/jpeg, image/png, image/webp

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
<a name="capturescreenshotunauthenticated"></a>
# **CaptureScreenshotUnauthenticated**
> byte[] CaptureScreenshotUnauthenticated (string token, string url, string fileType = null, long? ttl = null, bool? invalidate = null, bool? full = null, bool? lazyloadScroll = null, long? delay = null, long? width = null, long? height = null, long? quality = null, decimal? scale = null, long? x = null, long? y = null, bool? redirect = null, string language = null, bool? randomUserAgent = null, string userAgent = null, string headers = null, string cookies = null, string css = null, string js = null, string wait = null, string element = null, string timezone = null, string device = null, decimal? latitude = null, decimal? longitude = null, decimal? accuracy = null, string proxy = null, bool? adblock = null, bool? hideCookieBanners = null)



Webseite-Herunterladen.de Screenshot Capture is a very simple but powerful screenshot API that anyone can easily use to create pixel-perfect website screenshots. It always uses a recent version of Chrome to ensure that all modern web features are fully supported and rendering is exactly as your customers would expect.

### Example
```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class CaptureScreenshotUnauthenticatedExample
    {
        public void main()
        {
            var apiInstance = new ScreenshotApi();
            var token = token_example;  // string | A valid token is needed to make paid API calls. Tokens can be managed from your account.
            var url = url_example;  // string | The URL of the website you want to capture. Please include the protocol (http:// or https://).
            var fileType = fileType_example;  // string | The image file format of the captured screenshot. Either png, jpeg, webp or PDF with 72 dpi. (optional)  (default to png)
            var ttl = 789;  // long? | Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days. (optional) 
            var invalidate = true;  // bool? | Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged. (optional) 
            var full = true;  // bool? | Set this parameter to true if you want to screenshot the whole web page in full size. (optional) 
            var lazyloadScroll = true;  // bool? | Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen. (optional)  (default to false)
            var delay = 789;  // long? | The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds. (optional) 
            var width = 789;  // long? | The width, in pixels, of the browser viewport to use. (optional)  (default to 1920)
            var height = 789;  // long? | The height, in pixels, of the browser viewport to use. Ignored if you set full to true. (optional)  (default to 1080)
            var quality = 789;  // long? | The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression. (optional)  (default to 90)
            var scale = 1.2;  // decimal? | The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced. (optional)  (default to 1.0)
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
            var timezone = timezone_example;  // string | The IANA time zone identifier used for this capture. (optional)  (default to Europe/Berlin)
            var device = device_example;  // string | The device used in the emulation. (optional) 
            var latitude = 1.2;  // decimal? | The latitude used in the emulation of the geo-location. (optional)  (default to 0.0)
            var longitude = 1.2;  // decimal? | The longitude used in the emulation of the geo-location. (optional)  (default to 0.0)
            var accuracy = 1.2;  // decimal? | The accuracy in meters used in the emulation of the geo-location. (optional)  (default to 2.0)
            var proxy = proxy_example;  // string | Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280 (optional) 
            var adblock = true;  // bool? | Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads. (optional)  (default to false)
            var hideCookieBanners = true;  // bool? | Prevent cookie banners and pop-ups from being displayed. The best possible result is tried. (optional)  (default to false)

            try
            {
                byte[] result = apiInstance.CaptureScreenshotUnauthenticated(token, url, fileType, ttl, invalidate, full, lazyloadScroll, delay, width, height, quality, scale, x, y, redirect, language, randomUserAgent, userAgent, headers, cookies, css, js, wait, element, timezone, device, latitude, longitude, accuracy, proxy, adblock, hideCookieBanners);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling ScreenshotApi.CaptureScreenshotUnauthenticated: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**| A valid token is needed to make paid API calls. Tokens can be managed from your account. | 
 **url** | **string**| The URL of the website you want to capture. Please include the protocol (http:// or https://). | 
 **fileType** | **string**| The image file format of the captured screenshot. Either png, jpeg, webp or PDF with 72 dpi. | [optional] [default to png]
 **ttl** | **long?**| Number of seconds the capture file is cached by our CDN. An API request that is loaded through the cache does not count as a paid request. You can set a number of seconds from 0 seconds up to 2592000 seconds. This is a maximum of 30 days. | [optional] 
 **invalidate** | **bool?**| Force the API to invalidate the cache and capture a new screenshot. This call costs you additional money, because a call of a cache hit is not charged. | [optional] 
 **full** | **bool?**| Set this parameter to true if you want to screenshot the whole web page in full size. | [optional] 
 **lazyloadScroll** | **bool?**| Set this parameter to true to scroll down through the entire page before taking a screenshot. This is useful for triggering animations or lazy load elements in full screen. | [optional] [default to false]
 **delay** | **long?**| The delay in milliseconds to wait after the page loads before taking the screenshot. This is in milliseconds. One second is 1000 milliseconds. From 0 milliseconds to a maximum of 10,000 milliseconds. | [optional] 
 **width** | **long?**| The width, in pixels, of the browser viewport to use. | [optional] [default to 1920]
 **height** | **long?**| The height, in pixels, of the browser viewport to use. Ignored if you set full to true. | [optional] [default to 1080]
 **quality** | **long?**| The quality of the image between 0 and 100. This works only for the jpeg format, for PNG images the parameter is applied only during compression. | [optional] [default to 90]
 **scale** | **decimal?**| The scale factor of the device to use when taking the screenshot. For example, a scale factor of 2 produces a high-resolution screenshot suitable for viewing on Retina devices. The larger the scale factor, the larger the screenshot produced. | [optional] [default to 1.0]
 **x** | **long?**| The starting point of a section screenshot on the X axis. | [optional] [default to 0]
 **y** | **long?**| The starting point of a section screenshot on the Y axis. | [optional] [default to 0]
 **redirect** | **bool?**| If you set Redirect, the response will be a 302 redirect to the screenshot file in our CDN. | [optional] [default to false]
 **language** | **string**| Sets the Accept-Language header on requests to the target URL so that you can take screenshots from a website with a specific language. | [optional] 
 **randomUserAgent** | **bool?**| Sets a random user agent header to emulate a different devices when taking screenshots. | [optional] [default to false]
 **userAgent** | **string**| Sets the user agent header to emulate a specific device when taking screenshots. | [optional] 
 **headers** | **string**| A semicolon-separated list of header parameters to be used when capturing the screenshot. Each header should be passed as a key-value pair and multiple pairs should be separated by a semicolon. | [optional] 
 **cookies** | **string**| A semicolon-separated list of cookies to be used when capturing the screenshot. Each cookies should be passed as a key-value pair and multiple pairs should be separated by a semicolon. | [optional] 
 **css** | **string**| Inject your custom CSS. | [optional] 
 **js** | **string**| Inject your custom Javascript. | [optional] 
 **wait** | **string**| Wait until the specified CSS selector matches an element present in the page before taking a screenshot. The process is canceled after 60 seconds. | [optional] 
 **element** | **string**| Takes a screenshot of the first element matched by the specified CSS selector. This is ignored if full is true. (This option cannot be used with the PDF export format.) | [optional] 
 **timezone** | **string**| The IANA time zone identifier used for this capture. | [optional] [default to Europe/Berlin]
 **device** | **string**| The device used in the emulation. | [optional] 
 **latitude** | **decimal?**| The latitude used in the emulation of the geo-location. | [optional] [default to 0.0]
 **longitude** | **decimal?**| The longitude used in the emulation of the geo-location. | [optional] [default to 0.0]
 **accuracy** | **decimal?**| The accuracy in meters used in the emulation of the geo-location. | [optional] [default to 2.0]
 **proxy** | **string**| Use an address of a proxy server through which the screenshot should be taken. The proxy address should be formatted as http://username:password@proxyserver.com:31280 | [optional] 
 **adblock** | **bool?**| Prevent ads from being displayed. Block requests from popular ad networks and hide frequent ads. | [optional] [default to false]
 **hideCookieBanners** | **bool?**| Prevent cookie banners and pop-ups from being displayed. The best possible result is tried. | [optional] [default to false]

### Return type

**byte[]**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/pdf, image/jpeg, image/png, image/webp

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)
