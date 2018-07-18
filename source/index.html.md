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
Web push notification is the new marketing channel, which outperforms any traditional marketing channels such as E-mail, SMS or Retargeting in terms of Click-through rates(CTR). Web push notification is not a new customer acquisition channel, it is a new channel which helps you to re-engage with your existing visitors in the most effective way. 

In order to be able to send notifications, you have to get the permission from the user. After the user opts-in to get the notifications, websites can send as much push notifications as possible to the user. But it should be taken into the consideration that too many irrelevant notifications would make the user to opt-out. 

The most powerful feature of browser push notifications is that the user doesn’t have to be on your website in order to receive your notification. You can grab attention of your user on whichever page they are browsing!
 
If the browser is not working or their device is not turned on, you can still send the notification and your users will receive it whenever they turn their browsers on.

A push notification consists of a title, a description, an icon and a URL that shows where the user will land upon clicking on the notification. You can also add action buttons such as calling a phone number, sending an e-mail, or directing users to different pages, in addition to directing users on a single URL. 

## Which browsers are supported?
At the moment, Google Chrome(42+), Mozilla Firefox(46+), Safari(7.1+) and Yandex Browser are supported on desktop devices. It is at beta phase on Opera Browser, which will be available for public versions soon.

On Android devices, Google Chrome, Mozilla Firefox, Opera Mobile are the browsers which has support for web push notifications. 

On iOS devices, web push notifications are not supported at the moment. We expect it to be released in the upcoming versions.

# Getting Started
## Creating your account
So you have decided to give <a href="https://frizbit.com" target="_blank">Frizbit</a> a try, but you are not sure where to begin. Have no fear, this step-by-step guide will help you how to get started and send push notifications in order to reach your users.

Make sure you have <a href="https://frizbit.com" target="_blank">signed up</a> for an account before continuing, since you will need a key to authenticate to the Frizbit services.

## Adding your website
Adding new website to <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a> doesn’t take more than one minute. Frizbit offers three different installation options to support all kind of websites. To be able to decide which option suits to your website, please refer informations below.

### Fully HTTPS websites
All browsers except Apple Safari require _Fully_ HTTPS enabled website in order to start collecting web push notification subscribers. This is the default&native option for web push notification feature. If all of your pages are served under HTTPS, we recommend you to select this option.

### Partly HTTPS websites
Some of the websites serve their homepages under HTTP even though they have some pages served under HTTPS. In this case, if you can change your configurations to serve your all web pages under HTTPS, we recommend you to do that before adding your website to <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a>. If you can not change your configuration easily, we offer Partly HTTPS support in order to enable web push notification support.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/partly-https-1.png "Adding partly HTTPS website")

By selecting _Only some pages are served HTTPS_, you can enter a directory name that will host our installation files under HTTPS. 

The difference between _Fully_ HTTPS and _Partly_ HTTPS support is that, we will prompt a popup serving under HTTPS in order to ask native permission as shown below.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/partly-https-2.png "Permission popup for Partly HTTPS website")
 
### HTTP only websites
If you don’t have SSL certificate and all of your web pages are served under HTTP, this is the valid option for you. 

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/http-1.png "Adding HTTP only website")

By selecting _We don’t have HTTPS support_, you can enter a subdomain name that will host our installation files under HTTPS. 

The difference between _Partly_ HTTPS and _HTTP only_ support is that, we will prompt a popup serving under Frizbit HTTPS subdomain in order to ask native permission as shown below.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/http-2.png "Permission popup for HTTP only website")

## Creating Google Project for Chrome
Google Chrome Browser uses Google’s Cloud Messaging Service (which is now merged with Google Firebase) for sending web push notifications. To be able to send and receive notifications via Google Chrome, we need to create a project for our website on this platform and then obtain our Legacy Server Key and Sender ID for this push notifications project.

While creating a new website on <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard,</a> 

* If you have selected HTTPS setup to collect the subscribers on your own domain, this step is required for your website.
* If you have not selected HTTPS setup, you don’t need to do this step as <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a> shall use its default Legacy Server Key and Sender ID in this case. However, in this case you wouldn’t be able to access the extra stats of your project on the Google Services interface.

To create your project on Google Cloud Messaging Service (Firebase) and get your Legacy Server Key and Google Sender ID, please follow the instructions below

1\. **Visit Google Firebase (previously Google Services Wizard)**

Visit the <a href="https://firebase.google.com/?cntapi=gcm&platform=android" target="_blank">Google Firebase.</a> 
If you are not logged in to any Google account, please log in to your Google Account first. On the page after logging in, click on the **Get Started** button.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-1.jpg "Creating a Firebase Application Step 1")

2\. **Start Adding Project on Google Firebase Console**

After logging in, you’ll be redirected to the console of Google Firebase.

