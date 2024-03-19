# 3040Crypto API

## API Description

This api is a wallet. Where you can keep and track your crypto currency. You can send money between wallets/accounts and check how much money you have.

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
