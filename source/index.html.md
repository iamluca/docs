---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://discordimages.com'>Documentation Powered by Discord Images</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Discord Images  API! You can use our API to access Discord Images API endpoints, which can get information on your account, or uploads in our database.

We have language bindings in Shell and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "token: images_api"
```

```javascript
const request = require('request');
const fs = require('fs');

 const token = 'images_api';

 const options = {
 method: 'POST',
 url: 'https://discordimages.com/api/upload',
 headers: {
     "token": token
   },
 formData: {
      "files[]": fs.createReadStream('./image.jpg');
    }
 };
```

> Make sure to replace `images_api` with your API key.

Discord Images uses API keys to allow access to the API. You can register a new Discord Images API key at our [developer portal](https://discordimages.com/auth).

Discord Images expects for the API key to be included in all API requests to the server in a header that looks like the following:

`token: images_api`

<aside class="notice">
You must replace <code>images_api</code> with your personal API key.
</aside>

# User API Routes

## Get All Uploads

```shell
curl "http://discordimages.com/api/uploads"
  -H "token: images_api"


> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all uploads.

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

