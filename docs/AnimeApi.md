# AnimeApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1AnimeGet**](AnimeApi.md#v1AnimeGet) | **GET** /v1/anime | List Anime Catalog
[**v1AnimeSlugGet**](AnimeApi.md#v1AnimeSlugGet) | **GET** /v1/anime/{slug} | Get Anime Details by Slug



## v1AnimeGet

List Anime Catalog

Retrieve paginated list of anime with filters for type, status, season, year, genre, and search.

### Example

```bash
shionstream-cli v1AnimeGet  page=value  limit=value  search=value  type=value  status=value  genre=value  season=value  year=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **string** |  | [optional] [default to 1]
 **limit** | **string** |  | [optional] [default to 20]
 **search** | **string** |  | [optional] [default to null]
 **type** | **string** |  | [optional] [default to null]
 **status** | **string** |  | [optional] [default to null]
 **genre** | **string** |  | [optional] [default to null]
 **season** | **string** |  | [optional] [default to null]
 **year** | **string** |  | [optional] [default to null]
 **sort** | **string** |  | [optional] [default to latest]

### Return type

[**V1AnimeGet200Response**](V1AnimeGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1AnimeSlugGet

Get Anime Details by Slug

Retrieve comprehensive anime metadata including associated genres, studios, schedule, and trending stats.

### Example

```bash
shionstream-cli v1AnimeSlugGet slug=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **slug** | **string** |  | [default to null]

### Return type

[**V1AnimeSlugGet200Response**](V1AnimeSlugGet200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

