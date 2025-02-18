---
title: Get Supported TLDs | Unstoppable Domains Developer Portal
description: This page covers the documentation for the `Get Supported TLDs` endpoint.
---

# Get Supported TLDs

```
https://resolve.unstoppabledomains.com/supported_tlds
```

This endpoint returns all the domain endings provided and supported by Unstoppable Domains.

## Request Method

* GET

## Authentication

* none

## URL Params

* none

## Query Params

* none

## Returns

An object with a `tlds` field that contains a list of domain endings supported by Unstoppable Domains.

* `tlds`: (array) An array of the domain endings supported by Unstoppable Domains.

## Example

Here is an example request to query for the domain endings supported by Unstoppable Domains:

### Request

```bash
curl --location --request GET 'https://unstoppabledomains.g.alchemy.com/supported_tlds'
```

### Response

```json
{
    "tlds": [
        "crypto",
        "coin",
        "wallet",
        "blockchain",
        "bitcoin",
        "x",
        "888",
        "nft",
        "dao",
        "zil"
    ]
}
```

<embed src="/snippets/_discord.md" />
