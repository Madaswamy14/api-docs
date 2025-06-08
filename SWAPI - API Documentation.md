# SWAPI API Reference Document

## Overview

### Introduction

The Star Wars API (SWAPI) is a public API that provides data from the Star Wars universe, including information on characters, films, planets, and more. This documentation will help you make API calls to retrieve various details about the Star Wars universe.

### Getting Started

**Base URL**

The API is available at https://swapi.dev/api/

**Prerequisites**

You can use curl or httpie to make API calls. You can install them from [curl](http://curl.haxx.se/) or [httpie](http://httpie.org/) using the package manager of your choice.

**Authentication/Authorization**

SWAPI is an open API that does not require Authentication/Authorization.

**Pricing**

SWAPI is absolutely free to use.

**Status Codes**

The following are the HTTP status codes that you may encounter when using the API:

| Status Code | Description |
|-------------|-------------|
| 200 OK | Indicates a successful response |
| 404 Not Found | Indicates that there is no resource with the specified id |

**Rate Limits**

We have an API throttle that blocks IP addresses that exceed our API rate limits. The rate limit for general API requests via an IP address is **10,000 requests per day**.

## API Reference

### People

#### Get All People

**Method**

GET - Retrieves the details of all people.

**Request URL**

https://swapi.dev/api/people

**Response Parameters**

| Parameter | Child Parameter | Data Type | Description |
|-----------|----------------|-----------|-------------|
| count | | integer | Specifies the total number of people |
| next | | nullable string | Specifies the URL of the next page; if none exists, "null" will be displayed |
| previous | | nullable string | Specifies the URL of the previous page; if none exists, "null" will be displayed |
| results | | array of objects | |
| | name | string | Specifies the name of the person |
| | height | string | Specifies the height of the person |
| | mass | string | Specifies the mass of the person |
| | hair_color | string | Specifies the hair color of the person |
| | skin_color | string | Specifies the skin color of the person |
| | eye_color | string | Specifies the eye color of the person |
| | birth_year | string | Specifies the birth year of the person |
| | gender | string | Specifies the gender of the person |
| | homeworld | string | Specifies the URL of a planet where the person was born or inhabits |
| | films | array of string | Specifies an array of URLs containing information about the films the person has appeared in |
| | species | nullable array of string | Specifies an array of URLs containing information about the species the person belongs to |
| | vehicles | nullable array of string | Specifies an array of URLs containing information about every vehicle the person has piloted |
| | starships | nullable array of string | Specifies an array of URLs containing information about every spaceship the person has piloted |
| | created | string | Specifies the date and time when the person's details were created |
| | edited | string | Specifies the date and time the person's details were edited |
| | url | string | Specifies the URL that contains the person's details |

**Example Response**

```json
{
  "count": 82,
  "next": "https://swapi.dev/api/people/?page=2",
  "previous": null,
  "results": [
    {
      "name": "Luke Skywalker",
      "height": "172",
      "mass": "77",
      "hair_color": "blond",
      "skin_color": "fair",
      "eye_color": "blue",
      "birth_year": "19BBY",
      "gender": "male",
      "homeworld": "https://swapi.dev/api/planets/1/",
      "films": [
        "https://swapi.dev/api/films/1/",
        "https://swapi.dev/api/films/2/",
        "https://swapi.dev/api/films/3/",
        "https://swapi.dev/api/films/6/"
      ],
      "species": [],
      "vehicles": [
        "https://swapi.dev/api/vehicles/14/",
        "https://swapi.dev/api/vehicles/30/"
      ],
      "starships": [
        "https://swapi.dev/api/starships/12/",
        "https://swapi.dev/api/starships/22/"
      ],
      "created": "2014-12-09T13:50:51.644000Z",
      "edited": "2014-12-20T21:17:56.891000Z",
      "url": "https://swapi.dev/api/people/1/"
    }
  ]
}
```

**Response Status Codes**

- 200 OK
- 404 NOT FOUND

#### Get a Person by ID

**Method**

GET - Retrieves the details of a person by ID.

**Request URL**

https://swapi.dev/api/people/{id}

**Sample URL**

https://swapi.dev/api/people/5

**Path Parameters**

| Parameter | Required | Data Type | Description |
|-----------|----------|-----------|-------------|
| id | Yes | integer | Specifies the person's ID |

**Response Parameters**

| Parameter | Data Type | Description |
|-----------|-----------|-------------|
| name | string | Specifies the name of the person |
| height | string | Specifies the height of the person |
| mass | string | Specifies the mass of the person |
| hair_color | string | Specifies the hair color of the person |
| skin_color | string | Specifies the skin color of the person |
| eye_color | string | Specifies the eye color of the person |
| birth_year | string | Specifies the birth year of the person |
| gender | string | Specifies the gender of the person |
| homeworld | string | Specifies the URL of a planet where the person was born or inhabits |
| films | array of string | Specifies an array of URLs containing information about the films the person has appeared in |
| species | nullable array of string | Specifies an array of URLs containing information about the species the person belongs to |
| vehicles | nullable array of string | Specifies an array of URLs containing information about every vehicle the person has piloted |
| starships | nullable array of string | Specifies an array of URLs containing information about every spaceship the person has piloted |
| created | string | Specifies the date and time when the person's details were created |
| edited | string | Specifies the date and time the person's details were edited |
| url | string | Specifies the URL that contains the person's details |

**Example Response**

```json
{
  "name": "Leia Organa",
  "height": "150",
  "mass": "49",
  "hair_color": "brown",
  "skin_color": "light",
  "eye_color": "brown",
  "birth_year": "19BBY",
  "gender": "female",
  "homeworld": "https://swapi.dev/api/planets/2/",
  "films": [
    "https://swapi.dev/api/films/1/",
    "https://swapi.dev/api/films/2/",
    "https://swapi.dev/api/films/3/",
    "https://swapi.dev/api/films/6/",
    "https://swapi.dev/api/films/7/"
  ],
  "species": [
    "https://swapi.dev/api/species/1/"
  ],
  "vehicles": [
    "https://swapi.dev/api/vehicles/30/"
  ],
  "starships": [],
  "created": "2014-12-10T15:20:09.791000Z",
  "edited": "2014-12-20T21:17:50.315000Z",
  "url": "https://swapi.dev/api/people/5/"
}
```

**Response Status Codes**

- 200 OK
- 404 NOT FOUND