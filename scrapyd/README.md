### Twisted版本说明
Scrapyd需要依赖Twisted-18.9.0，不要使用最新版本，否则后续使用会报错：`builtins.AttributeError: 'int' object has no attribute 'splitlines'`，以后最新版本也许会修复，暂时先用老版本。

### 启动容器
```bash
$ docker run --name scrapyd -d -p 6800:6800 uplemon/scrapyd:1.0
```
