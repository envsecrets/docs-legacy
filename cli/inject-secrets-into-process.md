---
description: >-
  Inject secrets into your current shell and natively access them in your
  processes.
---

# Inject Secrets Into Process

```sh
envsecrets run -- [YOUR COMMAND]
```

## Example

Create a simple Golang script which is supposed to access and print the value of a specific secret in our environment.

```go
package main

import (
	"fmt"
	"os"
)

const variable = "FIRST"

func main() {
	fmt.Println("Value of", variable, ":", os.Getenv(variable))
}
```

Initialize your project root for envsecrets.

```sh
envsecrets init
```

Save the secret value into your envsecrets account.

```sh
envsecrets set FIRST=awesome
```

Now run the Go script.

```sh
envsecrets run -- go run main.go
```

This should produce the following output.

```
Value of FIRST: awesome
```

Enjoy!
