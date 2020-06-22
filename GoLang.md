When I worked for Cepave, I developed a simple framework(base on [Gin framework](https://github.com/gin-gonic/gin), as Go language) to ease
authoring of web service.

The framework let you bind web parameters by [Struct tag](https://golang.org/ref/spec#Struct_types):

```go
import (
  gmvc "github.com/Cepave/open-falcon-backend/common/gin/mvc"
)

mvcBuilder := gmvc.NewMvcBuilder(gmvc.NewDefaultMvcConfig())

engine.GET(
  "/your_get_service",
  mvcBuilder.BuildHandler(func(
    v *struct {
      Name string `mvc:"query[name]"`
      Age int16 `mvc:"query[age]"`
      SessionId string `mvc:"header[owl-session-id]"`
    }
  ) string {
      // Access HTTP parameters by v.Name, v.SessionId ...

      return "OK"
  }),
)
```

While you are doing type conversion and validation, this framework can "inject" services for you:

```go
engine.GET(
  "/your_get_service",
  mvcBuilder.BuildHandler(func(
		validator *validator.Validate,
		convSrv otype.ConversionService,
    v *struct {
      Name string `mvc:"query[name]"`
      Age int16 `mvc:"query[age]"`
      SessionId string `mvc:"header[owl-session-id]"`
    }
  ) string {
      // Access HTTP parameters by v.Name, v.SessionId ...

      return "OK"
  }),
)
```

- The [specification](doc/gin-mvc.pdf) of this framework.
- The [source code](https://github.com/fwtpe/owl-backend/tree/master/common/gin/mvc) of this framework.
