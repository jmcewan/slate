---
title: dostuff Reference

language_tabs:
  - shell
  - ruby

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/jmcewan/dostuff'>Documentation Powered by Slate</a>

includes:
  - errors

##search: true
---

# Work in Progress

Hi - this is a very rough start to the ```dostuff``` instructions

@jamesmcewan 

<aside class="success">
got the documentatoin to work
</aside>


# Introduction

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.


# _dostuff_ for Users

The purpose of dostuff is to allow a low effort way to deploy cloud workers by using a colleciton of scripts and text files  

```shell
$cd my_project/
$my_project/ dostuff create
Project ID Created and saved in '.config.yml'
$my_project/
```
Once the unique project id (UUID) has been created it will be used to group the multiple scripts to ensure the data is not mixed up between "jobs".

Dostuff jobs consist of a minimum of three files
 
* Input Files (where the data is and how to interpret it)
* Job Files (what you want to do with data)
* Output Files (where you want it to go) 

Multiple Input files can created and funnelled into a Job File

```shell
$my_project/ dostuff input
How do you want connect the data? (local | s3 | sftp | ftp)
local
What format is the data? (CSV | TXT )
csv
Do the files have a prefix? (e.g. Transactions.)
bricks
Do the files have a suffix? (e.g. .csv)
.csv
How many lines at the top of the file should be skipped? (0 if none)
0
How many lines at the bottom of the file should be skipped? (0 if none)
0

```






# _dostuff_ for Developers 

Inspired by tools like jekyllrb and markdown that allow websites to be deployed from a few files, dostuff hopes to do the same for "cloud workers"

`config.yml` contains the project UUID

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

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace `meowmeowmeow` with your personal API key.
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
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/kittens`

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
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

