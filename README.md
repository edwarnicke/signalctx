```go
ctx := signalctx.WithSignals(parentCtx)
```

creates a ctx that will be cancelled when the process receives

```go
os.Interrupt,
syscall.SIGHUP,
syscall.SIGTERM,
syscall.SIGQUIT,
```

Alternately, the signals upon which the ctx should be cancelled can be specified:

```go
ctx := signalctx.WithSignals(parentCtx,os.Interrupt, syscall.SIGTERM)
```
