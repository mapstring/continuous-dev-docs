---
layout: page
title: 2 - Organizations
permalink: /organizations/
has_toc: true
---

```
endpoint: https://api.continuous.sh/organizations
```

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


### POST /organizations

Creates a new user organization in the user space.

#### Request
```
Authorization: Token
```

```json
{
	"name": "singular-organization-name"
}
```

#### Response
```json
{
	"name": "singular-organization-name"
}
```

### GET /organizations

Returns an X-Org-Authorization token containing the list of user permissions
on his organizations.

#### Headers

```
Authorization: Token
```

#### Request

nil

#### Response

```json
{
  "authorization": "...."
}
```

The emitted token given in the `authorization` element is required to perform queries on alternatives APIs, such as `repositories` or `vault` endpoints.

### GET /organizations/:id

Returns information about an organization.

#### Request

```
id: uuid of organization to fetch
```

#### Response

```json
{
	"id": "111-222-333-444-555",
	"name": "my-organization",
	"creator_id": "222-333-444-555-666",
	"privileges": [
		{
			"id": "c24dfbca-6eaa-49da-b6a1-f27fcb2af222",
			"user_id": "222-333-444-555-666",
			"permissions": 999,
			"created_at": "2023-11-13T20:49:39.66593Z"
		}
	]
}
```
