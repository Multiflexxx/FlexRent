
# Flex-Rent
## OBJECT-DEFINITION
***
Offer:<a name="offer_object"></a>
```javascript
{
    offer_id: string,
    title: string,
    description: string,
    number_of_ratings: number,
    rating: number,
    price: number,
    category: {
        name: string,
        category_id: number,
        picture_link?: string
    },
    picture_links?: Array<string>,
    blocked_dates?: Array<{
        from_date: Date,
        to_date: Date
    }>,
    lessor?: {
        first_name: string,
        last_name: string,
        user_id: string,
        post_code: string,
        city: string,
        verified: boolean,
        lessor_rating: number,
        number_of_lessor_ratings: number
    } 
}
```
IMPORTANT:<br>
Offers in Arrays for `GET` calls do not contain `blocked_dates`!

Category:<a name="category_object"></a>
```javascript
{
    category_id: number,
    name: string,
    picture_link: string
}
```

Request:<a name="request_object"></a>
```javascript
{
    request_id: string,
    user: User,
    offer: Offer,
    status_id: number,
    date_range: {
        from_date: Date,
        to_date: Date
    },
    message: string,
    qr_code_id: string
}
```

User:<a name="user_object"></a>
```javascript
{
    user_id: string,
    first_name: string,
    last_name: string,
    email?: string,
    phone_number?: string,
    password_hash?: string,
    verified: boolean,
    place_id?: number,
    post_code?: string,
    city?: string,
    street?: string,
    house_number?: string,
    lessee_rating: number,
    number_of_lessee_ratings: number,
    lessor_rating: number,
    number_of_lessor_ratings: number,
    date_of_birth?: Date,
}
```

***
## OFFER
***

## `Methode` /template
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| limit (query) | string         |                |Standard=25                        


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 
| 201           | CREATED               |  

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           |
| 401           | UNAUTHORIZED          |
| 404           | NOT  FOUND            |
| 500           | INTERNAL SERVER ERROR |
<br>

## `GET`/offer/all
#### Get all offers or only the offers filtered by limit, category and/or search

### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| post_code (query) | string     | X              | Postcode of user
| limit (query) | number         |                |Standard limit: 25                        
| category (query)| number       |                | Category ID of the offer
| search (query) | string        |                | Part of title of the offer
| distance (query) | number      |                | Standard distance: 30 km
| price_below (query)| number    |                | Price of offer lower than
| rating_above (query)| number   |                | Min rating of offer

### Success Responses

| Code          | Description           | Message      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Response example:

`Array<`[Offer](#offer_object)`>`


### Error
| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           | Not a valid input         
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/top-categories
#### Returns the four categories with most offers in it
### Parameters

none 


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Response example:

`Array<`[Category](#category_object)`>`

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------          
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/categories
#### Returns all available categories

### Parameters

none 


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Response example:

`Array<`[Category](#category_object)`>`

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------          
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/images/{id}

#### Returns an image from disk
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |       x        | Image ID                       


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |  

Returns the image.

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 404           | NOT  FOUND            | Image not found
<br>

## `GET` /offer/user-offers/{id}

#### Returns all offers for a user id.
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         | x              | ID of the user


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |  

Response example:

`Array<`[Offer](#offer_object)`>`

### Error

| Code          | Description           | Error Message      
| ------------- |--------------------   |-------------
| 400           | BAD REQUEST           | Not a valid user/session
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `GET` /offer
#### Returns a set of offers to be shown on the Homepage
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| post_code (query) | string     |       x        | Postcode of user
| distance (query)  | number     |                | Default distance: 30km


### Success Responses

| Code          | Description           | Response      
| ------------- |--------------------   |-------------
| 200           | OK                    | 

Response example:

```javascript
{
    "best_offers": Array<Offer>,
    "best_lessors": Array<Offer>,
    "latest_offers": Array<Offer>
}
```


### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/{id}
#### Returns the offer object with the given offer ID
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |       x        | ID of the offer                      


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | No id is provided
| 404           | NOT  FOUND            | Offer not found
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `PATCH` /offer/{id}
#### Updates an offer given the id and parameters to be updated. Authorization needed. 
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |        x       | ID of the offer      
| body (body)   | object         | x              | Offer body with the updated attributes<br>   ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```}, ```<br>&nbsp;&nbsp;&nbsp;```"offer": {```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "title": "New offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "description": "This is a new offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "price": 12.50, ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "category": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"category_id": 1```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "blocked_dates": [```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```{ ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"from_date": "2021-04-23T00:00:00.000Z", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"to_date": "2021-04-23T00:00:00.000Z" ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```}```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```],```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"delete_images": [```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"/path/to/file/", "/path/to/file/"```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```]```<br>&nbsp;&nbsp;&nbsp;```}```<br>``` }```    


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```

