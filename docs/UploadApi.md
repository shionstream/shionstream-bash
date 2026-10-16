# UploadApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1UploadHlsPost**](UploadApi.md#v1UploadHlsPost) | **POST** /v1/upload/hls | Upload HLS Package to Cloudflare R2
[**v1UploadImagePost**](UploadApi.md#v1UploadImagePost) | **POST** /v1/upload/image | Upload Image to Cloudflare R2



## v1UploadHlsPost

Upload HLS Package to Cloudflare R2

Ingests multi-resolution HLS package (master playlist, variants, and .ts segment chunks) directly into Cloudflare R2 object storage.

### Example

```bash
shionstream-cli v1UploadHlsPost
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UploadHlsPost200Response**](V1UploadHlsPost200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UploadImagePost

Upload Image to Cloudflare R2

Uploads posters, banners, or avatars directly to Cloudflare R2.

### Example

```bash
shionstream-cli v1UploadImagePost
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UploadImagePost200Response**](V1UploadImagePost200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

