# EpisodesApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1AnimeSlugEpisodesGet**](EpisodesApi.md#v1AnimeSlugEpisodesGet) | **GET** /v1/anime/{slug}/episodes | List Episodes by Anime Slug
[**v1EpisodesIdStreamGet**](EpisodesApi.md#v1EpisodesIdStreamGet) | **GET** /v1/episodes/{id}/stream | Get Episode Stream Sources



## v1AnimeSlugEpisodesGet

List Episodes by Anime Slug

Retrieve an ordered list of published episodes for a specific anime.

### Example

```bash
shionstream-cli v1AnimeSlugEpisodesGet slug=value  page=value  limit=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **slug** | **string** |  | [default to null]
 **page** | **string** |  | [optional] [default to 1]
 **limit** | **string** |  | [optional] [default to 50]
 **sort** | **string** |  | [optional] [default to asc]

### Return type

[**V1AnimeSlugEpisodesGet200Response**](V1AnimeSlugEpisodesGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1EpisodesIdStreamGet

Get Episode Stream Sources

Retrieve video playback manifests, multi-resolution URLs, subtitles, and audio tracks for an episode.

### Example

```bash
shionstream-cli v1EpisodesIdStreamGet id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string** |  | [default to null]

### Return type

[**V1EpisodesIdStreamGet200Response**](V1EpisodesIdStreamGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

