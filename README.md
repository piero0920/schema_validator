# jsonvalidator for deno

Json Validator - validates a json object against defined schema.

## Docs

- API Documentation: https://vasuvanka.github.io/json-validator

## Example

```ts
import { validate } from "https://deno.land/x/jsonvalidator/mod.ts";
const bodySchema = {
  name: {
    type: String,
  },
  phone: { type: Number },
  isLoggedIn: { type: Boolean },
  address: {
    line: {
      add: [{ type: Number }],
    },
    street: { type: String },
    city: { type: String },
    pincode: { type: Number },
  },
  list: [{ type: String }],
};

const body = {
  name: "Hello",
  phone: 88010000000,
  address: {
    line: {
      add: [1],
    },
    street: "streetlk111",
    city: "some city",
    pincode: 453672,
  },
  isLoggedIn: false,
  list: ["hello", "world"],
};
const error = validate(body, bodySchema, { allowUnknown: true });
console.log(error);

const err = validate(body, bodySchema, { allowUnknown: false });
console.log(err);
```

## LICENCE

MIT

## Free software,hell ya.
