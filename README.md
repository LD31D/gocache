# gocache

A **lightweight in-memory key-value cache** for Go. \
Designed for simplicity, minimalism, and zero external dependencies.


## 🚀 Installation

```shell
go get github.com/LD31D/gocache
```

## 📦 Usage

```go
package main

import (
	"fmt"

	"github.com/LD31D/gocache"
)

func main() {
	// Create a new cache (returns a value, not a pointer)
	cache := gocache.New()

	// Store a value in the cache
	cache.Set("userId", 42)

	// Retrieve the value
	fmt.Println(cache.Get("userId")) // Output: 42

	// Delete the value
	cache.Delete("userId")

	// Attempt to retrieve the deleted value (will return nil)
	fmt.Println(cache.Get("userId")) // Output: <nil>
}
```

## 🛠 API Reference

### `New() Cache`
Creates and returns a **new cache instance**.

> ⚠️ **Important:** `New()` returns a **value**, not a pointer.  
> Copying the `Cache` value will create an independent copy with its own internal map.

---

### `Set(key string, value any)`
Stores a value in the cache under the specified key.  
If the key already exists, its value will be overwritten.

---

### `Get(key string) any`
Retrieves the value associated with the given key.  
Returns `nil` if the key does not exist.

---

### `Delete(key string)`
Removes the key and its associated value from the cache.



## 📄 License

MIT – free for personal and commercial use.
