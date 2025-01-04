# v-lambda

Libraries to help V developers develop AWS Lambda functions.

## Installation

Add `v-lambda` to your `v.mod`.

```v
Module {
	// ...
	dependencies: [
		'https://github.com/koki-develop/v-lambda.git@0.1.0'
	]
}
```

And run `v install`.

## Usage

```v
module main

import lambda
import json

struct Input {
	// ...
}

fn main() {
	lambda.start(handler)!
}

fn handler(ctx lambda.Context, event string) !string {
	input := json.decode(Input, event)!

	return json.encode({
		'success': true
	})
}
```

For actual usage examples, please refer to [koki-develop/vlang-aws-lambda-example](https://github.com/koki-develop/vlang-aws-lambda-example).

## LICENSE

[MIT](./LICENSE)
