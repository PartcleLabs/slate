---
title: Wurk API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Wurk API! You can use our API to access Wurk API endpoints, to post tasks to our wurkers.

<!-- We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation. -->

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: XXXXXX"
```

> Make sure to replace `XXXXXX` with your API key.

Wurk uses API keys to allow access to the API. You will receive your API key via email once you contact us.

Wurk expects for the API key to be included in all API requests to the server in a header that looks like the following:

Authorization: XXXXXX

<aside class="notice">
You must replace <code>XXXXXX</code> with your personal API key.
</aside>

# Tasks

## Create a new wurk unit

```shell
  curl "http://beta.wurkiq.com/api/v1/create_unit" \
  -H "Authorization: XXXXXX" \
  -d title="Man looking through binoculars" \
  -d content_type="video" \
  -d "videos[]=http://1.videohost.mpg" \
  -d "videos[]=http://2.videohost.mpg"

```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "video task created successfully",
  "task_id": "3234sdfsvjpoj23fsd"
}
```



This endpoint creates a new wurk unit.

### HTTP Request

`GET http://beta.wurkiq.com/api/v1/create_unit`

### Data Parameters

Parameter | Type | Default | Description | isRequired
--------- | ------- | -------- | ----------- | ---------------------
title | String | - | the title of the task | if content_type is text
description | String | - | the description of the task | No
content_type | String | text | main content type of the task, possible values include 'image', 'video', 'web' | No
images | Array | [] | array of image urls, eg: ["http://1.img.imgur.jpg", "http://2.img.imgur.jpg"] | if content_type is image
videos | Array | [] | array of image urls, eg: ["http://1.videohost.mpg", "http://2.videohost.mpg"] | if content_type is video
links | Array | [] | array of web urls, eg: ["http://website_1.com", "http://website_2.com"] | if content_type is web

<aside class="success">
Remember — include your API Token in the header
</aside>


