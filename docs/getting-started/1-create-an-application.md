---
layout: default
title: Part 1 Create an application
parent: Getting Started
nav_order: 1
---

# Part 1: Create an application

[API AutoFlow Cloud](https://console.apiautoflow.com/){: .btn .btn-blue }

## Create API (Server and Endpoint)
Define how you want to expose the data. For example,

`http://localhost:1111/test`

Let’s create a Server with port number 1111 and an Endpoint with the URI /test

## 1. Create Server
Add a server by pressing the [Add] drop-down on the top of the screen.

![Create Server](/assets/images/create_server.png)

<img src="/assets/images/tip-icon.png" alt="!" width="20"/> Tips

The server will be created with a random port number. You can change the port number by press selecting the Server icon which opens the Server settings.

**Change Port Number**

Change the port number to 1111

![Port Number](/assets/images/port_number_change.png)

## 2. Create Endpoint
Add a server endpoint by pressing the [Add] drop-down on the top of the screen

![Create Endpoint](/assets/images/create-endpoint.png)

<img src="/assets/images/tip-icon.png" alt="!" width="20"/> Tips

The endpoint by default has a root path /. You can change the root path by press selecting the Endpoint icon which opens the Endpoint settings.

### Change Path

* Change the path to /test
* Change the method to GET

![Change Path](/assets/images/change-endpoint-path.png)

## Integration with Database
Use database connector to get data from Postgres

Add Postgres Database Action
From the right panel, press the Action tab, and drag-n-drop the database/Postgres action to the flow

![Database Integration](/assets/images/database-integration.gif)

Configure Postgres Data Action
**Enter the credentials for the database.**

```yaml
query: [S] SELECT * FROM public.demo
address: [S] 129.146.123.245
port: [N] 5432
username: [S] psdju
password: [S]
database: [S]
format: [processed]
use-mock-result: [B] Uncheck
```

#### Output the data into HTTP Response Body.

Drag and drop the response body from the flow transaction data to the output

![Output](/assets/images/action-output.gif)

**Check Data**: Make sure you are getting the data by going to

```
http://localhost:1111/test
```

### Data Transformation
Logic Execution: Transform data and apply automation. There are many data handling actions available.

Join “First and Last” name
For this exercise, we will join two strings using the string/join action.

Add String/join action to the flow

Configure String/join Action

Be sure to set output to “Response/body”

**Check data**: Go to the URL http://localhost:1111/test to check the data.

Reformat Timestamp
For the second exercise, we will change the format of date and time as below.

```
2021/04/16  ----->   2021-04-16
```
Add String/replace action to the flow

Configure String/replace action

Be sure to set output to “Response/body”

Check data: Go to the URL http://localhost:1111/test to check the data.
