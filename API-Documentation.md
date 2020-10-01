
# Flex-Rent
## OFFER
***

## `GET` /offer/all
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
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
| limit (query) | string         |                |Standard=25                        
| category (query)| string       |                | Category ID of the offer
| search (query) | string        |                | Part of title of the offer

### Success Responses

| Code          | Description           | Message      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error
| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           | Not a valid input         
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/categories
### Parameters

none                     


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------          
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/images/{id}
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |       x        |Image ID                       


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |  

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 404           | NOT  FOUND            | Image not found
<br>

## `GET` /offer/user-offers (authentification required)
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| body (body)   | object         | x              |   body object for the user authentification <br>```{ ```<br>```"session_id": "hwhroqhqrprhqp20",```<br>``` "user_id": "1"```<br>```}  ```                


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    |  

### Error

| Code          | Description           | Error Message      
| ------------- |--------------------   |-------------
| 400           | BAD REQUEST           | Not a valid user/session
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `GET` /offer
### Parameters

none                       


### Success Responses

| Code          | Description           | Response      
| ------------- |--------------------   |-------------
| 200           | OK                    | 


### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `GET` /offer/{id}
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |       x        | ID of the offer                      


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | No id is provided
| 404           | NOT  FOUND            | Offer not found
| 500           | INTERNAL SERVER ERROR | Something went wrong

<br>

## `PATCH` /offer/{id}
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| id (path)     | string         |        x       | ID of the offer      
| body (body)   | object         | x              | Offer body with the updated attributes<br>  ```{```<br>```"session_id": "hka09whoöam", ```<br>```"user_id": "1",```<br>``` "title": "Test offer", ```<br>``` "description": "This is a test offer", ```<br>``` "price": 12.50, ``` <br>``` "category_id": 1, ``` <br>``` "delete_images": [...], ``` <br>```"blocked_dates": [{ ```<br>```"from_date": "2021-04-23T00:00:00.000Z", ```<br>```"to_date": "2021-04-23T00:00:00.000Z" }]```<br>```} ```       


### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 


### Error

| Code          | Description           | Error Message      
| ------------- |--------------------   |------------- 
| 400           | BAD REQUEST           | Not a valid input / Couldn't update offer
| 500           | INTERNAL SERVER ERROR | Something went wrong
<br>

## `PUT` /offer
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| body (body) | object         |  x              | Offer body that should be created <br> ```{```<br>```"session_id": "hoazuebq98zb", ```<br>``` "user_id": "1", ```<br>``` "title": "New offer", ```<br>``` "description": "This is a new offer", ```<br>``` "price": 12.50, ```<br>``` "category_id": 1, "blocked_dates": [{ ```<br>```"from_date": "2021-04-23T00:00:00.000Z", ```<br>```"to_date": "2021-04-23T00:00:00.000Z" }]```<br>```} ```                        

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 201           | CREATED               |  

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |------------- 
| 400           | BAD REQUEST           | Not a valid input
| 500           | INTERNAL SERVER ERROR | Could not create offer

<br>

## `PUT` /offer/images
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| images (path) | array         |       x        |Array of multipart image files
| body (body)   | object        |      x         |```{```<br>```"session_id": 1,```<br>``` "offer_id": 1,```<br>``` "user_id": 1```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Images are not an array
| 404           | NOT  FOUND            |Not a valid user/session
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `DELETE` /offer/{id}
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         |```{```<br>```"session_id": 1,```<br>``` "user_id": 1```<br>```}```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid user/session
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `POST` /offer/{id}
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         |```{```<br>```"session_id":1, ```<br>```"user_id":1,```<br>``` "message": `Heyhoooooooo`,```<br>``` "date_range":[{```<br>```"from_date": "2021-04-23T00:00:00.000Z",```<br>``` "to_date": "2021-04-23T00:00:00.000Z"}]```<br>```} ```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error 

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...

<br>

## `POST` /offer/rate/{id}
### Parameters

| Name          | Type          | Required       |   Description
| ------------- |-------------  |-------------   | -----
| id (path)     | string        |       x        |ID of the offer to be rated 
| body (body)   | object        |      x         |```{```<br>```"session_id":1, ```<br>```  "user_id":1,```<br>```"rating": 4.5```<br>```} ```

### Success Responses

| Code          | Description           | Response      
| ------------- |---------------------  |-------------
| 200           | OK                    | 

### Error

| Code          | Description           | Error Message      
| ------------- |---------------------  |-------------
| 400           | BAD REQUEST           |Not a valid offer
| 404           | NOT  FOUND            |Not a valid offer
| 500           | INTERNAL SERVER ERROR |Something went wrong...



## USER
***
## `GET` /user/all
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |------------    | -----
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

## `GET` /user/{id}
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