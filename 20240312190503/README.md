# Go: Starting project

# Dependency tracking 

`Go` uses `go.mod` file to track project dependencies, it is part of the project and has to be added to the repository.
To create a `go.mod` file run `go mod init command`, this commands takes is project's module path.

To ensure integrity of dependencies go tools create `go.sum`, this file is used to store checksums of modules used in the project.

Both `go.mod` and `go.sum` should be added to the version control system.

## Module naming

Module path is used as module name and will be used as import path prefix.
Path should indicate origin of the package, if modules won't be published it can be company name or other unique name.

Module paths usually use following format

```
<prefix>/<name>
```

If module is meant to be published prefix should indicate where the module is located.
For example if module is hosted on github, module path would look something like `github.com/user-name/repo-name`.

# Hello world

In yout text editor of choice create `main.go` and put in following code.

```
package main

import "fmt"

func main() {
    fmt.Println("Hello world")
}

```

`package main` this line declares that file is part of the main package.
Packages are a method of grupping functions and data structures together and are defined by directory structure.

`import "fmt"` import fmt package that is part of Go's standard library.
Fmt package is used to format text and printing to console.

`func main()` implements main function that will print `Hello world` to console when application is run.
`main` function is called by default when main package is run.

# Useful commands

- `go run <path>` will build and run the project
- `go build <path>` will build the project
- `go install <path>` will compile and install the package

