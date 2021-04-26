# 【OCOE筆記】Unity - 各平台檔案路徑\(收集整理中\)

## **Application.dataPath** **建議視窗開發中用的路徑：**

windows:  /Assets

IPone: Application/???/Name.app/Data

Android: /data/app/Name.apk

## **Application.persistentDataPath** **Contains the path to a persistent data directory \(Read Only\).** **平台中的公開目錄，文件持久性的保存不會因為應用程式更新或升級而刪除**

windows:  C:/Users/xxxx/AppData/LocalLow/CompanyName/ProductName

IPone: Application/???/Documents

Android: /data/data/Name/files

## **Application.streamingAssetsPath** **專案目錄下面的 Assets/StreamingAssets**

windows:   /Assets/StreamingAssets

IPone: Application/???/Name.app/Data/Raw

Android: jar:file:///data/app/Name.apk/!/assets

## **Application.temporaryCachePath** **Contains the path to a temporary data / cache directory \(Read Only\).** **平台的快取儲存路徑**

windows: C:/Users/xxxx/AppData/Local/Temp/CompanyName/ProductName

IPone: Application/???/Library/Caches

Android:  /data/data/Name/cache

