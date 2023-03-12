# UUID

[![GoDoc](https://godoc.org/github.com/pkg-id/uuid?status.svg)](https://godoc.org/github.com/pkg-id/uuid)
[![Go Report Card](https://goreportcard.com/badge/github.com/pkg-id/uuid)](https://goreportcard.com/report/github.com/pkg-id/uuid)

UUID is a 128 bit (16 byte) Universal Unique Identifier as defined in RFC 4122.

## Installation

```bash
go get github.com/pkg-id/uuid
```

## Usage

```go
package main

import "github.com/pkg-id/uuid"

func main() {
	v4 := uuid.NewV4Generator(uuid.SecureReader)

	uid, err := v4.NewUUID()
	if err != nil {
		panic(err)
	}

	println(uid.String())
}
```

or use StaticReader for testing purposes:

```go
package main

import "github.com/pkg-id/uuid"

func main() {
    v4 := uuid.NewV4Generator(uuid.StaticReader)

    uid, err := v4.NewUUID()
    if err != nil {
        panic(err)
    }

    println(uid.String() == uuid.StaticUUID) // true
}
```

## License

MIT License. See [LICENSE](LICENSE) for details.