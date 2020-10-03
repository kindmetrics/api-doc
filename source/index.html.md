---
title: Kindmetrics API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://app.kindmetrics.io/sign_up'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Kindmetrics API. Here you can handle your domains and the statistics for your domains. You can show your most important data directly in your app for optimizing your flow.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://app.kindmetrics.io/api/domains"
  -H "Authorization: Bearer APIKEY"
```

> Make sure to replace `APIKEY` with your API key.

Kindmetrics uses API keys to allow access to the API. You can get your API key at your [api tokens page](http://app.kindmetrics.io/me/tokens).

Kindmetrics expect the token to be an param (`?token=APITOKEN`) or in the headers like below:

`Authorization: APITOKEN`

<aside class="notice">
You must replace <code>APITOKEN</code> with your personal API key.
</aside>

# Domains

## Get Your Domains

```shell
curl "https://app.kindmetrics.io/api/domains"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "address": "kindmetrics.io"
  }
]
```

This endpoint retrieves all your domains.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains`

## Retrieve one Domain

```shell
curl "https://app.kindmetrics.io/api/domains/1"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
{
  "address": "kindmetrics.io",
  "visitors": 3041,
  "pageviews": 5643,
  "bounce": 64,
  "track_snippet": "<script src=\"https://kindmetrics.io/js/kind.js\" defer=\"true\" data-domain=\"kindmetrics.io\"></script>"
}
```

This endpoint retrieves one of your domains.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint


## Create an Domain

```shell
curl "https://app.kindmetrics.io/api/domains"
  -X POST
  -d {"domain": {"address": "kindmetrics.io", "time_zone": "Europe/Stockholm"}}
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
{
  "address": "kindmetrics.io",
  "visitors": 0,
  "pageviews": 0,
  "bounce": 0,
  "track_snippet": "<script src=\"https://kindmetrics.io/js/kind.js\" defer=\"true\" data-domain=\"kindmetrics.io\"></script>"
}
```

This endpoint retrieves one of your domains.

### HTTP Request

`POST https://app.kindmetrics.io/api/domains`

### Query Parameters

Parameter   | Default   | Description
------------|-----------|------------
address     | none      | domain address without `www.` prefix, as example `kindmetrics.io`
time_zone   | none      | time zone in format `Continent/City`


# Domain stats

You can get all data you can see on the dashboard in different requests. They will be aggregated results and show the data based on the period you have chosen.

## Retrieve Pages

```shell
curl "https://app.kindmetrics.io/api/domains/1/pages"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "address": "/open-source-analytics",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves pages stats for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/pages`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint


## Retrieve Entry Pages

```shell
curl "https://app.kindmetrics.io/api/domains/1/entry_pages"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "address": "/open-source-analytics",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves entry pages stats for your domain. Entry page is the first page the visitor visit when visiting your website.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/entry_pages`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint


## Retrieve Sources

```shell
curl "https://app.kindmetrics.io/api/domains/1/sources"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "source": "indiehackers.com",
    "medium": "social",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves sources stats for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/sources`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint


## Retrieve Referrers

```shell
curl "https://app.kindmetrics.io/api/domains/1/referrers"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "url": "https://www.indiehackers.com/",
    "domain": "indiehackers.com",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves referrer stats for your domain, usually used for seeing links for a specific source or medium on kindmetrics.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/referrers`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint

## Retrieve Countries

```shell
curl "https://app.kindmetrics.io/api/domains/1/countries"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "Sweden",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves countries stats for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/countries`

### Query Parameters

Parameter   | Default        | Description
------------|----------------|------------
to          | Today          | Date you want to show the stats to, can be today or earlier, not in the future, like: `2020-06-01`
from        | 7 days ago     | Date where you want to show stats from, like: `2020-04-01`
source_name | None           | Source you want to filter on. Like `Google` or `indiehackers.com`
medium_name | None           | Group of sources you want to filter on, like `Social` or `Search`
site_path   | None           | url path of your site you want to see aggregated stats for, like `/blog`
goal_id     | None           | aggregate stats for goals - get goal id from the goal api endpoint

## Retrieve Current Visitors

```shell
curl "https://app.kindmetrics.io/api/domains/1/current"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
{
  "current": 3
}
```

This endpoint retrieves current visitors for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/current`

## Retrieve Goals

```shell
curl "https://app.kindmetrics.io/api/domains/1/goals"
  -H "Authorization: Bearer APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "/sign_up",
    "kind": "Path",
    "conversions": 3
  }
]
```

This endpoint retrieves current visitors for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/goals`
