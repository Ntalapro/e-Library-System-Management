# e-Library-Management-System
Library Management System. Tech Stack -> Angular, SpringBoot and PostgreSQL 


Getting Started

## Backend

--coming--
-------------------------------------------------------------------------------------------------------------------------------------


## Frontend
--coming--
-------------------------------------------------------------------------------------------------------------------------------------

## API Reference (this is the initial, it'll expand as we grow this app)

Getting Started
Base URL: At present this app can only be run locally and is not hosted as a base URL. The backend app is hosted at the default, http://127.0.0.1:5000/, which is set as a proxy in the frontend configuration.
Authentication: This version of the application does not require authentication or API keys.

Error Handling
Errors are returned as JSON objects in the following format:
```json
{
    "success": False, 
    "error": 400,
    "message": "bad request"
}
```
The API will return three error types when requests fail(we gonna add more if needd):

400: Bad Request
404: Resource Not Found
422: Not Processable
500: Internal Server Error

ENDPOINTS 

`GET '/books'`

- Fetches a dictionary of books in which the keys are the ids
- Request Arguments: None
- Returns: An object with all the books.

```json
 {
   "books": [
    {
      "id": 1,
      "title": "Madagascar",
      "author": "The Penguin",
      "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
      "quantity": 2
      "description_id":1
    },
    {
      "id": 2,
      "title": "Madagascar",
      "author": "The Penguin",
      "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
      "quantity": 2
      "description_id":1
    }
   ]
}
```

---
`GET '/books/${id}'`

- Fetches book by id
- Request Arguments: `id` - integer
- Returns: An object with the book requested 

```json
   {
    "book":{
          "id": 1,
          "title": "Madagascar",
          "author": "The Penguin",
          "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
          "quantity": 2
          "description_id":1
       }
```
---


`GET '/books/description/${id}'`

- Fetches book by id
- Request Arguments: `id` - integer
- Returns: An object with the book requested 

```json
   {
    "book":{
          "id": 1,
          "title": "Madagascar",
          "author": "The Penguin",
          "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
          "quantity": 2
          "description_id":1
       },
    "summary":{
          "id": 1,
          "description": "Madagascar, officially the Republic of Madagascar, is an island country lying off the southeastern coast of Africa. ",
          "summary_of_the_book": "In The Power of Moments, Chip and Dan Heath explain that when people assess an experience, such as an experience with a brand, they tend to rate the                                     experience based on the ending. In The Little Book of Yes, by contrast, Noah Goldstein discusses endings in the context of persuasion.By summarizing                                    an idea, in my own words, and then looking at that idea through the lens of another context, I was able to understand it on a deeper, more                                               applicable layer. 
                                    Granted, for ideas covered, again and again, there’s a risk of moving too far from the source. (Think of all the instances of “research shows that”                                     with no reference.) 
                                    But for principle-based ideas (e.g., the trichotomy of control), connecting “knowledge trees,” as author James Clear calls them, helps you                                              internalize and remember what you read."
        }
    }
```
---

`DELETE '/books/${id}'`

- Deletes a specified book using the id of the question
- Request Arguments: `id` - integer
- Returns: Does not need to return anything besides the appropriate HTTP status code. Optionally can return the id of the question. 

---

`POST '/books'`

- Sends a post request in order to get the next question
- Request Body:

```json
{
      "title": "Madagascar",
      "author": "The Penguin",
      "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
      "quantity": 2
      "description_id":1
}
```

- Returns: Does not return any new data
---

---

`POST '/books/'`

- Sends a post request in order to search for a specific book by title
- Request Body:

```json
{
  "searchTitle": "this is the title the user is looking for"
}
```

- Returns: any array of bookss, a number of totalBooks that met the search title

```json
{
  "books": [
    {
      "id": 1,
      "title": "Madagascar",
      "author": "The Penguin",
      "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
      "quantity": 2
      "description_id":1
    },
    {
      "id": 2,
      "title": "Madagascar",
      "author": "The Penguin",
      "imgaddress": "https://upload.wikimedia.org/wikipedia/en/thumb/e/e2/IMG_Academy_Logo.svg/640px-IMG_Academy_Logo.svg.png",
      "quantity": 2
      "description_id":1
    }
   ],
  "totalBooks": 2,
}
```
-----------


Deployment N/A

Authors
Tshepiso Ncosane & Thabiso Hlatshwayo & Zwelly Sithole

Acknowledgements
The awesome Team
