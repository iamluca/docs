---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='https://discordimages.com/auth'>Sign Up for a Developer Key</a>
  - <a href='https://discordimages.com/tos'>Terms of Service</a>
  - <a href='https://discordimages.com/privacy'>Privacy Policy</a>
  - <a href='https://discordimages.com'>Docs Powered by Discord Images</a>

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
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "files": [
        {
            "id": 1222,
            "albumid": null,
            "timestamp": 1543958602,
            "name": "UGRmm.jpg",
            "userid": 89,
            "size": "508 kB",
            "file": "https://discordimages.com/UGRmm.jpg",
            "date": "2018-12-4 16:23:22",
            "album": "",
            "extname": ".jpg",
            "thumb": "https://discordimages.com/thumbs/UGRmm.png"
        },
        {
            "id": 1180,
            "albumid": null,
            "timestamp": 1543636852,
            "name": "3y8qD.txt",
            "userid": 89,
            "size": "14 B",
            "file": "https://discordimages.com/3y8qD.txt",
            "date": "2018-11-30 23:00:52",
            "album": "",
            "extname": ".txt"
        },
        {
            "id": 1142,
            "albumid": null,
            "timestamp": 1543532615,
            "name": "PpuoP.jpeg",
            "userid": 89,
            "size": "8.12 kB",
            "file": "https://discordimages.com/PpuoP.jpeg",
            "date": "2018-11-29 18:03:35",
            "album": "",
            "extname": ".jpeg",
            "thumb": "https://discordimages.com/thumbs/PpuoP.png"
        },
        {
            "id": 1126,
            "albumid": null,
            "timestamp": 1543444480,
            "name": "Q6lM7.png",
            "userid": 89,
            "size": "4.35 kB",
            "file": "https://discordimages.com/Q6lM7.png",
            "date": "2018-11-28 17:34:40",
            "album": "",
            "extname": ".png",
            "thumb": "https://discordimages.com/thumbs/Q6lM7.png"
        },
        {
            "id": 1125,
            "albumid": null,
            "timestamp": 1543444446,
            "name": "zfhFD.png",
            "userid": 89,
            "size": "7.46 kB",
            "file": "https://discordimages.com/zfhFD.png",
            "date": "2018-11-28 17:34:06",
            "album": "",
            "extname": ".png",
            "thumb": "https://discordimages.com/thumbs/zfhFD.png"
        },
        {
            "id": 1080,
            "albumid": null,
            "timestamp": 1543343958,
            "name": "yQyXo.jpeg",
            "userid": 89,
            "size": "8.51 kB",
            "file": "https://discordimages.com/yQyXo.jpeg",
            "date": "2018-11-27 13:39:18",
            "album": "",
            "extname": ".jpeg",
            "thumb": "https://discordimages.com/thumbs/yQyXo.png"
        }
    ]
}
```

This endpoint retrieves all uploads.

# Post an Upload

Posts an upload to Discord Images using your account.

```javascript
 //requiring Main Libraries
 
const request = require('request');
 const fs = require('fs');

 //Token

 const token = 'image_api';

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

 //send request
 request(options, function (err, res, body) {
  if(err) console.log(err);
  console.log(body);
 });
```

> The above command returns JSON structured like this:

```javascript
{
  success: true,
  code: your_files_code.exenstion,
  url: your_uploaded_files_url_to_access
}
```

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

