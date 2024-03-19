# 3040Crypto API

## API Description
3040Crypto API is designed to manage and facilitate crypto currency management. Allowing the user to access an account, and receive their currency specific balance.

## List of endpoints with parameters
login -> username, password
get balance -> wallet, session cookie

## Description of resources - formatted as JSON

```JSON
{
  "user": {
    "id": "ID",
    "username": "username",
    "password": "password"
  },
{
  "wallet"{
    "wallet id": "wallet ID",
    "owner id": "owner ID",
    "balance": "balance",
    "currency": "currency" 
  }
}
```

## Sample request with sample response

### Sample Request

```http
GET /api/wallets HTTP/1.1
Content-Type: application/json
```

### Sample Response
