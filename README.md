# nilQL

Library for working with encrypted data within nilDB queries and replies.

## Package Installation and Usage

The package can be installed using [pnpm](https://pnpm.io/):

```shell
pnpm install
```

The library can be imported in the usual way:

```ts
import { nilql } from "@nillion/nilql";
```

An example demonstrating use of the library is presented below:

```ts
const cluster = {"nodes": [{}, {}]};
const secretKey = await nilql.secretKey(cluster, {"sum": true});
const plaintext = BigInt(123);
const ciphertext = await nilql.encrypt(secretKey, plaintext);
const decrypted = await nilql.decrypt(secretKey, ciphertext);
console.log(plaintext, decrypted); // Should output `123n 123n`.
```

## Testing and Conventions

All unit tests are executed and their coverage measured with [vitest](https://vitest.dev/):

```shell
pnpm test
```

Style conventions are enforced using [biomejs](https://biomejs.dev/):

```shell
pnpm lint
```

Types are checked with:

```shell
pnpm typecheck
```

## Contributions

In order to contribute, open an issue or submit a pull request on the GitHub. To enforce conventions, git hooks are provided and can be setup with:

```shell
pnpm install-hooks
```

## Versioning

The version number format for this library and the changes to the library associated with version number increments conform with [Semantic Versioning 2.0.0](https://semver.org/#semantic-versioning-200).
