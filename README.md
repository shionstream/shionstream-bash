# ShionStream API Bash client

## Overview

This is a Bash client script for accessing ShionStream API service.

The script uses cURL underneath for making all REST calls.

## Usage

```shell
# Make sure the script has executable rights
$ chmod u+x shionstream-cli

# Print the list of operations available on the service
$ ./shionstream-cli -h

# Print the service description
$ ./shionstream-cli --about

# Print detailed information about specific operation
$ ./shionstream-cli <operationId> -h

# Make GET request
./shionstream-cli --host http://<hostname>:<port> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make GET request using arbitrary curl options (must be passed before <operationId>) to an SSL service using username:password
shionstream-cli -k -sS --tlsv1.2 --host https://<hostname> -u <user>:<password> --accept xml <operationId> <queryParam1>=<value1> <header_key1>:<header_value2>

# Make POST request
$ echo '<body_content>' | shionstream-cli --host <hostname> --content-type json <operationId> -

# Make POST request with simple JSON content, e.g.:
# {
#   "key1": "value1",
#   "key2": "value2",
#   "key3": 23
# }
$ echo '<body_content>' | shionstream-cli --host <hostname> --content-type json <operationId> key1==value1 key2=value2 key3:=23 -

# Make POST request with form data
$ shionstream-cli --host <hostname> <operationId> key1:=value1 key2:=value2 key3:=23

# Preview the cURL command without actually executing it
$ shionstream-cli --host http://<hostname>:<port> --dry-run <operationid>

```

## Docker image

You can easily create a Docker image containing a preconfigured environment
for using the REST Bash client including working autocompletion and short
welcome message with basic instructions, using the generated Dockerfile:

```shell
docker build -t my-rest-client .
docker run -it my-rest-client
```

By default you will be logged into a Zsh environment which has much more
advanced auto completion, but you can switch to Bash, where basic autocompletion
is also available.

## Shell completion

### Bash

The generated bash-completion script can be either directly loaded to the current Bash session using:

```shell
source shionstream-cli.bash-completion
```

Alternatively, the script can be copied to the `/etc/bash-completion.d` (or on OSX with Homebrew to `/usr/local/etc/bash-completion.d`):

```shell
sudo cp shionstream-cli.bash-completion /etc/bash-completion.d/shionstream-cli
```

#### OS X

On OSX you might need to install bash-completion using Homebrew:

```shell
brew install bash-completion
```

and add the following to the `~/.bashrc`:

```shell
if [ -f $(brew --prefix)/etc/bash_completion ]; then
  . $(brew --prefix)/etc/bash_completion
fi
```

### Zsh

In Zsh, the generated `_shionstream-cli` Zsh completion file must be copied to one of the folders under `$FPATH` variable.

## Documentation for API Endpoints

