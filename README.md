# 3040Crypto API

## API Description

3040Crypto's API is designed to help user's securely manage their cryptocurrency. 
By providing the user with security through the use of user accounts. 
Thus, in order to view or interact with their cryptocurrency they will need to login to a 3040Crypto account. 
Then once logged in they will be able to view all of their wallets and the balance of each individual wallet.

## List of endpoints with parameters

### Login

- Endpoint: POST `/login?username=user&password=pass`
- Parameters:
  - `username`: User's username.
  - `password`: User's password.
- Description: This endpoint logins a user through a post request by creating a new user session. 

### Get Wallets

- Endpoint: GET `/wallets/{user_id}`
- Parameters:
  - `user_id`: ID of the user.
- Description: This endpoint retrieves all wallets associated with the specified user through a get request.

### Get Balance

- Endpoint: GET `/balance/{wallet_id}`
- Parameters:
  - `wallet_id`: ID of the wallet.
- Description: This endpoint retrieves the balance of a specified wallet through a get request.

## Description of resources - formatted as JSON

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
    "currency": "currency"
  },
  "serverSession": {
    "session_id": 12,
    "user_id": 123,
    "valid": true
  },
  "userSession": {
    "user_id": 123,
    "valid": true
  },
  "userWallets": [1, 1234, 71, 21],
  "walletBalance": {
    "balance": "balance",
    "currency": "currency"
  }
}
```

In the above JSON the first three objects which are user, wallet and serverSession represent how the data is stored on the server's side. 
While the last three objects which are userSession, userWallets and walletBalance represent the objects returned by the http responses to the three API requests outlined above. 
Where userSession is returned by the login endpoint, userWallets is returned by the get wallets endpoint and the walletBalance object is returned by the get balance endpoint.

## Sample request with sample response

### Sample Request

```http
POST /login?username=user&password=pass HTTP/1.1
Content-Type: application/json


```

### Sample Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Set-Cookie: sessionId="12"

{
  "userSession": {
    "user_id": 123,
    "valid": true
  }
}
```
