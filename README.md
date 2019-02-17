Ported from https://github.com/sindresorhus/camelcase

# camelcase

![DenoLib](https://denolib.com/badge?scope=denolib&repo=camelcase)
[![Build Status](https://img.shields.io/travis/denolib/camelcase.svg?style=flat-square)](https://travis-ci.org/denolib/camelcase)

> Convert a dash/dot/underscore/space separated string to camelCase or PascalCase: `foo-bar` → `fooBar`

## Usage

```ts
import { camelCase } from "https://denolib.com/denolib/camelcase/mod.ts";

camelCase("foo-bar");
//=> "fooBar"

camelCase("foo_bar");
//=> "fooBar"

camelCase("Foo-Bar");
//=> "fooBar"

camelCase("Foo-Bar", { pascalCase: true });
//=> "FooBar"

camelCase("--foo.bar", { pascalCase: false });
//=> "fooBar"

camelCase("foo bar");
//=> "fooBar"

console.log(process.argv[3]);
//=> "--foo-bar"
camelCase(process.argv[3]);
//=> "fooBar"

camelCase(["foo", "bar"]);
//=> "fooBar"

camelCase(["__foo__", "--bar"], { pascalCase: true });
//=> "FooBar"
```

## API

### camelCase(input, [options])

#### input

Type: `string` `string[]`

String to convert to camel case.

#### options

Type: `Object`

##### pascalCase

Type: `boolean`<br>
Default: `false`

Uppercase the first character: `foo-bar` → `FooBar`
