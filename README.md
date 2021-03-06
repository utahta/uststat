# Ustream live status

[![Build Status](https://travis-ci.org/utahta/ustream-live-status.svg?branch=master)](https://travis-ci.org/utahta/ustream-live-status)

Get the ustream live status.

## Installing

```
$ go get -u github.com/utahta/ustream-live-status/cmd/uststat
```

## Usage

```
$ uststat -h
Usage of uststat:
  -name string
        Specifies the ustream channel name

```
```
$ uststat -name iss-hdev-payload
live
```
```
$ uststat -name momoclotv
offline
```

## Example

```go
package main

import (
	"log"

	"github.com/utahta/ustream-live-status"
)

func main() {
	c, err := uststat.New()
	if err != nil {
		log.Fatal(err)
	}

	live, err := c.IsLive("iss-hdev-payload")
	if err != nil {
		log.Fatal(err)
	}

	log.Print(live)
}
```

## Contributing

1. Fork it ( https://github.com/utahta/uststat/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

