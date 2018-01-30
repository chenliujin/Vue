
# proxyTable

开发模式下允许访问多个 API 服务器。

```
proxyTable: {
   '/shopping':{//此处并非一定和url一致。
      target:'https://api1.example.com/shopping',
      changeOrigin:true,//允许跨域
      pathRewrite:{
        '^/shopping': ''
      }
    },
   '/login':{//此处并非一定和url一致。
      target:'https://api2.example.com/login',
      changeOrigin:true,//允许跨域
      pathRewrite:{
        '^/login': ''
      }
    }
}
```

此段代码表示，如果请求地址以/shopping开头，则自动加上target。
如：/shopping/v2/restaurant/category  等于
https://api1.example.com/shopping/v2/restaurant/category，

/login => https://api2.example.com/login
