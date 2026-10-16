# CommentsApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1CommentsGet**](CommentsApi.md#v1CommentsGet) | **GET** /v1/comments | Get Episode Comments
[**v1CommentsIdLikePost**](CommentsApi.md#v1CommentsIdLikePost) | **POST** /v1/comments/{id}/like | Like or Dislike Comment
[**v1CommentsIdReportPost**](CommentsApi.md#v1CommentsIdReportPost) | **POST** /v1/comments/{id}/report | Report Comment
[**v1CommentsPost**](CommentsApi.md#v1CommentsPost) | **POST** /v1/comments | Create Comment



## v1CommentsGet

Get Episode Comments

Retrieves threaded comments for an episode, ordered by newest first, with like/dislike counts.

### Example

```bash
shionstream-cli v1CommentsGet  episodeId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **episodeId** | **string** |  | [default to null]

### Return type

[**V1CommentsGet200Response**](V1CommentsGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1CommentsIdLikePost

Like or Dislike Comment

Adds or toggles a like/dislike reaction on a comment. Upserts on [commentId, userId].

### Example

```bash
shionstream-cli v1CommentsIdLikePost id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string** |  | [default to null]
 **v1CommentsIdLikePostRequest** | [**V1CommentsIdLikePostRequest**](V1CommentsIdLikePostRequest.md) |  | [optional]

### Return type

[**V1CommentsIdLikePost200Response**](V1CommentsIdLikePost200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1CommentsIdReportPost

Report Comment

Submits a comment to the moderation queue with a reason.

### Example

```bash
shionstream-cli v1CommentsIdReportPost id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string** |  | [default to null]
 **v1CommentsIdReportPostRequest** | [**V1CommentsIdReportPostRequest**](V1CommentsIdReportPostRequest.md) |  | [optional]

### Return type

[**V1CommentsIdLikePost200Response**](V1CommentsIdLikePost200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1CommentsPost

Create Comment

Creates a new comment or reply on an episode. Supports both authenticated users and guests (guest requires name and email).

### Example

```bash
shionstream-cli v1CommentsPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v1CommentsPostRequest** | [**V1CommentsPostRequest**](V1CommentsPostRequest.md) |  | [optional]

### Return type

[**V1CommentsPost201Response**](V1CommentsPost201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

