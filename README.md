# go-igc

[![Build Status](https://travis-ci.org/igcfs/go-igc.svg?branch=master)](http://travis-ci.org/igcfs/go-igc)
[![Coverage Status](https://coveralls.io/repos/github/igcfs/go-igc/badge.svg?branch=master)](https://coveralls.io/github/igcfs/go-igc?branch=master) 
[![GoDoc](https://godoc.org/github.com/igcfs/go-igc?status.png)](https://godoc.org/github.com/igcfs/go-igc) [![Go Report Card](https://goreportcard.com/badge/github.com/igcfs/go-igc)](https://goreportcard.com/report/github.com/igcfs/go-igc)
[![Maintainability](https://api.codeclimate.com/v1/badges/ea02bf3c04e959e3cbe5/maintainability)](https://codeclimate.com/github/marni/goigc/maintainability) 
[![Test Coverage](https://api.codeclimate.com/v1/badges/ea02bf3c04e959e3cbe5/test_coverage)](https://codeclimate.com/github/igcfs/go-igc/test_coverage)
![Project Status](http://img.shields.io/badge/status-alpha-red.svg)


Go library for processing and manipulating [IGC] files(https://www.fai.org/sites/default/files/documents/igc_fr_spec_with_al4a_2016-4-10.pdf) 
files.

Note:
This is a fork from original project by [Ricardo Rocha](https://github.com/rochaporto) 
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

	"github.com/igcfs/go-igc"
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


## Resources



## Testing

Tests rely on the golden files. To update the golden files, run the tests with the `-update` flag:
```
go test -update .
```

## Documentation

    $ godoc github.com/marni/goigc
    
* [Latest IGC technical spec](https://www.fai.org/sites/default/files/documents/igc_fr_spec_with_al4a_2016-4-10.pdf). 
The IGC file specification is provided by FAI and IGC standarization committes and 
should be used as a reference. See section A9 for the example of IGC file.
* An example IGC files can be downloaded from [XContest.org](http://xcontest.org), eg. [a short flight](https://www.xcontest.org/track.php?t=1533585909.37.igc)
* [IGC Waypoint format](https://www.fai.org/sites/default/files/documents/wpformat.pdf) (useful for fields specs)

