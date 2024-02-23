## http.ServeMux wrapper

This repository contains a custom middleware router implementation in Go. The router allows you to define middleware functions and apply them to specific routes or route prefixes.

Go version 1.22 is required

## Usage

Create a new router instance with NewRouter().

```
router := NewRouter()
```

Use middleware functions with the Use() method to apply them to all routes, or with UseWithPrefix() to apply them only to paths containing a specified prefix.

```
router.Use(SetRequestID, LogRequest)

router.GET("/", index)

router.UseWithPrefix("/hello/", SayHello)

router.GET("/hello/", index)
```


