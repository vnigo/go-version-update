# go-version-update
[![Go Report Card](https://goreportcard.com/badge/github.com/Code-Hex/go-version-update)](https://goreportcard.com/report/github.com/Code-Hex/go-version-update) [![GoDoc](https://godoc.org/github.com/Code-Hex/go-version-update?status.svg)](https://godoc.org/github.com/Code-Hex/go-version-update)  
Update the version string of your go project.  
Rewrite the value of the `const` or `var` variables matching `/version/i` to the specified version string.

# Synopsis

```go
package main

import update "github.com/Code-Hex/go-version-update"

func main() {

    // Find go files are described version variables.
    founds, err := update.GrepVersion("target_directory")
    if err != nil {
        panic(err)
    }

    // Re write value of version variables.
    for _, path := range founds {
        // Re write to "1.2.3"
        if err := update.NextVersion(os.Stdout, "1.2.3", path); err != nil {
            panic(err)
        }
    }
}
```

You can also modify the version of your project using the `goversion` command.

## goversion
```
Usage: goversion [options] 
  Options:
  -h,  --help                   print usage and exit
  -f,  --format <version>       rewrite version of code
  -d,  --dir                    target directory
```

# Installation
- Library install

        go get github.com/Code-Hex/go-version-update

- `goversion` command install

        go get github.com/Code-Hex/go-version-update/cmd/goversion

# Contribute
If you find an issue with this library, please report an issue.  
If you'd like, we welcome any contributions. Fork this library and submit a pull request.

# License
[MIT](https://github.com/Code-Hex/go-version-update/blob/master/LICENSE)
# Author
[codehex](https://twitter.com/CodeHex)
