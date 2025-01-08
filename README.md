# v-lambda

Libraries to help V developers develop AWS Lambda functions.

## Installation

```console
$ v install koki-develop.lambda
```

## Usage

```v
module main

import koki_develop.lambda
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
