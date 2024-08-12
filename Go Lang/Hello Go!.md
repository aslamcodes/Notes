# Icebreaker
```go
package main
// Package is a way to group functions

import "fmt"
// This is a pacakage that contains functions for formatting code.
// And it is one of the standard library packages.
import "rsc.io/quote"
// This is a package that is not part of the standard library.
// I installed by just writing "import "rsc.io/quote" and then running "go mod tidy" in the terminal.

func main() {
	fmt.Println("Hello")
    fmt.Println(quote.Go())
}
// run this with go run . / go run hello.go
```
# Calling functions within local modules
```
- greetings/
	- go.mod
	- greeting.go
- hello/
	- go.mod
	- hello.go
```

```go 
// greeting.go
package greetings

import "fmt"

// Function names start with a capital letter, they are exported
func Hello(name string) string {
	message := fmt.Sprintf("Hi, %v. Welcome!", name)
	return message
}
```

```go
// hello.go
package main

import (
    "fmt"
    "gomod.com/greetings"
)

func main() {
    // Get a greeting message and print it.
    message := greetings.Hello("Gladys")
    fmt.Println(message)
}
```

> [!WARNING] Shallow knowledge Alert
> - Go "tools" tries to look out for "gomod.com/greetings" to get the code for the greetings module, which is obviously a made up url. So we instructed `go` to look at '`../greetings`' with `replace` command
> - But if for real origins like `github.com/aslamcodes/todo-go` or `rsc.io/quote` which gives HTTP response, how go figures out is with `go-import` meta tag. But how it is added to the HTML page of that repo provider?? 

> [!NOTE] Modules never imported
> - [From a reddit post](https://www.reddit.com/r/golang/comments/kait2j/comment/gfecsoi/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button): Modules are never imported. Packages are imported and packages are how Go code is reused, evolves and is used. Modules are just a group of packages with the same version number
> - Modules just a way of tracking dependencies and versioning the packages. the `package.json` of node projects
> 

```text
module gomod.com/hello

go 1.22.6

replace gomod.com/greetings => ../greetings

require gomod.com/greetings v0.0.0-00010101000000-000000000000

```
Using `go mod tidy` will add the `require` 'command' into the go mod file.
