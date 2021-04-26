---
description: 使用Android SDK內的tools 去完成Android系統的unity App Debug Log
---

# 【OCOE筆記】Unity Android 實機運行Log監測

## 1.下載/安裝 android studio 

## 2.使用命令提示字元

set path to ..Android\SDK\platform-tools

EX:  `cd C:\Users\AppData\Local\Android\Sdk\platform-tools`

## 3.透過adb 下參數

```
adb logcat -s Unity ActivityManager PackageManager dalvikvm DEBUG
```



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------雖然只是倉庫筆記，但如果有錯或是有更佳的資訊 歡迎聯繫我~

