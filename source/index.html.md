---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - json--request: request
  - json--response: response

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors
  - api
  - guideline

search: true
---
# Introduction

SuiteCRM Api Docs (Owlting version)
test for github hooks2

# Authentication

* Client credentials Grant

**Headers**:<br>

param         | value
-----         | -----
Content-Type  | application/vnd.api+json
Accept        | application/vnd.api+json
Authorization | Bearer {{token}}

# Base URLs:
env        | url
---        | ---
staging    | https://crm-staging.owlting.com

# Authentication with Client Credentials

## Required parameters

param         | value
-----         | -----
grant_type    | client_credentials
client_id     | ExampleClientName
client_secret | ExampleSecretPassword

```json--request
{
    "grant_type": "client_credentials",
    "client_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "client_secret": "secret"
}
```

Example Response:

```json--response
{
   "token_type":"Bearer",
   "expires_in":3600,
   "access_token":"{{access_token}}"
}
```

Parameter    | description
----------   | ----------------------
token_type   | the Bearer token value
expires_in   | an integer representing the TTL of the access token
access_token | a JWT signed with the authorization server’s private key. It is required that you include this in the HTTP headers, each time you make a request to the API

# Get MetaData

## HTTP Request
`GET http://example.com/Api/docs/swagger/swagger.json`

# Available parameters
According to JsonApi specification, the available parameters are the following depending on the GET endpoint:

## Fields
Fields can filter on attribute object. Allowed keys are valid bean properties.

Example:

`http://example.com/V8/module/Accounts/11a71596-83e7-624d-c792-5ab9006dd493?fields[Accounts]=name,account_type`

```json--response
{
    "data": {
        "type": "Account",
        "id": "11a71596-83e7-624d-c792-5ab9006dd493",
        "attributes": {
            "name": "White Cross Co",
            "account_type": "Customer"
        },
        "relationships": {
            "AOS_Contracts": {
                "links": {
                    "related": "/V8/module/Accounts/11a71596-83e7-624d-c792-5ab9006dd493/relationships/aos_contracts"
                }
            }
        }
}
```

## Page
Page can filter beans and set pagination. Allowed key are number and size.

* page[number] : number of the wanted page

* page[size] : size of the result

Example:

`http://example.com/V8/module/Accounts?fields[Account]=name,account_type&page[number]=3&page[size]=1`

Result:

```json--response
{
    "meta": {
        "total-pages": 54
    },
    "data": [
        {
            "type": "Account",
            "id": "e6e0af95-4772-5773-ae70-5ae70f931feb",
            "attributes": {
                "name": "",
                "account_type": ""
            },
            "relationships": {
                "AOS_Contracts": {
                    "links": {
                        "related": "/V8/module/Accounts/e6e0af95-4772-5773-ae70-5ae70f931feb/relationships/aos_contracts"
                    }
                }
            }
        }
    ],
    "links": {
        "first": "/V8/module/Accounts?fields[Account]=name,account_type&page[number]=1&page[size]=1",
        "prev": "/V8/module/Accounts?fields[Account]=name,account_type&page[number]=2&page[size]=1",
        "next": "/V8/module/Accounts?fields[Account]=name,account_type&page[number]=4&page[size]=1",
        "last": "/V8/module/Accounts?fields[Account]=name,account_type&page[number]=54&page[size]=1"
    }
}
```
## Sort
Sort is only available when collections wanted to be fetched. Sorting is set to ASC by default. If the property is prefixed with hyphen, the sort order changes to DESC.

<aside class="warning"><strong>Important notice</strong>: we only support single sorting right now!</aside>

Example:

`http://example.com/V8/module/Accounts?sort=-name`

Result:

