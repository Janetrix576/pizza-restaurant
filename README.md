# pizza-restaurant

A simple pizza restaurant application.

## Installation

  
     bash
git clone https://github.com/your-username/pizza-restaurant.git
cd pizza-restaurant
pipenv install
pipenv shell
``` # Run database migrations
flask seed all        # Seed the database with initial data
flask run             # Start the Flask development server
```

## Running the Application

```bash
flask db upgrade      
flask seed all        
flask run             
```

## Database Migration & Seeding

- **Migrate:**  
  Run `flask db upgrade` to apply migrations.
- **Seed:**  
  Run `flask seed all` to populate the database with sample data.

## Route Summary

| Method | Endpoint                | Description                  |
|--------|-------------------------|------------------------------|
| GET    | /pizzas                 | List all pizzas              |
| GET    | /restaurants            | List all restaurants         |
| GET    | /restaurants/&lt;id&gt; | Get restaurant by ID         |
| POST   | /restaurant_pizzas      | Add pizza to a restaurant    |

## Example Requests & Responses

### List all pizzas

**Request:**  
`GET /pizzas`

**Response:**
```json
[
  {
    "id": 1,
    "name": "Margherita",
    "ingredients": "Tomato, Mozzarella, Basil"
  }
]
```

### Get restaurant by ID

**Request:**  
`GET /restaurants/1`

**Response:**
```json
{
  "id": 1,
  "name": "Pizza Palace",
  "address": "123 Main St",
  "pizzas": [
    {
      "id": 1,
      "name": "Margherita",
      "ingredients": "Tomato, Mozzarella, Basil"
    }
  ]
}
```

### Add pizza to a restaurant

**Request:**  
`POST /restaurant_pizzas`

**Body:**
```json
{
  "price": 12,
  "pizza_id": 1,
  "restaurant_id": 1
}
```

**Response:**
```json
{
  "id": 1,
  "pizza_id": 1,
  "restaurant_id": 1,
  "price": 12
}
```

## Validation Rules

- `price` must be an integer between 1 and 30.
- `pizza_id` and `restaurant_id` must reference existing records.
- All fields are required for POST requests.

## Using Postman

1. Import the API endpoints into Postman.
2. Set the request type (GET/POST) and URL.
3. For POST requests, set the body to `raw` and select `JSON`.
4. Send requests and view responses.

