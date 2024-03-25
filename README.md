# Lenslocked

Learn to build real, production grade web applications.

## go modules

```go
go mod init github.com/yzwdroid/lenslocked
go install
lenslocked
```

## Dynamic Reloading

Dynamic reloading is basically the act of watching for changes in your code, and then automatically rebuilding and restarting your program once a change is detected.
```
go install github.com/cortesi/modd/cmd/modd@latest
# modd.conf

**/*.go {
  prep: go test @dirmods
}
# Exclude all test files of the form *_test.go
**/*.go !**/*_test.go {
  prep: go build -o lenslocked .
  daemon +sigterm: ./lenslocked
}
```

- Setting Header Values `Content-Type`

common ones: `text/html, application/json, image/png, video/mp4`

## Router
```
go get -u github.com/go-chi/chi/v5
```
The -u flag instructs get to update modules providing dependencies of packages named on the command line to use newer minor or patch releases when available.