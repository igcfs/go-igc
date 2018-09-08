# goigc 

[![Build Status](https://api.travis-ci.org/marni/goigc.svg?branch=master)](http://travis-ci.org/marni/goigc) 
[![Coverage Status](https://coveralls.io/repos/github/marni/goigc/badge.svg?branch=master)](https://coveralls.io/github/marni/goigc?branch=master) 
[![GoDoc](https://godoc.org/github.com/marni/goigc?status.png)](https://godoc.org/github.com/marni/goigc) [![Go 
Report Card](https://goreportcard.com/badge/github.com/marni/goigc)](https://goreportcard.com/report/github.com/marni/goigc)
![Project Status](http://img.shields.io/badge/status-alpha-red.svg)

Go library for processing and manipulating [IGC](http://www.fai.org/component/phocadownload/category/?download=5745:igc-flight-recorder-specification-edition-2-with-al1-2011-5-31) 
files.

Forked from original project by [Ricardo Rocha](https://github.com/rochaporto) 
[https://github.com/ezgliding/goigc](https://github.com/ezgliding/goigc)

## Current version

**v0.1.0**

**Note**: the library status is *alpha*. The API is subject to 
change. No backwards compatibility should be assumed. Use at your own risk.

First stable release will be v1.0.0.

## Usage

```
package main

import (
	"fmt"

	"github.com/marni/goigc"
)

func main() {
    s := "http://skypolaris.org/wp-content/uploads/IGS%20Files/Madrid%20to%20Jerez.igc"
    track, err := igc.ParseLocation(s)
    if err != nil {
        fmt.Errorf("Problem reading the track", err)
    }

    fmt.Printf("Pilot: %s, gliderType: %s, date: %s", 
        track.Pilot, track.GliderType, track.Date.String())
}
```

## Testing

Tests rely on the golden files. To update the golden files, run the tests with the `-update` flag:
```
go test -update .
```

## Documentation

    $ godoc github.com/marni/goigc

