## Middleware information

This folder contains a middleware which enables net/http/pprof.


## Install

```sh
$ go get -u github.com/iris-contrib/middleware.v5/pprof
```

## Usage

```go
package main

import (
	"github.com/iris-contrib/middleware/pprof"
	"gopkg.in/kataras/iris.v5"
)

func main() {
  
	iris.Get("/", func(ctx *iris.Context) {
		ctx.HTML(iris.StatusOK, "<h1> Please click <a href='/debug/pprof'>here</a>")
	})

	iris.Get("/debug/pprof/*action", pprof.New())

	iris.Listen(":8080")
}

```
