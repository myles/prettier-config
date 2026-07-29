# @mylesb/prettier-config

> Myles' shared [Prettier](https://prettier.io) configuration for (hopefully) all his projects.

A single source of truth for code formatting, so every project stays consistent without copy-pasting settings around.

## Settings

| Option          | Value   | Meaning                                            |
| --------------- | ------- | -------------------------------------------------- |
| `trailingComma` | `"all"` | Trailing commas wherever possible (incl. function args). |
| `tabWidth`      | `2`     | Two spaces per indentation level.                  |
| `singleQuote`   | `false` | Use double quotes.                                 |

Everything else falls back to [Prettier's defaults](https://prettier.io/docs/options).

## Installation

```sh
npm install --save-dev @mylesb/prettier-config prettier
```

> Requires Prettier `>=3.0.0`.

## Usage

### Reference it from `package.json`

The simplest option — point Prettier at the package by name:

```json
{
  "prettier": "@mylesb/prettier-config"
}
```

### Extend it from a config file

If you need to add or override a few options, re-export the shared config and spread it:

```js
// prettier.config.mjs
import mylesPrettierConfig from "@mylesb/prettier-config";

/** @type {import("prettier").Config} */
export default {
  ...mylesPrettierConfig,
  // your overrides here
};
```

## Formatting

Once configured, run Prettier as usual:

```sh
# Check that files are formatted
npx prettier . -c

# Format files in place
npx prettier . --write
```

## License

[MIT](./LICENSE) © [Myles Braithwaite](https://myles.garden)
