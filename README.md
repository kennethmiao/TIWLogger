# 接口调用

1. 初始化
全局初始化一次即可

iOS/Mac/Windows
```
TIWLOG_INIT()
```
Android
```
TIWLogger.INIT(Context context)
```

2. 配置
每次更换用户配置一次

iOS/Mac/Windows
```
TIWLOG_CONFIG(config)
```
Android
```
TIWLogger.CONFIG(TIWLoggerConfig config)
```

TIWLoggerConfig

| 字段名 | 默认值 | 类型  | 说明 |
| --- | --- | --- | --- | --- |
| nativeSdkVersion | - | string |  |
| webSdkVersion | - | string |  |
| business | - | string | 白板为 tiw |
| enterId | - | string |  |
| sdkAppId | - | uint32 |  |
| roomId | - | uinit32 |  |
| userId | - | string |  |
| fileDir | - | string | 文件路径 |

3. 设置会话

3.1 获取 SessionId 和 GlobalRandom（必须在 CONFIG 之后获取）

iOS/Mac/Windows
```
TIWLOG_SESSIONID()
TIWLOG_GLOBALRANDOM()
```

Android
```
TIWLogger.SESSIONID()
TIWLogger.GLOBALRANDOM()
```

3.2 设置到 Web 端
在初始化白板时，将 SessionId 和 GlobalRandom 设置到 Web 端，对应初始化参数为
`sessionId` 和 `globalRandom`

4. 日志和上报

日志

iOS/Mac/Windows
```
TIWDLOG(module, format, ...)
TIWILOG(module, format, ...)
TIWWLOG(module, format, ...)
TIWELOG(module, format, ...)
TIWFLOG(module, format, ...)
```

Android
```
TIWLogger.DLOG(String tag, String content)
TIWLogger.ILOG(String tag, String content)
TIWLogger.WLOG(String tag, String content)
TIWLogger.ELOG(String tag, String content)
TIWLogger.FLOG(String tag, String content)
```

上报
iOS/Mac/Windows

```
//普通上报
TIWREPORT(level, action, parameter, ext, code, desc, stack)
//耗时上报
TIWREPORT_STAET(label)
......
TIWREPORT_ENDED(label, level, action, parameter, ext, code, desc, stack)
```

Android
```
//普通上报
TIWLogger.REPORT(TIWReportLevel level, String action, String parameter, String ext, int code, String desc, String stack)
//耗时上报
TIWLogger.REPORT_STAET(String label)
......
TIWLogger,REPORT_ENDED(String label, TIWReportLevel level, String action, String parameter, String ext, int code, String desc, String stack)
```

5. 反初始化

iOS/Mac/Windows
```
TIWLOG_UNINIT()
```
Android
```
TIWLogger.UNINIT()
```