### Error

| Code          | Description           | Error Message      
| ------------- |--------------------   |------------- 
| 400           | BAD REQUEST           | Not a valid input / Couldn't update offer
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `PUT` /offer
#### Creates a new offer using the parameters passed in the request body
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| body (body) | object         |  x              | Offer body that should be created <br> ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```}, ```<br>&nbsp;&nbsp;&nbsp;```"offer": {```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "title": "New offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "description": "This is a new offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "price": 12.50, ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "category": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"category_id": 1```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "blocked_dates": [```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```{ ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"from_date": "2021-04-23T00:00:00.000Z", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"to_date": "2021-04-23T00:00:00.000Z" ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```}```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```]```<br>&nbsp;&nbsp;&nbsp;```}```<br>``` }```                        

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 201           | CREATED               |  

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```
### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Not a valid input
| 500           | INTERNAL SERVER ERROR | Could not create offer

<br>

## `POST` /offer/images
#### Accepts up to ten files to upload images
### Parameters
Accepts only a multipartform request (instead of JSON)

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| images (path) | array         |       x        |Array of multipart image files
| offer_id     | string         |       x        | ID of offer <br> ```eef88333-2118-4f2e-950c-444f2a31da10```
| user_id      | string         |       x        | ID of user <br> ```eef88333-2118-4f2e-950c-444f2a31da10```
| session_id   | string         |       x        | ID of session <br> ```eef88333-2118-4f2e-950c-444f2a31da10```


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```
### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Images are not an array
| 404           | NOT  FOUND            |Not a valid user/session
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `PATCH` /offer/delete-offer/{id}
#### Deletes an offer by id. Authorization needed.
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         | Authentication object```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```}```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```
### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid user/session
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `POST` /offer/{id}
#### Books offer for a specified time frame. Authorization needed.
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         | ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;```"message": "message",```<br>&nbsp;&nbsp;&nbsp;```"date_range": {```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"from_date": "2021-04-23T00:00:00.000Z",```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"to_date": "2021-04-23T00:00:00.000Z"```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```}```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Response example:
[Request](#request_object)
```javascript
{
    "request_id": "ef88333-2118-4f2e-950c-444f2a31da10",
    "user": {
        "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "first_name": "Name",
        "last_name": "Name",
        "verified": true,
        "place_id": 8952,
        "lessee_rating": 0,
        "number_of_lessee_ratings": 0,
        "lessor_rating": 0,
        "number_of_lessor_ratings": 0,
        "email": "mail@test.com",
        "phone_number": "123456789",
        "street": "Street",
        "house_number": "4",
        "date_of_birth": "2020-06-12T22:00:00.000Z",
        "post_code": "01234",
        "city": "City"
    },
    "offer": {
        "offer_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "title": "Title",
        "description": "Description",
        "number_of_ratings": 1,
        "rating": 5.0,
        "price": 12.25,
        "category": {
            "name": "Category 1",
            "category_id": 1,
            "picture_link": "picture_link"
        },
        "picture_links": [
            "/path/to/image/"
        ],
        "lessor": {
            "first_name": "Name",
            "last_name": "Name",
            "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
            "post_code": "1067",
            "city": "City",
            "verified": false,
            "lessor_rating": 5.0,
            "number_of_lessor_ratings": 20
        },
        "blocked_dates": [
            {
                "from_date": "2021-04-22T22:00:00.000Z",
                "to_date": "2021-04-22T22:00:00.000Z"
            }
        ]
    },
    "status_id": 1,
    "date_range": {
        "from_date": "2021-05-01T00:00:00.000Z",
        "to_date": "2021-05-01T00:00:00.000Z",
    },
    "message": "Message"
}
```

### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `POST` /offer/rate/{id}
#### Rate an offer. Authorization needed. 
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         | ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;```"rating": 4.5```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
```javascript
{
    "offer_id": "eef88333-2118-4f2e-950c-444f2a31da10",
    "title": "Title of the offer",
    "description": "Description of the offer (up to 500 chars)",
    "number_of_ratings": 1,
    "rating": 5.0,
    "price": 12.25,
    "category": {
        "name": "Electronics",
        "category_id": 1,
        "picture_link": "/link/to/image/"
    },
    "picture_links": [
      "/link/to/image/",
      "/link/to/image/"
    ],
    "lessor": {
        "first_name": "Name",
        "last_name": "Name",
        "user_id": "eef88333-2118-4f2e-950c-444f2a31da10",
        "post_code": "1067",
        "city": "Dresden",
        "verified": false,
        "lessor_rating": 4.1,
        "number_of_lessor_ratings": 20
    },
    "blocked_dates": [
        {
            "from_date": "2021-04-23T00:00:00.000Z",
            "to_date": "2021-04-23T00:00:00.000Z"
        }
    ]
}
```
### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

## `POST` /offer/user-requests
#### returns a request for a given request id OR all requests for a given user and status
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| body (body)   | object        |      x         | ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;```"request"?: {}, "status_code":5, "lessor":true```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
Array<[Request](#request_object)>
OR
[Request](#request_object)
```javascript
{
    "request_id": "ef88333-2118-4f2e-950c-444f2a31da10",
    "user": {
        "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "first_name": "Name",
        "last_name": "Name",
        "verified": true,
        "place_id": 8952,
        "lessee_rating": 0,
        "number_of_lessee_ratings": 0,
        "lessor_rating": 0,
        "number_of_lessor_ratings": 0,
        "email": "mail@test.com",
        "phone_number": "123456789",
        "street": "Street",
        "house_number": "4",
        "date_of_birth": "2020-06-12T22:00:00.000Z",
        "post_code": "01234",
        "city": "City"
    },
    "offer": {
        "offer_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "title": "Title",
        "description": "Description",
        "number_of_ratings": 1,
        "rating": 5.0,
        "price": 12.25,
        "category": {
            "name": "Category 1",
            "category_id": 1,
            "picture_link": "picture_link"
        },
        "picture_links": [
            "/path/to/image/"
        ],
        "lessor": {
            "first_name": "Name",
            "last_name": "Name",
            "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
            "post_code": "1067",
            "city": "City",
            "verified": false,
            "lessor_rating": 5.0,
            "number_of_lessor_ratings": 20
        },
        "blocked_dates": [
            {
                "from_date": "2021-04-22T22:00:00.000Z",
                "to_date": "2021-04-22T22:00:00.000Z"
            }
        ]
    },
    "status_id": 1,
    "date_range": {
        "from_date": "2021-05-01T00:00:00.000Z",
        "to_date": "2021-05-01T00:00:00.000Z",
    },
    "message": "Message"
}
```
### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

## `POST` /offer/handle-requests
#### Accepts a request object; Is used for whole booking process
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| body (body)   | object        |      x         | ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "eef88333-2118-4f2e-950c-444f2a31da10", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "eef88333-2118-4f2e-950c-444f2a31da10" ```<br>&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;```"request": {"status_code": 5, ...}, ```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

