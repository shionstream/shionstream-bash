# DashboardApi

All URIs are relative to **

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1DashboardAnimeGet**](DashboardApi.md#v1DashboardAnimeGet) | **GET** /v1/dashboard/anime | Get Administrative Anime List
[**v1DashboardCategoriesGet**](DashboardApi.md#v1DashboardCategoriesGet) | **GET** /v1/dashboard/categories | Get Category &amp; Genre Distributions
[**v1DashboardEpisodesGet**](DashboardApi.md#v1DashboardEpisodesGet) | **GET** /v1/dashboard/episodes | Get Administrative Episodes List
[**v1DashboardModerationGet**](DashboardApi.md#v1DashboardModerationGet) | **GET** /v1/dashboard/moderation | Get Comment Moderation Reports
[**v1DashboardModerationIdPatch**](DashboardApi.md#v1DashboardModerationIdPatch) | **PATCH** /v1/dashboard/moderation/{id} | Resolve or Dismiss Moderation Report
[**v1DashboardOverviewGet**](DashboardApi.md#v1DashboardOverviewGet) | **GET** /v1/dashboard/overview | Get Dashboard Overview
[**v1DashboardRolesGet**](DashboardApi.md#v1DashboardRolesGet) | **GET** /v1/dashboard/roles | Get System Roles &amp; Permissions
[**v1DashboardSeasonsGet**](DashboardApi.md#v1DashboardSeasonsGet) | **GET** /v1/dashboard/seasons | Get Seasonal Broadcast Distributions
[**v1DashboardStatsGet**](DashboardApi.md#v1DashboardStatsGet) | **GET** /v1/dashboard/stats | Get Platform Stats
[**v1DashboardUsersGet**](DashboardApi.md#v1DashboardUsersGet) | **GET** /v1/dashboard/users | Get Users Directory (Admin Only)



## v1DashboardAnimeGet

Get Administrative Anime List

Returns paginated anime catalog with filters for administration.

### Example

```bash
shionstream-cli v1DashboardAnimeGet  page=value  limit=value  status=value  search=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **string** |  | [optional] [default to 1]
 **limit** | **string** |  | [optional] [default to 20]
 **status** | **string** |  | [optional] [default to null]
 **search** | **string** |  | [optional] [default to null]

### Return type

[**V1DashboardAnimeGet200Response**](V1DashboardAnimeGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardCategoriesGet

Get Category & Genre Distributions

Returns format categories and genres with associated anime counts.

### Example

```bash
shionstream-cli v1DashboardCategoriesGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DashboardCategoriesGet200Response**](V1DashboardCategoriesGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardEpisodesGet

Get Administrative Episodes List

Returns paginated episodes with upload status for administration.

### Example

```bash
shionstream-cli v1DashboardEpisodesGet  page=value  limit=value  animeId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **string** |  | [optional] [default to 1]
 **limit** | **string** |  | [optional] [default to 20]
 **animeId** | **string** |  | [optional] [default to null]

### Return type

[**V1DashboardEpisodesGet200Response**](V1DashboardEpisodesGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardModerationGet

Get Comment Moderation Reports

Returns reported comments queue with status filter.

### Example

```bash
shionstream-cli v1DashboardModerationGet  status=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status** | **string** |  | [optional] [default to pending]

### Return type

[**V1DashboardModerationGet200Response**](V1DashboardModerationGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardModerationIdPatch

Resolve or Dismiss Moderation Report

Updates comment report status and optionally deletes the reported comment.

### Example

```bash
shionstream-cli v1DashboardModerationIdPatch id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string** |  | [default to null]
 **v1DashboardModerationIdPatchRequest** | [**V1DashboardModerationIdPatchRequest**](V1DashboardModerationIdPatchRequest.md) |  | [optional]

### Return type

[**V1UserSettingsPatch200Response**](V1UserSettingsPatch200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardOverviewGet

Get Dashboard Overview

Returns traffic telemetry, recent activity logs, and administrative notifications.

### Example

```bash
shionstream-cli v1DashboardOverviewGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DashboardOverviewGet200Response**](V1DashboardOverviewGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardRolesGet

Get System Roles & Permissions

Returns role definitions and active user member counts.

### Example

```bash
shionstream-cli v1DashboardRolesGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DashboardRolesGet200Response**](V1DashboardRolesGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardSeasonsGet

Get Seasonal Broadcast Distributions

Returns anime release distribution grouped by season and year.

### Example

```bash
shionstream-cli v1DashboardSeasonsGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DashboardSeasonsGet200Response**](V1DashboardSeasonsGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardStatsGet

Get Platform Stats

Returns aggregated platform metrics including anime count, episode count, user count, and storage estimates.

### Example

```bash
shionstream-cli v1DashboardStatsGet
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**V1DashboardStatsGet200Response**](V1DashboardStatsGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## v1DashboardUsersGet

Get Users Directory (Admin Only)

Returns registered users directory with role and status information.

### Example

```bash
shionstream-cli v1DashboardUsersGet  page=value  limit=value  role=value  search=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **string** |  | [optional] [default to 1]
 **limit** | **string** |  | [optional] [default to 20]
 **role** | **string** |  | [optional] [default to null]
 **search** | **string** |  | [optional] [default to null]

### Return type

[**V1DashboardUsersGet200Response**](V1DashboardUsersGet200Response.md)

### Authorization

[Bearer](../README.md#Bearer)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

