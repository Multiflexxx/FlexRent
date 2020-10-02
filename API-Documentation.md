
# Flex-Rent
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
#### Returns all available categories

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

#### Returns an image from disk
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

## `GET` /offer/user-offers

#### Returns all offers for a user id. Authorization required.
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
#### Returns a set of offers to be shown on the Homepage
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
#### Returns the offer object with the given offer ID
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
#### Updates an offer given the id and parameters to be updated. Authorization needed. 
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
#### Creates a new offer using the parameters passed in the request body
### Parameters

| Name          | Type           |Required        | Description
| ------------- |-------------   |-------------   | -----
| body (body) | object         |  x              | Offer body that should be created <br> ```{```<br>&nbsp;&nbsp;&nbsp;```"session": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "session_id": "hoazuebq98zb", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "user_id": "1" ```<br>&nbsp;&nbsp;&nbsp;```}, ```<br>&nbsp;&nbsp;&nbsp;```"offer": {```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "title": "New offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "description": "This is a new offer", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "price": 12.50, ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "category": { ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"category_id": 1```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```},```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;``` "blocked_dates": [```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```{ ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"from_date": "2021-04-23T00:00:00.000Z", ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"to_date": "2021-04-23T00:00:00.000Z" ```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```}```<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```]```<br>&nbsp;&nbsp;&nbsp;```}```<br>``` }```                        

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
#### Accepts up to ten files to upload images
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
#### Deletes an offer by id. Authorization needed.
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
#### Books offer for a specified time frame. Authorization needed.
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
#### Rate an offer. Authorization needed. 
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