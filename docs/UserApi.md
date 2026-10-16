# UserApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1UserHistoryDelete**](UserApi.md#v1UserHistoryDelete) | **DELETE** /v1/user/history | Clear All History
[**v1UserHistoryGet**](UserApi.md#v1UserHistoryGet) | **GET** /v1/user/history | Get Watch History
[**v1UserHistoryIdDelete**](UserApi.md#v1UserHistoryIdDelete) | **DELETE** /v1/user/history/{id} | Delete History Item
[**v1UserHistoryPost**](UserApi.md#v1UserHistoryPost) | **POST** /v1/user/history | Record Playback Progress
[**v1UserProfileGet**](UserApi.md#v1UserProfileGet) | **GET** /v1/user/profile | Get User Profile
[**v1UserSettingsGet**](UserApi.md#v1UserSettingsGet) | **GET** /v1/user/settings | Get User Settings
[**v1UserSettingsPatch**](UserApi.md#v1UserSettingsPatch) | **PATCH** /v1/user/settings | Update User Settings
[**v1UserWatchlistAnimeIdDelete**](UserApi.md#v1UserWatchlistAnimeIdDelete) | **DELETE** /v1/user/watchlist/{animeId} | Remove from Watchlist
[**v1UserWatchlistAnimeIdPatch**](UserApi.md#v1UserWatchlistAnimeIdPatch) | **PATCH** /v1/user/watchlist/{animeId} | Update Watchlist Entry
[**v1UserWatchlistGet**](UserApi.md#v1UserWatchlistGet) | **GET** /v1/user/watchlist | Get User Watchlist
[**v1UserWatchlistPost**](UserApi.md#v1UserWatchlistPost) | **POST** /v1/user/watchlist | Add to Watchlist



## v1UserHistoryDelete

Clear All History

Clears the authenticated user's entire watch history.

### Example

```bash
shionstream-cli v1UserHistoryDelete
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserHistoryGet

Get Watch History

Retrieves the authenticated user's watch history sorted by most recent.

### Example

```bash
shionstream-cli v1UserHistoryGet  limit=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **string** |  | [optional] [default to 50]

### Return type

[**V1UserHistoryGet200Response**](V1UserHistoryGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserHistoryIdDelete

Delete History Item

Deletes a single watch history record.

### Example

```bash
shionstream-cli v1UserHistoryIdDelete id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string** |  | [default to null]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserHistoryPost

Record Playback Progress

Records or updates playback progress for an episode (heartbeat). Upserts on [userId, episodeId].

### Example

```bash
shionstream-cli v1UserHistoryPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v1UserHistoryPostRequest** | [**V1UserHistoryPostRequest**](V1UserHistoryPostRequest.md) |  | [optional]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserProfileGet

Get User Profile

Retrieves the authenticated user's profile with activity summary (watchlist count and recent history count).

### Example

```bash
shionstream-cli v1UserProfileGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UserProfileGet200Response**](V1UserProfileGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserSettingsGet

Get User Settings

Retrieves player preferences and notification settings for the authenticated user.

### Example

```bash
shionstream-cli v1UserSettingsGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1UserSettingsGet200Response**](V1UserSettingsGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserSettingsPatch

Update User Settings

Updates player preferences and notification settings.

### Example

```bash
shionstream-cli v1UserSettingsPatch
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v1UserSettingsPatchRequest** | [**V1UserSettingsPatchRequest**](V1UserSettingsPatchRequest.md) |  | [optional]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserWatchlistAnimeIdDelete

Remove from Watchlist

Removes an anime from the user's watchlist.

### Example

```bash
shionstream-cli v1UserWatchlistAnimeIdDelete animeId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **animeId** | **string** |  | [default to null]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserWatchlistAnimeIdPatch

Update Watchlist Entry

Updates status or favorite flag for a specific anime in the user's watchlist.

### Example

```bash
shionstream-cli v1UserWatchlistAnimeIdPatch animeId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **animeId** | **string** |  | [default to null]
 **v1UserWatchlistAnimeIdPatchRequest** | [**V1UserWatchlistAnimeIdPatchRequest**](V1UserWatchlistAnimeIdPatchRequest.md) |  | [optional]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserWatchlistGet

Get User Watchlist

Retrieves the authenticated user's anime watchlist with optional status filter.

### Example

```bash
shionstream-cli v1UserWatchlistGet  status=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status** | **string** |  | [optional] [default to null]

### Return type

[**V1UserWatchlistGet200Response**](V1UserWatchlistGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1UserWatchlistPost

Add to Watchlist

Adds an anime to the user's watchlist. Upserts if the anime already exists in the watchlist.

### Example

```bash
shionstream-cli v1UserWatchlistPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v1UserWatchlistPostRequest** | [**V1UserWatchlistPostRequest**](V1UserWatchlistPostRequest.md) |  | [optional]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

