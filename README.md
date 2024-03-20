# 3040Crypto API

## API Description

3040Crypto API is designed to manage and facilitate crypto currency management. Allowing the user to access an account, and receive their currency specific balance.

## List of endpoints with parameters

### Login

- Endpoint: `/login?username=sample&password=1234`
- Parameters:
  - `username`: User's name.
  - `password`: User's password.

### Get Wallets

- Endpoint: `/wallets`
- Parameters:
  - `user_id`: ID of the user.
- Description: Retrieves all wallets associated with the specified user.

### Get Balance

- Endpoint: `/wallet/balance`
- Parameters:
  - `wallet_id`: ID of the wallet.
- Description: Retrieves the balance of the specified wallet.

## Description of resources - formatted as JSON

```JSON
{
  "user": {
    "id": 123,
    "username": "username",
    "password": "password"
  },
{
  "wallet"{
    "wallet id": "wallet ID",
    "owner id": 123,
    "balance": "balance",
    "currency": "currency"
  }
}
```

## Sample request with sample response

### Sample Request

```http
POST /login HTTP/1.1
Content-Type: application/json

username=myusername&password=mypassword
```

### Sample Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "status": "success",
  "user_id": 123
}
```
