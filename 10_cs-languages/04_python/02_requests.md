# Python Requests Library

## Table of Contents

1. [Make a Request](#Make-a-Request)
1. [Passing Parameters in URLs](#Passing-Parameters-in-URLs)
1. [Response Content](#Response-Content)
1. [Request Headers](#Requests-Headers)
1. [Request Post](#Requests-Post)

## Installation

- comming up

## Make a Request

Let's get a webpage with its content inside a response `r`.
```python
import requests
r = requests.get('https://api.github.com/events')
# the object r now has all the info we need
# we can access this info with diff methods & attributes
```
Examples of how to make other HTTP request types.
```python
r = requests.put('https://httpbin.org/put', data = {'key':'value'})
r = requests.delete('https://httpbin.org/delete')
r = requests.head('https://httpbin.org/get')
r = requests.options('https://httpbin.org/get')
```

## Passing Parameters in URLs

```python
# passing values through query string paramaters (after the < ? >).
# to do this using the  < get() >, pass data to < params >.
# pass a dictionary of value pairs to the < params > keyword.
payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.get('https://httpbin.org/get', params=payload)

# you can print the string to see how requests constructed it
print(r.url)
https://httpbin.org/get?key2=value2&key1=value1
```

## Response Content

Type of information we can access from the response `r` :
```python
#####     .STATUS_CODE     #####
# status code [a 200 return means the request was successful]
r.status_code

#####     .RAISE_FOR_STATUS()     #####
# If the response was successful, no Exception will be raised
r.raise_for_status()

#####     .JSON()     #####
# there is JSON decoder, in case we are dealing w JSON data
r = requests.get('https://api.github.com/events')
r.json() # {'repository': {'open_issues': 0, 'url': 'https://github.com/...

#####     .TEXT     #####
# decoding of bytes to a str requires an encoding scheme, 
# requests will try to guess encoding based on response’s headers 
# if not specified, you can provide an explicit encoding 
# by setting .encoding before accessing .text:
r = requests.get('https://api.github.com/events')
r.encoding = 'utf-8' # Optional: requests infers this internally
r.text # '{"repository":{"open_issues":0,"url":"https://github.com/...

#####     .CONTENT     #####
# access response body as bytes, for non-text requets
# binary response content
r = requests.get('https://api.github.com')
r.content # b'{"current_user_url":"https://api.github.com/user",...

#####     .HEADERS     #####
# response headers can give useful info, to access :
r.headers # {'Server': 'Github.com', 'Date': 'Mon, 10 Dec 2018 ...}
```

## Requests Headers

If you want to add custom HTTP < headers > to a request, you must pass them through a dictionary to the < headers > parameter.
```python
headers = {'x-user': 'test123'}
r = requests.get('https://jsonplaceholder.typicode.com/users', 
headers=headers)
```

## Requests Post

Use the `requests.post()` method to send data to be posted.
```python
r = requests.post(url, data={key: value}, json={key: value}, **kwargs)

# print content of request, if params were json
print(r.json())
```
Parameters
| Parameters       | Description     |
| :------------- | :----------:  |
|  url | required. The url of the request.   |
| data   | (optional) Dictionary, list of tuples, bytes, or a file object to send to body of Request |
| json | (optional) json data to send in the body of the `request`   |
| **kwargs   | (optional) arguments that `request` takes|


## POST a Multipart-Encoded File

## Response Status Codes

## Response Headers

## Cookies

## Redirection and History

## Timeouts

## Errors and Exceptions

# Advanced Usage

## Session Objects

## Requests and Response Objects

## Prepared Requests

## SSL Cert Verification

## Client Side Certificates 

## CA Certificates

## Body Content Workflow

## Keep-Alive

## Streaming Uploads

## Chumk-Encoded Requests

## POST Multiple Multipart-Encoded Files

## Event Hooks

## Custom Authentication

## Streaming Requests

## Proxies

## Compliance

## HTTP Verbs

## Custom Verbs

## Link Headers

## Transport Adapters

## Blocking  or Non-Blocking?

## Headers Ordering

## Timeouts

# Authentication

## Basic Authentication

## Digest Authentication

## Oauth 1 Authentication

## Oauth 2 and OpenID Connect Authentication

## Other Authentication

## New Forms of Authentication