All URIs are relative to **

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AnimeApi* | [**v1AnimeGet**](docs/AnimeApi.md#v1animeget) | **GET** /v1/anime | List Anime Catalog
*AnimeApi* | [**v1AnimeSlugGet**](docs/AnimeApi.md#v1animeslugget) | **GET** /v1/anime/{slug} | Get Anime Details by Slug
*CommentsApi* | [**v1CommentsGet**](docs/CommentsApi.md#v1commentsget) | **GET** /v1/comments | Get Episode Comments
*CommentsApi* | [**v1CommentsIdLikePost**](docs/CommentsApi.md#v1commentsidlikepost) | **POST** /v1/comments/{id}/like | Like or Dislike Comment
*CommentsApi* | [**v1CommentsIdReportPost**](docs/CommentsApi.md#v1commentsidreportpost) | **POST** /v1/comments/{id}/report | Report Comment
*CommentsApi* | [**v1CommentsPost**](docs/CommentsApi.md#v1commentspost) | **POST** /v1/comments | Create Comment
*DashboardApi* | [**v1DashboardAnimeGet**](docs/DashboardApi.md#v1dashboardanimeget) | **GET** /v1/dashboard/anime | Get Administrative Anime List
*DashboardApi* | [**v1DashboardCategoriesGet**](docs/DashboardApi.md#v1dashboardcategoriesget) | **GET** /v1/dashboard/categories | Get Category &amp; Genre Distributions
*DashboardApi* | [**v1DashboardEpisodesGet**](docs/DashboardApi.md#v1dashboardepisodesget) | **GET** /v1/dashboard/episodes | Get Administrative Episodes List
*DashboardApi* | [**v1DashboardModerationGet**](docs/DashboardApi.md#v1dashboardmoderationget) | **GET** /v1/dashboard/moderation | Get Comment Moderation Reports
*DashboardApi* | [**v1DashboardModerationIdPatch**](docs/DashboardApi.md#v1dashboardmoderationidpatch) | **PATCH** /v1/dashboard/moderation/{id} | Resolve or Dismiss Moderation Report
*DashboardApi* | [**v1DashboardOverviewGet**](docs/DashboardApi.md#v1dashboardoverviewget) | **GET** /v1/dashboard/overview | Get Dashboard Overview
*DashboardApi* | [**v1DashboardRolesGet**](docs/DashboardApi.md#v1dashboardrolesget) | **GET** /v1/dashboard/roles | Get System Roles &amp; Permissions
*DashboardApi* | [**v1DashboardSeasonsGet**](docs/DashboardApi.md#v1dashboardseasonsget) | **GET** /v1/dashboard/seasons | Get Seasonal Broadcast Distributions
*DashboardApi* | [**v1DashboardStatsGet**](docs/DashboardApi.md#v1dashboardstatsget) | **GET** /v1/dashboard/stats | Get Platform Stats
*DashboardApi* | [**v1DashboardUsersGet**](docs/DashboardApi.md#v1dashboardusersget) | **GET** /v1/dashboard/users | Get Users Directory (Admin Only)
*EpisodesApi* | [**v1AnimeSlugEpisodesGet**](docs/EpisodesApi.md#v1animeslugepisodesget) | **GET** /v1/anime/{slug}/episodes | List Episodes by Anime Slug
*EpisodesApi* | [**v1EpisodesIdStreamGet**](docs/EpisodesApi.md#v1episodesidstreamget) | **GET** /v1/episodes/{id}/stream | Get Episode Stream Sources
*SampleApi* | [**v1ProtectedSampleGet**](docs/SampleApi.md#v1protectedsampleget) | **GET** /v1/protected/sample | Protected Sample Endpoint
*SystemApi* | [**healthGet**](docs/SystemApi.md#healthget) | **GET** /health | Health Check
*UploadApi* | [**v1UploadHlsPost**](docs/UploadApi.md#v1uploadhlspost) | **POST** /v1/upload/hls | Upload HLS Package to Cloudflare R2
*UploadApi* | [**v1UploadImagePost**](docs/UploadApi.md#v1uploadimagepost) | **POST** /v1/upload/image | Upload Image to Cloudflare R2
*UserApi* | [**v1UserHistoryDelete**](docs/UserApi.md#v1userhistorydelete) | **DELETE** /v1/user/history | Clear All History
*UserApi* | [**v1UserHistoryGet**](docs/UserApi.md#v1userhistoryget) | **GET** /v1/user/history | Get Watch History
*UserApi* | [**v1UserHistoryIdDelete**](docs/UserApi.md#v1userhistoryiddelete) | **DELETE** /v1/user/history/{id} | Delete History Item
*UserApi* | [**v1UserHistoryPost**](docs/UserApi.md#v1userhistorypost) | **POST** /v1/user/history | Record Playback Progress
*UserApi* | [**v1UserProfileGet**](docs/UserApi.md#v1userprofileget) | **GET** /v1/user/profile | Get User Profile
*UserApi* | [**v1UserSettingsGet**](docs/UserApi.md#v1usersettingsget) | **GET** /v1/user/settings | Get User Settings
*UserApi* | [**v1UserSettingsPatch**](docs/UserApi.md#v1usersettingspatch) | **PATCH** /v1/user/settings | Update User Settings
*UserApi* | [**v1UserWatchlistAnimeIdDelete**](docs/UserApi.md#v1userwatchlistanimeiddelete) | **DELETE** /v1/user/watchlist/{animeId} | Remove from Watchlist
*UserApi* | [**v1UserWatchlistAnimeIdPatch**](docs/UserApi.md#v1userwatchlistanimeidpatch) | **PATCH** /v1/user/watchlist/{animeId} | Update Watchlist Entry
*UserApi* | [**v1UserWatchlistGet**](docs/UserApi.md#v1userwatchlistget) | **GET** /v1/user/watchlist | Get User Watchlist
*UserApi* | [**v1UserWatchlistPost**](docs/UserApi.md#v1userwatchlistpost) | **POST** /v1/user/watchlist | Add to Watchlist


## Documentation For Models

 - [HealthGet200Response](docs/HealthGet200Response.md)
 - [HealthGet500Response](docs/HealthGet500Response.md)
 - [V1AnimeGet200Response](docs/V1AnimeGet200Response.md)
 - [V1AnimeGet200ResponseDataInner](docs/V1AnimeGet200ResponseDataInner.md)
 - [V1AnimeGet200ResponsePagination](docs/V1AnimeGet200ResponsePagination.md)
 - [V1AnimeSlugEpisodesGet200Response](docs/V1AnimeSlugEpisodesGet200Response.md)
 - [V1AnimeSlugEpisodesGet200ResponseAnime](docs/V1AnimeSlugEpisodesGet200ResponseAnime.md)
 - [V1AnimeSlugEpisodesGet200ResponseDataInner](docs/V1AnimeSlugEpisodesGet200ResponseDataInner.md)
 - [V1AnimeSlugGet200Response](docs/V1AnimeSlugGet200Response.md)
 - [V1AnimeSlugGet200ResponseData](docs/V1AnimeSlugGet200ResponseData.md)
 - [V1AnimeSlugGet200ResponseDataGenresInner](docs/V1AnimeSlugGet200ResponseDataGenresInner.md)
 - [V1AnimeSlugGet200ResponseDataSchedule](docs/V1AnimeSlugGet200ResponseDataSchedule.md)
 - [V1AnimeSlugGet200ResponseDataTrendingStats](docs/V1AnimeSlugGet200ResponseDataTrendingStats.md)
 - [V1CommentsGet200Response](docs/V1CommentsGet200Response.md)
 - [V1CommentsGet200ResponseDataInner](docs/V1CommentsGet200ResponseDataInner.md)
 - [V1CommentsIdLikePost200Response](docs/V1CommentsIdLikePost200Response.md)
 - [V1CommentsIdLikePostRequest](docs/V1CommentsIdLikePostRequest.md)
 - [V1CommentsIdReportPostRequest](docs/V1CommentsIdReportPostRequest.md)
 - [V1CommentsPost201Response](docs/V1CommentsPost201Response.md)
 - [V1CommentsPostRequest](docs/V1CommentsPostRequest.md)
 - [V1DashboardAnimeGet200Response](docs/V1DashboardAnimeGet200Response.md)
 - [V1DashboardCategoriesGet200Response](docs/V1DashboardCategoriesGet200Response.md)
 - [V1DashboardCategoriesGet200ResponseCategoriesInner](docs/V1DashboardCategoriesGet200ResponseCategoriesInner.md)
 - [V1DashboardCategoriesGet200ResponseGenresInner](docs/V1DashboardCategoriesGet200ResponseGenresInner.md)
 - [V1DashboardEpisodesGet200Response](docs/V1DashboardEpisodesGet200Response.md)
 - [V1DashboardModerationGet200Response](docs/V1DashboardModerationGet200Response.md)
 - [V1DashboardModerationGet200ResponseReportsInner](docs/V1DashboardModerationGet200ResponseReportsInner.md)
 - [V1DashboardModerationGet200ResponseReportsInnerAuthor](docs/V1DashboardModerationGet200ResponseReportsInnerAuthor.md)
 - [V1DashboardModerationGet200ResponseReportsInnerReporter](docs/V1DashboardModerationGet200ResponseReportsInnerReporter.md)
 - [V1DashboardModerationIdPatchRequest](docs/V1DashboardModerationIdPatchRequest.md)
 - [V1DashboardOverviewGet200Response](docs/V1DashboardOverviewGet200Response.md)
 - [V1DashboardOverviewGet200ResponseNotificationsInner](docs/V1DashboardOverviewGet200ResponseNotificationsInner.md)
 - [V1DashboardOverviewGet200ResponseRecentActivitiesInner](docs/V1DashboardOverviewGet200ResponseRecentActivitiesInner.md)
 - [V1DashboardOverviewGet200ResponseTrafficDataInner](docs/V1DashboardOverviewGet200ResponseTrafficDataInner.md)
 - [V1DashboardRolesGet200Response](docs/V1DashboardRolesGet200Response.md)
 - [V1DashboardRolesGet200ResponseRolesInner](docs/V1DashboardRolesGet200ResponseRolesInner.md)
 - [V1DashboardSeasonsGet200Response](docs/V1DashboardSeasonsGet200Response.md)
 - [V1DashboardSeasonsGet200ResponseSeasonsInner](docs/V1DashboardSeasonsGet200ResponseSeasonsInner.md)
 - [V1DashboardStatsGet200Response](docs/V1DashboardStatsGet200Response.md)
 - [V1DashboardStatsGet200ResponseStats](docs/V1DashboardStatsGet200ResponseStats.md)
 - [V1DashboardUsersGet200Response](docs/V1DashboardUsersGet200Response.md)
 - [V1DashboardUsersGet200ResponseUsersInner](docs/V1DashboardUsersGet200ResponseUsersInner.md)
 - [V1EpisodesIdStreamGet200Response](docs/V1EpisodesIdStreamGet200Response.md)
 - [V1EpisodesIdStreamGet200ResponseAudioInner](docs/V1EpisodesIdStreamGet200ResponseAudioInner.md)
 - [V1EpisodesIdStreamGet200ResponseEpisode](docs/V1EpisodesIdStreamGet200ResponseEpisode.md)
 - [V1EpisodesIdStreamGet200ResponseSourcesInner](docs/V1EpisodesIdStreamGet200ResponseSourcesInner.md)
 - [V1EpisodesIdStreamGet200ResponseSubtitlesInner](docs/V1EpisodesIdStreamGet200ResponseSubtitlesInner.md)
 - [V1ProtectedSampleGet200Response](docs/V1ProtectedSampleGet200Response.md)
 - [V1ProtectedSampleGet200ResponseUser](docs/V1ProtectedSampleGet200ResponseUser.md)
 - [V1ProtectedSampleGet401Response](docs/V1ProtectedSampleGet401Response.md)
 - [V1UploadHlsPost200Response](docs/V1UploadHlsPost200Response.md)
 - [V1UploadHlsPost200ResponseData](docs/V1UploadHlsPost200ResponseData.md)
 - [V1UploadImagePost200Response](docs/V1UploadImagePost200Response.md)
 - [V1UploadImagePost200ResponseData](docs/V1UploadImagePost200ResponseData.md)
 - [V1UserHistoryGet200Response](docs/V1UserHistoryGet200Response.md)
 - [V1UserHistoryGet200ResponseDataInner](docs/V1UserHistoryGet200ResponseDataInner.md)
 - [V1UserHistoryPostRequest](docs/V1UserHistoryPostRequest.md)
 - [V1UserProfileGet200Response](docs/V1UserProfileGet200Response.md)
 - [V1UserProfileGet200ResponseData](docs/V1UserProfileGet200ResponseData.md)
 - [V1UserProfileGet200ResponseDataActivity](docs/V1UserProfileGet200ResponseDataActivity.md)
 - [V1UserSettingsGet200Response](docs/V1UserSettingsGet200Response.md)
 - [V1UserSettingsGet200ResponseData](docs/V1UserSettingsGet200ResponseData.md)
 - [V1UserSettingsGet200ResponseDataNotifications](docs/V1UserSettingsGet200ResponseDataNotifications.md)
 - [V1UserSettingsGet200ResponseDataPlayer](docs/V1UserSettingsGet200ResponseDataPlayer.md)
 - [V1UserSettingsPatch200Response](docs/V1UserSettingsPatch200Response.md)
 - [V1UserSettingsPatchRequest](docs/V1UserSettingsPatchRequest.md)
 - [V1UserSettingsPatchRequestNotifications](docs/V1UserSettingsPatchRequestNotifications.md)
 - [V1UserSettingsPatchRequestPlayer](docs/V1UserSettingsPatchRequestPlayer.md)
 - [V1UserSettingsPatchRequestProfile](docs/V1UserSettingsPatchRequestProfile.md)
 - [V1UserWatchlistAnimeIdPatchRequest](docs/V1UserWatchlistAnimeIdPatchRequest.md)
 - [V1UserWatchlistGet200Response](docs/V1UserWatchlistGet200Response.md)
 - [V1UserWatchlistGet200ResponseDataInner](docs/V1UserWatchlistGet200ResponseDataInner.md)
 - [V1UserWatchlistPostRequest](docs/V1UserWatchlistPostRequest.md)


## Documentation For Authorization


## Bearer


- **Type**: HTTP Bearer Token authentication (JWT / API-Key)