Example response:
[Request](#request_object)
```javascript
{
    "request_id": "ef88333-2118-4f2e-950c-444f2a31da10",
    "user": {
        "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "first_name": "Name",
        "last_name": "Name",
        "verified": true,
        "place_id": 8952,
        "lessee_rating": 0,
        "number_of_lessee_ratings": 0,
        "lessor_rating": 0,
        "number_of_lessor_ratings": 0,
        "email": "mail@test.com",
        "phone_number": "123456789",
        "street": "Street",
        "house_number": "4",
        "date_of_birth": "2020-06-12T22:00:00.000Z",
        "post_code": "01234",
        "city": "City"
    },
    "offer": {
        "offer_id": "ef88333-2118-4f2e-950c-444f2a31da10",
        "title": "Title",
        "description": "Description",
        "number_of_ratings": 1,
        "rating": 5.0,
        "price": 12.25,
        "category": {
            "name": "Category 1",
            "category_id": 1,
            "picture_link": "picture_link"
        },
        "picture_links": [
            "/path/to/image/"
        ],
        "lessor": {
            "first_name": "Name",
            "last_name": "Name",
            "user_id": "ef88333-2118-4f2e-950c-444f2a31da10",
            "post_code": "1067",
            "city": "City",
            "verified": false,
            "lessor_rating": 5.0,
            "number_of_lessor_ratings": 20
        },
        "blocked_dates": [
            {
                "from_date": "2021-04-22T22:00:00.000Z",
                "to_date": "2021-04-22T22:00:00.000Z"
            }
        ]
    },
    "status_id": 1,
    "date_range": {
        "from_date": "2021-05-01T00:00:00.000Z",
        "to_date": "2021-05-01T00:00:00.000Z",
    },
    "message": "Message"
}
```
### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...


## USER
***

## `GET` /user/{id}
#### Returns a single user specified by the ID passed in the URL.
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| id (path) | string         |     x           | ID of the user                     


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 404           | NOT  FOUND            | User not found
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `PUT` /user
#### Creates a user with the Specified parameters in the request body
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| body (body) | object         |     x           | ``` {```<br>```"user_id": "", ```<br>``` "first_name": "Max", ```<br>``` "last_name": "Mustermann", ```<br>``` "email": "Max.Mustermann@flexrent.com", ```<br>``` "phone_number": "01234567", ```<br>``` "password_hash": "hoüh03uphrfupn",```<br>```  "verified": "false", ```<br>``` "place_id"= 1, ```<br>``` "post_code": "1234", ```<br>``` "city": "Musterstadt", ```<br>``` "street": "Musterstraße", ```<br>```"house_number": 11, ```<br>```"lessee_rating": 0, ```<br>```"number_of_lessee_ratings": 0, ```<br>```"lessor_rating": 0, ```<br>```"number_of_lessor_ratings": 0, ```<br>```"date_of_birth": 1989-04-23T00:00:00.000Z ```<br>```}```


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |------------- 
| 201           | CREATED               |  

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Not a valid input
| 401           | UNAUTHORIZED          | Email and password don't match
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `PATCH` /user
#### Updates a specified user with the data passed in the request's body. Authorization needed. 
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| body (body) | object         |           x     | ``` { ```<br>``` "auth": { ```<br>```"session": { ```<br>```"session_id": "joa9he9rqnaoö", ```<br>``` "user_id": "1" }```<br>```}, ```<br>```"user": { ```<br>``` "user_id": "1", ```<br>``` "first_name": "Max", ```<br>``` "last_name": "Mustermann", ```<br>``` "email": "Max.Mustermann@flexrent.com", ```<br>``` "phone_number": "01234567", ```<br>``` "password_hash": "hoüh03uphrfupn",```<br>```  "verified": "false", ```<br>``` "place_id"= 1, ```<br>``` "post_code": "1234", ```<br>``` "city": "Musterstadt", ```<br>``` "street": "Musterstraße", ```<br>```"house_number": 11, ```<br>```"lessee_rating": 0, ```<br>```"number_of_lessee_ratings": 0, ```<br>```"lessor_rating": 0, ```<br>```"number_of_lessor_ratings": 0, ```<br>```"date_of_birth": 1989-04-23T00:00:00.000Z ```<br>```},```<br>```"password": { ```<br>```"old_password_hash": "h9qhdujipad", ```<br>```"new_password_hash": "j9h3en9uamp" }```<br>```}```                       


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |   

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Invalid Input
| 401           | UNAUTHORIZED          | Invalid authorization parameters
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `DELETE` /user/{id}
#### Deletes user given a ID and sufficient authorization.
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| id (path) | string         |      x          |ID of the user that should be deleted
| body (body)   | object        | x             | ```{ ```<br> &nbsp; &nbsp; &nbsp; ``` "auth": {```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;``` "session_id": "iq9eduq9emd"```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```}```<br>```}```


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           |
| 401           | UNAUTHORIZED          |
| 404           | NOT  FOUND            |
| 500           | INTERNAL SERVER ERROR |

<br>

## `POST` /user
#### Used for logging in a user, either with a session or email and password.
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| body (body) | object         |      x          |``` { ```<br>&nbsp; &nbsp; &nbsp;``` "auth": { ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"login": { ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"email": "Max.Mustermann@flexrent.com", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"password_hash": "h92n9udmdoq32" ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```}, ```<br> &nbsp; &nbsp; &nbsp;```"session": { ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"session_id": "hpqn39udnipn", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"user_id": "1"```<br>&nbsp; &nbsp; &nbsp;```}```<br>```}```                        


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |   

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Invalid authorization parameters
| 401           | UNAUTHORIZED          | Invalid session / Password and email don't match
| 404           | NOT  FOUND            | User not found
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `POST` /user/rate
#### Rate a user.
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| body (body) | object         |     x           |``` { ```<br>&nbsp; &nbsp; &nbsp;```"auth": ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"session": {```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"session_id": "u02duq9pnupni9", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"user_id": "2" ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```} ```<br>&nbsp; &nbsp; &nbsp;```}, ```<br>&nbsp; &nbsp; &nbsp;```"rating": { ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"user_id": "1", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"rating_type": "", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"rating": 5, ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"headline": "Super Typ", ```<br>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;```"text": "richtig geiler Typ" ```<br>&nbsp; &nbsp; &nbsp;```} ```<br>```}```                       


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |   

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Invalid input
| 401           | UNAUTHORIZED          | Invalid session
| 404           | NOT  FOUND            | User not found
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>
