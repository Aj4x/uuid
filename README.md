# Go UUID

A Go package for generating and parsing RFC 4122 compliant UUIDs (Universally Unique Identifiers).

## Features

- Generate RFC 4122 version 4 UUIDs using cryptographically secure random numbers
- Parse UUID strings into UUID objects
- Convert UUIDs to standard string representation
- Comprehensive error handling
- Zero dependencies outside of Go standard library

## Installation

```bash
go get github.com/Aj4x/uuid
```

Requires Go 1.23.0 or later.

## Usage

### Import the package

```go
import "github.com/Aj4x/uuid"
```

### Generate a new UUID

```go
// Generate a new random UUID
id, err := uuid.NewUUID()
if err != nil {
    // Handle error
    log.Fatal(err)
}

// Convert UUID to string
fmt.Println(id.String()) // e.g., "331495aa-cdef-4042-8123-aabbccddeeff"
```

### Parse a UUID string

```go
// Parse a UUID from string
id, err := uuid.ParseUUID("331495aa-cdef-4042-8123-aabbccddeeff")
if err != nil {
    // Handle error
    log.Fatal(err)
}

// Use the UUID
fmt.Println(id)
```

### Error Handling

The package provides specific error types for different validation failures:

```go
// Check for specific error types
id, err := uuid.ParseUUID("invalid-uuid")
if errors.Is(err, uuid.ErrInvalidUUIDFormat) {
    fmt.Println("The UUID format is invalid")
}
```

Available error types:
- `ErrFailedToGenerateUUID`: Failed to generate a UUID
- `ErrInvalidUUIDFormat`: Invalid UUID format
- `ErrInvalidUUIDLength`: Invalid UUID length
- `ErrInvalidUUIDHex`: Invalid UUID hex character
- `ErrFailedToDecodeUUID`: Failed to decode UUID

## License

MIT License

Copyright (c) 2025 Aj4x