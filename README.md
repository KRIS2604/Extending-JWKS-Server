JWKS Server Extension Project

This project implements a simple Flask-based web server that simulates a JSON Web Key Set (JWKS) endpoint and supports JWT authentication. The server generates RSA key pairs, stores them in an SQLite database, and exposes two main endpoints: `/auth` for JWT issuance and `/.well-known/jwks.json` for public key distribution.

Features

- Generates RSA private keys and stores them with expiration timestamps.
- Issues JWTs signed with valid or expired private keys.
- Exposes public keys via JWKS endpoint in JWK format.
- Uses SQLite for persistent key storage.
- Includes unit tests to validate key functionalities.

---

Endpoints

`POST /auth`

Returns a JWT token signed with a valid private key from the database.

Query Parameters:
- `expired=true` – Returns a token using an expired key (if available).

Response Example:
```json
{
  "token": "<JWT-TOKEN>"
}

+

