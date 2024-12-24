# @poppinss/object-builder

<br />

[![gh-workflow-image]][gh-workflow-url] [![npm-image]][npm-url] ![][typescript-image] [![license-image]][license-url]

## Installation

Install the package from the npm package registry.

```sh
# Npm
npm i @poppinss/object-builder

# Yarn
yarn add @poppinss/object-builder

# Pnpm
pnpm add @poppinss/object-builder
```

## Usage

The `ObjectBuilder` is a convenience class to create an object with dynamic properties. Consider the following example, where we wrap our code inside conditionals before adding the property `b` to the `startingObject`.

```ts
const startingObject = {
  a: 1
  // Add "b", if it exists
  ...(b ? { b } : {})
}

// OR
if (b) {
  startingObject.b = b
}
```

Instead of writing conditionals, you can consider using the Object builder fluent API.

```ts
import { ObjectBuilder } from '@poppinss/object-builder'
const builder = new ObjectBuilder({ a: 1 })

const plainObject = builder.add('b', b).toObject()
```

By default, only the `undefined` values are ignored. However, you can also ignore `null` values.

```ts
import { ObjectBuilder } from '@poppinss/object-builder'

const ignoreNullValues = true
const builder = new ObjectBuilder({ a: 1 }, ignoreNullValues)
```

Following are the available methods on the `ObjectBuilder` class.

```ts
builder.remove(key)
builder.has(key)
builder.get(key)
builder.add(key)

builder.toObject() // get plain object
```

## Contributing

One of the primary goals of Poppinss is to have a vibrant community of users and contributors who believes in the principles of the framework.

We encourage you to read the [contribution guide](https://github.com/poppinss/.github/blob/main/docs/CONTRIBUTING.md) before contributing to the framework.

## Code of Conduct

In order to ensure that the Poppinss community is welcoming to all, please review and abide by the [Code of Conduct](https://github.com/poppinss/.github/blob/main/docs/CODE_OF_CONDUCT.md).

## License

Poppinss object builder is open-sourced software licensed under the [MIT license](LICENSE.md).

[gh-workflow-image]: https://img.shields.io/github/actions/workflow/status/poppinss/object-builder/checks.yml?style=for-the-badge
[gh-workflow-url]: https://github.com/poppinss/object-builder/actions/workflows/checks.yml 'Github action'
[typescript-image]: https://img.shields.io/badge/Typescript-294E80.svg?style=for-the-badge&logo=typescript
[typescript-url]: "typescript"
[npm-image]: https://img.shields.io/npm/v/@poppinss/object-builder.svg?style=for-the-badge&logo=npm
[npm-url]: https://npmjs.org/package/@poppinss/object-builder 'npm'
[license-image]: https://img.shields.io/npm/l/@poppinss/object-builder?color=blueviolet&style=for-the-badge
[license-url]: LICENSE.md 'license'
