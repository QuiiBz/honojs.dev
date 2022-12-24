---
title: 'Lagon'
weight: 400
---

# Lagon

Lagon is an open source runtime and platform to run TypeScript and JavaScript Functions at the Edge. It's neither Node.js nor Deno.

Note that some middlewares don't work or are useless.

## 1. Install

First, install the Lagon CLI. Please refer to [the official documentation](https://docs.lagon.app/cli#installation).

Next, create an new project and install Hono:

```
npm init -y
npm i hono
```

## 2. Hello World

Create a new file `src/index.ts` and edit it:

```ts
// src/index.ts
import { Hono } from 'hono'
const app = new Hono()

app.get('/', (c) => c.text('Hello! Hono!'))

export const handler = app.fetch
```

## 3. Run

Run the command.

```ts
lagon dev src/index.ts
```

Then, access `http://localhost:1234` in your browser.

## Limitations

- The "Cache" middleware isn't supported yet
- The "Serve Static" middleware is useless, as Lagon serves your `public` directory by default.
