# 3040Crypto API

## API Description

This API is designed to help users view their 3040Crypto wallets, their wallets contents and transaction history. 
It accomplishes this through the use of three simple endpoints. 

## List of endpoints with parameters

### Get Wallets

- Endpoint: GET `/wallets/{username}`
- Parameters:
  - `username`: a user's 3040Crypto username.
- Description: This endpoint retrieves a list of wallet ID's that are associated with a username by making a get request.

### Get Balance

- Endpoint: GET `/balance/{wallet_id}`
- Parameters:
  - `wallet_id`: ID of the desired wallet.
- Description: This endpoint retrieves the balance of a specified wallet through a get request.

### Get Transactions

- Endpoint: GET `/transactions/{wallet_id}`
- Parameters:
  - `wallet_id`: ID of the desired wallet.
- Description: This endpoint retrieves all transactions associated with the specified wallet through a get request.

## Description of resources - formatted as JSON

In the following description of resources the first three objects which are user, wallet and transaction represent how users, wallets and transactions would be stored on 3040Cryptos servers. 

While the last three objects which are userWallets, walletBalance and userTransactions represent the objects returned by the http responses to the three API requests outlined above. 
Where userTransactions is returned by get transactions, userWallets is returned by get wallets and walletBalance is returned by get balance.


```JSON
{
  "user": {
    "user_id": 123,
    "username": "user",
    "password": "pass",
    "wallets": [1, 1234, 71, 21]
  },
  "wallet": {
    "wallet_id": 1234,
    "user_id": 123,
    "balance": "balance",
    "currency": "currency",
    "transactions": [12345]
  },
  "transaction": {
    "transaction_id": 12345,
    "wallet_id": 1234,
    "amount" 125.50,
    "source": 1234,
    "destination": 71
  }
  "userWallets": [1, 1234, 71, 21],
  "walletBalance": {
    "balance": "balance",
    "currency": "currency"
  },
  "userTransactions": [{
    "transaction_id": 12345,
    "wallet_id": 1234,
    "amount" 125.50,
    "source": 1234,
    "destination": 71
  }]
}
```

## Sample request with sample response

### Sample Request

```http
GET /wallets/123 HTTP/1.1
Content-Type: application/json


```

### Sample Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{"userWallets": [1, 1234, 71, 21]}
```
