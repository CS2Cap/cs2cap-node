# CS2Cap Node SDK

Typed TypeScript/Node client for the [CS2Cap](https://cs2cap.com) market-data API — CS2 item
prices, buy orders, sales history, and analytics across dozens of providers.

[![npm](https://img.shields.io/npm/v/cs2cap)](https://www.npmjs.com/package/cs2cap)

## Install

```bash
npm install cs2cap
```

## Quickstart

Set your API key in the environment. You can generate one from the Account page after
verifying your email address at [cs2cap.com](https://cs2cap.com).

```bash
export CS2C_API_KEY="sk_your_key_here"
```

Verify the install with a small catalog request:

```typescript
import { Configuration, ItemsApi } from "cs2cap";

const accessToken = process.env.CS2C_API_KEY;

if (!accessToken) {
  throw new Error("Set CS2C_API_KEY before running this example.");
}

const api = new ItemsApi(new Configuration({ accessToken }));
const response = await api.listItems({ q: "AK-47", rarityName: "Covert", limit: 5 });

console.log(response);
```

## Documentation

Full endpoint reference, guides, and tier details are at
[docs.cs2cap.com](https://docs.cs2cap.com). See the
[changelog](https://docs.cs2cap.com/changelog) for API and SDK updates.

## About this package

This SDK is generated from the public OpenAPI spec (`openapi.json`, included in this repo).
If you hit a bug in the generated client, please open an issue or PR on this repo — fixes are
applied in the generator pipeline rather than as hand-patches to the published package.
