---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
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
  -H "Authorization: APIKEY"
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
# With shell, you can just pass the correct header with each request
curl "https://app.kindmetrics.io/api/domains"
  -H "Authorization: APIKEY"
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

## Retreive one Domain

```shell
# With shell, you can just pass the correct header with each request
curl "https://app.kindmetrics.io/api/domains/1"
  -H "Authorization: APIKEY"
```

> The above command returns JSON structured like this:

```json
{
    "address": "kindmetrics.io",
    "visitors": 3041,
    "pageviews": 5643,
    "bounce": 64,
    "track_snippet": "<script src=\"https://localhost:5000/js/kind.js\" defer=\"true\" data-domain=\"kindmetrics.io\"></script>"
}
```

This endpoint retrieves one of your domains.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1`

## Retreive Pages for Domain

```shell
# With shell, you can just pass the correct header with each request
curl "https://app.kindmetrics.io/api/domains/1/pages"
  -H "Authorization: APIKEY"
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

## Retreive Sources for Domain

```shell
# With shell, you can just pass the correct header with each request
curl "https://app.kindmetrics.io/api/domains/1/pages"
  -H "Authorization: APIKEY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "source": "indiehackers.com",
    "url": "https://www.indiehackers.com/",
    "domain": "indiehackers.com",
    "medium": "social",
    "visitors": 12,
    "percentage": 24
  }
]
```

This endpoint retrieves pages stats for your domain.

### HTTP Request

`GET https://app.kindmetrics.io/api/domains/1/pages`
