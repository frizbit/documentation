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
## What are web push notifications?
*Web push notification* or in other words *browser push notification* is a brand new communication channel between websites and visitors. Web push notifications have been first initiated by Apple on Safari Browser for Mac OS X users in 2013, but it became much more scalable after Google Chrome launched its support for web push notifications.
 
Web push notifications are very similar to the push notifications sent by mobile apps on smartphones, in the sense that users can receive notifications whenever the websites send notifications. But there is one big difference is that you don’t need to have a mobile application to be able to send notifications to your users. 

## What can we do with web push notifications?
Web push notification is the new marketing channel, which outperforms any traditional marketing channels such as E-mail SMS or Retargeting in terms of Click-through rates(CTR). Web push notification is not a new customer acquisition channel, it is a new channel which helps you to re-engage with your existing visitors in the most effective way. 

In order to be able to send notifications, you have to get the permission from the user. After the user opts-in to get the notifications, websites can send as much push notifications as possible to the user. But it should be taken into the consideration that too many irrelevant notifications would make the user to opt-out. 

The most powerful feature of browser push notifications is that the user doesn’t have to be on your website in order to receive your notification. You can grab attention of your user on whichever page they are browsing!
 
If the browser is not working or their device is not turned on, you can still send the notification and your users will receive it whenever they turn their browsers on.

A push notification consists of a title, a description, an icon and a URL that shows where the user will land upon clicking on the notification. You can also add action buttons such as calling a phone number, sending an e-mail, or directing users to different pages, in addition to directing users on a single URL. 

## Which browsers are supported?
At the moment, Google Chrome(42+), Mozilla Firefox(46+), Safari(7.1+) and Yandex Browser are supported on desktop devices. 

On Android devices, Google Chrome, Mozilla Firefox are the browsers which has support for web push notifications. It is at beta phase on Opera Browser, which will be available for public versions soon.

On iOS devices, web push notifications are not supported at the moment. We expect it to be released in the upcoming versions.

# Getting Started
## Creating your account
## Adding your website
### Fully https websites
### Partly https websites
### Http only websites
## Creating Google Project for Chrome
Google Chrome Browser uses Google’s Cloud Messaging Service for sending push notifications. To be able to send and receive notifications via Google Chrome, we need to obtain a Google Server API Key and Google Project Number. 

If you would like not to create your own Google Server API Key and Google Project Number for your website, <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a> can use its default key. However, in this case you wouldn’t be able to access the extra stats of your project on the Google Services interface.

If you would like to create your own Google Server API Key and Google Project Number, please follow the instructions below.

1\. **Visit the Google Services Wizard**

If you are not logged in to any Google account, please log in to your Google Account first. Visit the <a href="https://developers.google.com/mobile/add?platform=android&cntapi=gcm" target="_blank">Google Services Wizard.</a> 

On the page after logging in, on the left menu you will see that _Android_ is selected by default. Don’t worry about creating an _Android_ application. There are no differences between sending web push notifications between Android or Google Chrome. They are using same service called Google Cloud Messaging which we will activate soon.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-1.png "Creating a Google Application Step 1")

2\. **Type any name to as your _App Name_**

As an example, we type _Frizbit_ in the screenshot above. You can type whatever name you prefer. As a suggestion, you can type _domain name_ and the word _push_ to identify the app clearly.

Alternatively, you can select an existing application from the dropdown, if you have any applications created previously.

3\. **Type any name as your _Android Package Name_**

As we are not sending push notifications to an Android application, we don’t need a package name. However, we must enter a value to continue. Please use a value that suits for your website. As a suggestion, you can type reverse domain naming as we use in the example above.

4\. **Click _Choose and Configure Services_ button to continue**

Wait a few seconds for the project to be created.

5\. **Click _Enable Google Cloud Messaging_ button**

After your project created, select **Cloud Messaging** to enable. Click **Enable Google Cloud Messaging.**

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-2.png "Activating Google Cloud Messaging")

6\. **Save Your Keys**

