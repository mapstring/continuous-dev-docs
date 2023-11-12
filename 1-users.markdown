---
layout: page
title: 1 - Users
permalink: /users/
has_toc: true
---

```
endpoint: https://api.continuous.sh/users/api
```

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


### POST /users

Creates a new user or returns 401.

#### Request
```json
{
	"email": "email@domain.tld",
	"password": "password",
	"password_confirm": "confirmation",
	"fullname": "User name"
}
```

#### Response
```json
{
  "id": "1111-2222-4444-5555-6666",
  "email": "email@domain.tld"
}
```

### GET /users/:id

Returns information about a user or 404 response code if no user found.

#### Params

```
id: user UUID
```

#### Request

nil

#### Response

```json
{
  "id": "1111-2222-4444-5555-6666",
  "email": "email@domain.tld",
  "activated": false|true
}
```

`activated` is related to the user account activation.

### GET /users/:id/activate

Activates a user account.
Returns 404 if no user found.

#### Params

```
id: user account UUID
```

#### Request

nil

#### Response

```json
{
  "id": "1111-2222-4444-5555-6666",
  "activated": false|true
}
```

### POST /sessions

Creates a new session to sign in the user. Returns a JWT token.

#### Request

```json
{
  "email": "email@domain.tld",
  "password": "user-password"
}
```

#### Response

```json
{
  "token": "...."
}
```