```json--response
{
    "data": [
        {
            "type": "Account",
            "id": "e6e0af95-4772-5773-ae70-5ae70f931feb",
            "attributes": {
                "name": "White Cross Co",
                "account_type": "Customer"
            },
            "relationships": {
                "AOS_Contracts": {
                    "links": {
                        "related": "/V8/module/Accounts/1d125d2a-ac5a-3666-f771-5ab9008b606c/relationships/aos_contracts"
                    }
                }
            }
        },
        {
            "type": "Account",
            "id": "7831d361-2f3c-dee4-d36c-5ab900860cfb",
            "attributes": {
                "name": "Union Bank",
                "account_type": "Customer"
            },
            "relationships": {
                "AOS_Contracts": {
                    "links": {
                         "related": "/V8/module/Accounts/7831d361-2f3c-dee4-d36c-5ab900860cfb/relationships/aos_contracts"
                    }
                }
            }
        }
    ],
}
```

## Filter

Our filter strategy is the following:

* filter[operator]=and

* filter[account_type][eq]=Customer

<aside class="warning"><strong>Important notice</strong>: we don’t support multiple level sorting right now!</aside>

### Supported operators

#### Comparison

<code>
EQ = '='<br>
NEQ = '<>'<br>
GT = '>'<br>
GTE = '>='<br>
LT = '<'<br>
LTE = '<='
</code>

#### Logical

`'AND', 'OR'`

Example 1:

`http://example.com/V8/module/Accounts?fields[Accounts]=name,account_type&filter[operator]=and&filter[account_type][eq]=Customer`

Example 1:

`http://example.com/V8/module/Accounts?filter[account_type][eq]=Customer`

# Endpoints

## Logout

`POST http://example.com/V8/logout`

## Get a module by ID

`GET http://example.com/V8/module/{moduleName}/{id}`

<aside class="notice">Available parameters: fields</aside>

Example:

`GET http://example.com/V8/module/Accounts/11a71596-83e7-624d-c792-5ab9006dd493?fields[Accounts]=name,account_type`

## Get collection of modules

`GET http://example.com/V8/module/{moduleName}`

<aside class="notice">Available parameters: fields, page, sort, filter</aside>

Example:

`GET http://example.com/V8/module/Accounts?fields[Accounts]=name,account_type&page[size]=4&page[number]=4`

## Create a module record

`POST http://example.com/V8/module`

```json--request
{
  "data": {
    "type": "Accounts",
    "id": "86ee02b3-96d2-47b3-bd6d-9e1035daff3a",
    "attributes": {
      "name": "Test account"
    }
  }
}
```

## Update a module record

`PATCH http://example.com/V8/module`

Example body:

```json--request
{
  "data": {
    "type": "Accounts",
    "id": "11a71596-83e7-624d-c792-5ab9006dd493",
    "attributes": {
      "name": "Updated name"
    }
  }
}
```

## Delte a module record

`DELETE http://example.com/V8/module/{moduleName}/{id}`

```json--response

HTTP/1.1 200

{
    "meta": {
        "message": "Record with id 9f66496b-e96b-96e0-bb6b-5f9a4aeea9c2 is deleted"
    },
    "data": []
}
```

## Get relationship

`GET http://example.com/V8/module/{moduleName}/{id}/relationships/{relatedModuleName}`

Example:

`GET http://example.com/V8/module/Accounts/129a096c-5983-1d59-5ddf-5d95ec91c144/relationships/Accounts`

## Create relationship

`POST http://example.com/V8/module/{moduleName}/relationships`

Example body:

```json--request
{
  "data": {
    "type": "Contacts",
    "id": "129a096c-5983-1d59-5ddf-5d95ec91c144"
  }
}
```

AccessDeniedException

```
{
    "errors": {
        "status": 400,
        "title": null,
        "detail": "[SuiteCRM] [AccessDeniedException] "
    }
}
```

## Delete relationship

`DELETE http://example.com/V8/module/{moduleName}/{id}/relationships/{relatedModule}/{relatedBeanId}`

Example:

`DELETE http://example/V8/module/Accounts/129a096c-5983-1d59-5ddf-5d95ec91c144/relationships/Accounts/11a71596-83e7-624d-c792-5ab9006dd493`