Google Services Wizard will enable Google Cloud Messaging and return two keys called _Server API Key_ and _Sender ID_(also known as the _Project Number_).

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/google-3.png "Activating Google Cloud Messaging")

Both keys will be asked while you are adding your website to the <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a> in order to start your service.

## Creating Certificate for Safari
The Apple Push Notification Service (APNs) is a service created by Apple, Inc. way back in 2009 to securely send push notifications from third party apps to the Apple devices of their users. In order to ensure that unwanted parties are not sending notifications to your application or website, Apple requires you to create an SSL certificate in order to allow secure connection to their servers. Please follow steps below to create the certificate for web push notifications.

1\. **Create Certificate Signing Request**

Open _Keychain Access_ on your Mac OS X. It may be located in “Applications” > “Utilites” > “Keychain Access”

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-1.png "Keychain Access")

Select “Keychain Access” > “Certificate Assistant” > ”Request a Certificate From a Certificate Authority…” from the top menu.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-2.png "Keychain Access2")

Select the “Save to disk” option and enter your information in the required fields. This creates a certification request file that will be used later.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-3.png "Keychain Access3")

2\. **Create a Website Push ID**

Visit the [Apple Developer Account.](https://developer.apple.com/account)

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-4.png "Apple Developer Account")

Select “Certificates, Identifiers & Profiles” and then “Website Push IDs” from the left menu. Click “+” icon on upper right corner to create a new Website Push ID.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-5.png "Apple Developer Account-2")

Enter a name and a unique identifier for your website push ID as shown in the example above. As recommended by Apple, use a reverse-domain name style string (i.e., com.domainname.appname) for a unique identifier. Click “Register” and “Done” to complete registration.

Please note the identifier as we will ask while you are creating a website by using <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard.</a>

3\. **Create a Website Push ID Certificate**

While you are on “Certificates, Identifiers & Profiles”, select “Certificates” > “All” from the left menu. Click “+” icon on upper right corner to create a new Website Push ID Certificate.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-6.png "Apple Developer Account-3")

Select “Website Push ID Certificate” checkbox under the “Production” section as we need a production certificate and click “Continue”.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-7.png "Apple Developer Account-4")

Select previously created Website Push ID from the dropdown and click “Continue”.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-8.png "Apple Developer Account-5")

In this step, Apple summarizes how to create a Certificate Signing request file. As we have already created a CSR file, click “Continue” to upload it for generating your certificate. 

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-9.png "Apple Developer Account-6")

Upload previously created Certificate Signing request file and generate your certificate.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-10.png "Apple Developer Account-7")

Press “Download” to save your certificate.

4\. **Create a Private Key for Frizbit Dashboard**

Open the .cer file you downloaded in the last step by double clicking on it in Finder.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-11.png "Apple Certificate-1")

After a few seconds the “Keychain Access” program should pop up. Select “Login” > “Keys” then right click on your key(**Private Key**) in the list and select “Export”. 

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/apple-12.png "Apple Certificate-2")

Give the file a unique name and press save. You will have an option to protect the file with a password. Add a password, you need to enter this same password on <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard.</a> Save the .p12 file and its password for later use.

Website Push ID, Website Push ID Certificate Private Key and its protection password will be asked while you are creating your website by using <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard.</a>

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

So you have decided to give [Frizbit](https://frizbit.com "push notification for your web applications" target="_blank") a try, but you are not sure where to begin. Have no fear, this step-by-step guide will help you how to get started and send push notifications to reach your users.

## What is Frizbit?
Frizbit is a simple and reliable push notification platform built for websites. 

## Starting with Frizbit
Make sure you have [signed up](https://frizbit.com "push notification for your web applications" target="_blank") for an account before continuing, since you will need a key to authenticate to the frizbit services.

## Basic Installation
The following installation steps will get Frizbit working on your website. 

1. Go to the Frizbit dashboard, and open Website Settings->Frizbit javascript. Copy the script shown there as below, which will include your API Key.

    <script src='//cdn.frizbit.com/frizbitjs/[YOUR FRIZBIT APP KEY].js'></script>
  
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