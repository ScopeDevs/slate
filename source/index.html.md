---
title: PeerPal API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true
---

# Introduction

PeerPal API allows you to obtain data pertaining to prospective parents and parent ambassadors that use PeerPal. If you are interested in partnering with us and using our API, please send us an email at pranav@peerpalschools.com or brennan@peerpalschools.com.

We have language bindings for JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

We will manually generate you an API Key, which you can use to make requests and access all the endpoints below.

PeerPal uses API keys to allow access to the API.

PeerPal expects for the API key to be included in all API requests to the server in the request body that looks like the following:

`{apiKey: "abcedefg"}`

<aside class="warning">
You must replace <code>abcedefg</code> with your personal API key.
</aside>

# Core API Requests

## Get your organization information

```javascript
const fetch = require("node-fetch");
const https = require("https");
const url = "https://www.peerpalapi.com/vendor/";

const headers = {
  "Content-Type": "application/json",
  Accept: "*/*"
};

const inputBody = {
  apiKey: "abcedefg"
};

fetch(url, {
  method: "POST",
  headers: headers,
  body: inputBody
})
  .then(res => {
    return res.json();
  })
  .then(body => {
    if (!body) {
      const er = { error: "nothing works" };
      console.log(er);
    }
    return body.data;
  })
  .catch(err => console.log(error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "5d67579ad227c80017cc789f",
    "isActive": true,
    "admin": {
      "first": "Jon",
      "last": "Doe",
      "email": "Jon@PeerpalSchools.com"
    },
    "apiKey": "abcedefg",
    "name": "PeerPal",
    "createdDate": "2019-10-04T04:13:42.686+00:00"
  }
]
```

This endpoint retrieves all information stored about your organization

### HTTP Request

`POST https://www.peerpalapi.com/vendor/`

### POST body

| body   | Description |
| ------ | ----------- |
| apiKey | abcedefg    |

<aside class="success">
You should be authenticated by now!
</aside>

## Get Parent Ambassadors per School

```javascript
const fetch = require("node-fetch");
const https = require("https");
const url = "https://www.peerpalapi.com/vendor/CurrentParents";

const headers = {
  "Content-Type": "application/json",
  Accept: "*/*"
};

const inputBody = {
  apiKey: "abcedefg",
  organization: "Bryn Mawr School"
};

fetch(url, {
  method: "POST",
  headers: headers,
  body: inputBody
})
  .then(res => {
    return res.json();
  })
  .then(body => {
    if (!body) {
      const er = { error: "nothing works" };
      console.log(er);
    }
    return body.data;
  })
  .catch(err => console.log(error));
```

> The above command returns a JSON of the parent ambassador data like this:

```json
{
  "id": "5d67579ad227c80017cc789f",
  "first": "Jane",
  "last": "Doe",
  "email": "JDoe@brynmawrschool.com",
  "profile": {},
  "imageURL": "http://res.cloudinary.com/peerpal/image/upload/v1579146163/e6ygfbg6rrskdmnjqi9o.jpg"
}
```

<aside class="notice">
This endpoint retrieves parent ambassadors for a specific school.
</aside>

<!-- <aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside> -->

### HTTP Request

`POST https://www.peerpalapi.com/vendor/CurrentParents`

### POST request body

| body         | Description      |
| ------------ | ---------------- |
| apiKey       | abcedefg         |
| organization | Bryn Mawr School |

## Get Prospective Parents per School

```javascript
const fetch = require("node-fetch");
const https = require("https");
const url = "https://www.peerpalapi.com/vendor/ProspectiveParents";

const headers = {
  "Content-Type": "application/json",
  Accept: "*/*"
};

const inputBody = {
  apiKey: "abcedefg",
  organization: "Bryn Mawr School"
};

fetch(url, {
  method: "POST",
  headers: headers,
  body: inputBody
})
  .then(res => {
    return res.json();
  })
  .then(body => {
    if (!body) {
      const er = { error: "nothing works" };
      console.log(er);
    }
    return body.data;
  })
  .catch(err => console.log(error));
```

> The above command returns JSON data of all the school's prospective parents:

```json
{
  "id": "5d67579ad227c80017cc789f",
  "first": "prospective",
  "last": "parent",
  "email": "propsect@gmail.com",
  "q1": 5
}
```

<aside class="notice">
This endpoint retrieves the prospective parents for a specific school
</aside>

### HTTP Request

`POST https://www.peerpalapi.com/vendor/ProspectiveParents`

### Request body

| body         | Description      |
| ------------ | ---------------- |
| apiKey       | abcedefg         |
| organization | Bryn Mawr School |
