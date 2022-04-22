# qa-tools-repo

<a href="https://emoji.gg/emoji/5498_catJAM"><img src="https://emoji.gg/assets/emoji/5498_catJAM.gif" width="64px" height="64px" alt="catJAM"></a>*Repository to my QA tools, snippets and demo projects.* <a href="https://emoji.gg/emoji/1430_catJAMReversed"><img src="https://emoji.gg/assets/emoji/1430_catJAMReversed.gif" width="64px" height="64px" alt="catJAMReversed"></a>


# Load Test Using Artillery.io + Faker.js

## Example

Command to run test with a result.json for test evidence:

```sh
artillery run -o results.json load-test-faker.yml
```

Converting results.json to html

```sh
artillery report -o results.html results.json
```

## Install

Artillery

```sh
npm install -g artillery
```

Faker Plugin

```sh

$ npm install -g artillery-plugin-faker

```

## Usage

Add the plugin to your loadtest configuration:

```yaml
config:

plugins:

faker:

locale: en
```

### Options

- `locale` (default: `en`) sets the locale of _faker.js_.

### Example

Using a string prefixed with `$faker.` as variable value will result in a random variable value returned by the indicated _faker.js_ function.

```yaml
config:

target: 'http://localhost:3000'

phases:
  - duration: 10

arrivalRate: 1

plugins:

faker:

locale: en

variables:

firstName: '$faker.name.firstName'

scenarios:
  - flow:

  - log: 'Making request with query: {{ firstName }}'

  - get:

url: '/search?q={{ firstName }}'
```

For a complete list of available _faker.js_ functions, have a look at the [faker.js documentation](https://github.com/faker-js/faker#api-methods). Please note that no parameters can be passed to the _faker.js_ functions at this time.

_Have a look at the `example.yml` file for a fully working example._