* If you don’t have any previous projects associated with your Google account, you’ll be only shown the button of **Add Project**. Please click that **Add Project** button.
* If you have existing projects for the same website, you can continue using the same project for Frizbit as well. If that is the case, select your previous web project.
* If you have existing projects for iOS or Android, please ignore them and click on **Add Project** button.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-2.jpg "Creating a Firebase Application Step 2")

3\. **Define a Name to your _Project_**

As an example, we have typed _MySuperDomain_ in the screenshot below. You can type whatever name you prefer. As a suggestion, you can type domain name without any dots or extra characters.
Then, make sure that you the tick boxes of the conditions are ticked.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-3.jpg "Creating a Firebase Application Step 3")

4\. **Continue to the Dashboard of the Project**

After a couple of seconds, you’ll see that your new project is created and ready to use. Click on the **Continue** button to proceed.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-4.jpg "Creating a Firebase Application Step 4")

5\. **Go to Project Settings**

On the interface of the project, you’ll see a menu on the left. Click the settings icon on top of this menu. On the dropdown menu extended, click on **Project Settings** button.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-5.jpg "Creating a Firebase Application Step 5")

6\. **Click _Cloud Messaging_ tab**

On the page opened, you’ll see many tabs. Click on **Cloud Messaging** button, which is the 2nd tab from the left.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-6.jpg "Creating a Firebase Application Step 6")

7\. **Save _Legacy Server Key_ and _Sender ID_**

We will see two keys already generated on Google Cloud Messaging, they are called Legacy Server Key (also know as _Server API Key_) and Sender ID (also known as the _Project Number_).

Both keys will be asked while you are adding your website to the <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a>. We should copy and paste both of these keys in the corresponding fields on the **Configurations** step of adding the website to the Frizbit Dashboard.

![](https://raw.githubusercontent.com/frizbit/documentation/master/source/images/Firebase-7.jpg "Creating a Firebase Application Step 7")

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

## Fully HTTPS websites
The following installation steps will get Frizbit working on your _Fully_ HTTPS website. 

1. Go to the <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a>, and open Website Settings->Frizbit javascript. Copy all the codes shown there as below, which will include your API Key.
```
<link rel="manifest" href="manifest.json"> 
<script src='//cdn.frizbit.com/frizbitjs/[YOUR FRIZBIT APP KEY].js'></script>
<script type="text/javascript"> var frizbit = frizbit || []; frizbit.push(["init", {[YOUR FRIZBIT CONFIGURATIONS]}]); </script>
```
  
2. On your website, insert this code just above the closing `</head>` tag.

3. Download installation files and copy the files to the top-level directory (root, or '/') of your server. Installation files should be reachable as shown below:
	* https://yourwebsite.com/manifest.json
	* https://yourwebsite.com/FrizbitServiceWorker.js
	* https://yourwebsite.com/FrizbitUpdateWorker.js

4. Navigate to your website and be the first subscriber!

## Partly HTTPS websites
The following installation steps will get Frizbit working on your _Partly_ HTTPS website. 

1. Go to the <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a>, and open Website Settings->Frizbit javascript. Copy all the codes shown there as below, which will include your API Key.
```
<script src='//cdn.frizbit.com/frizbitjs/[YOUR FRIZBIT APP KEY].js'></script>
<script type="text/javascript"> var frizbit = frizbit || []; frizbit.push(["init", {[YOUR FRIZBIT CONFIGURATIONS]}]); </script>
```
  
2. On your website, insert this code just above the closing `</body>` tag.

3. Download installation files and copy the files to the subfolder directory of your server that you have entered while adding your website to <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard.</a> Installation files should be reachable as shown below:
	* https://yourwebsite.com/[Subfolder]/manifest.json
	* https://yourwebsite.com/[Subfolder]/FrizbitServiceWorker.js
	* https://yourwebsite.com/[Subfolder]/FrizbitUpdateWorker.js
	* https://yourwebsite.com/[Subfolder]/index.html
	* https://yourwebsite.com/[Subfolder]/iframe.html

4. Navigate to your website and be the first subscriber!

## HTTP only website
The following installation steps will get Frizbit working on your HTTP only website. 

1. Go to the <a href="https://dashboard.frizbit.com" target="_blank">Frizbit Dashboard</a>, and open Website Settings->Frizbit javascript. Copy all the codes shown there as below, which will include your API Key.
```
<script src='//cdn.frizbit.com/frizbitjs/[YOUR FRIZBIT APP KEY].js'></script>
<script type="text/javascript"> var frizbit = frizbit || []; frizbit.push(["init", {[YOUR FRIZBIT CONFIGURATIONS]}]); </script>
```
  
2. On your website, insert this code just above the closing `</body>` tag.

3. Navigate to your website and be the first subscriber!

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
