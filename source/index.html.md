---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction
## What’s web push notifications?
## What can we do with web push notifications?
## Which browsers are supported?
# Getting Started
## Creating your account
## Adding your website
### Fully https websites
### Partly https websites
### Http only websites
## Creating Google project for Chrome
Google Chrome Browser uses Google’s Cloud Messaging Service for sending push notifications. To be able to send and receive notifications to Chrome, we’ll obtain a Google Server API Key and Google Project Number. Frizbit Dashboard provides default values for your website. But if you would like to provide your own keys, please follow the instructions to obtain them.

1. **Create a Google Application**

Visit the [Google Services Wizard.](https://developers.google.com/mobile/add?platform=android&cntapi=gcm) Don’t worry about creating an “Android” application. There are no differences between sending web push notifications between Android or Google Chrome. They are using same service called Google Cloud Messaging which we will activate soon.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-1.png "Creating a Google Application Step 1")

You can create a new application or select an existing application from the dropdown. In the example above, we create a new application called _Frizbit_. As we are not sending push notifications to an Android application, we don’t need a package name. However, we must enter a value to continue. Please use a value that suits for your website. You can use reverse domain naming as we use in the example above.

Click **Choose and configure services** to continue. Wait a minute for the project to be created.

2. **Activate Google Cloud Messaging**

After your project created, select **Cloud Messaging** to enable. Click **Enable Google Cloud Messaging.**

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-2.png "Activating Google Cloud Messaging")

3. **Save Your Keys**

Google Services Wizard will enable Google Cloud Messaging and return two keys called _Server API Key_ and _Sender ID_(also known as the _Project Number_).

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-3.png "Activating Google Cloud Messaging")

Both keys will be asked while you are creating your website by using [Frizbit Dashboard.](https://dashboard.frizbit.com) 

## Creating certificate for Safari
The Apple Push Notification Service (APNs) is a service created by Apple Inc. way back in 2009 to securely send push notifications from third party apps to their users' Apple devices. To be able to ensure that unwanted parties are not sending notifications to your application or website, Apple requires you to create an SSL certificate to allow secure connection to their servers. Please follow steps below to create the certificate for web push notifications.

1. **Create Certificate Signing request**
2. **Create a Web Push ID**
3. **Create a Web Push Certificate**

# Installation
## Fully https websites
## Partly https websites
### For your own https subdomain
### For provided frizbit https subdomain
## Http only website
## How to install by using Google Tag Manager
# Javascript API
## Getting Started
## Autoregister
## Prompt After
## Customizing Notify Box
## Checking Browser Support
## Segmentation Overview
## Assigning Segments
## Removing Segments
## Tagging Overview
## Assigning Tags
## Removing Tags
# REST API
## Getting Started
## Sending Your First Push
## Authentication
## Specification
## Basic Push

# Getting Started
## Introduction

So you have decided to give [Frizbit](https://frizbit.com "push notification for your web applications") a try, but you are not sure where to begin. Have no fear, this step-by-step guide will help you how to get started and send push notifications to reach your users.

## What is Frizbit?
Frizbit is a simple and reliable push notification platform built for websites. 

## Starting with Frizbit
Make sure you have [signed up](https://frizbit.com "push notification for your web applications") for an account before continuing, since you will need a key to authenticate to the frizbit services.

## Basic Installation
The following installation steps will get Frizbit working on your website. 

1. Go to the Frizbit dashboard, and open Website Settings->Frizbit javascript. Copy the script shown there as below, which will include your API Key.

    <script src='//cdn.frizbit.com/frizbitjs/[YOUR FRIZBIT APP KEY].js' async></script>
  
2. Using your website's dashboard paste this code just above the closing **</head>** tag.

3. Download installation files and copy to root folder.

4. Initialize the FrizbitJS on your pages.

# API References

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

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

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

Bu