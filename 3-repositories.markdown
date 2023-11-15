---
layout: page
title: 2 - Repositories
permalink: /repositories/
has_toc: true
---

```
endpoint: https://api.continuous.sh/repositories
```

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


*X-Org-Authorization* is a token provided by the `organizations-api` on `/organizations` endpoint.

### POST /repositories

Creates a repository in the selected organization.

#### Request

```
Authorization: X-Org-Authorization
```

```json
{
	"organization_id": "1111-2222-3333-4444",
	"name": "repository-name",
	"team": "team-name",
	"url": "git@github.com:team-name/repository-name.git"
}
```

* Taking the example of a Git repository available at `git@github.com:organization/repository.git`, `name = repository` and `team = organization`.

#### Response
```json
{
	"name": "repository-name",
	"team": "team-name",
	"url": "git@github.com:team-name/repository-name.git",
	"organization_id": "1111-2222-3333-4444",
	"id": "2222-3333-4444-5555"
}
```
