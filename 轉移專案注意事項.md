# 【OCOE筆記】Unity 轉移專案注意事項\(非破壞\)

### 1.啟用可見的元文件 <a id="visible_meta_files"></a>

 在Unity中，每個資產都有隱藏的.meta數據，這些元數據用於在腳本變量，遊戲對象和資產之間建立和維護引用。這些元數據存儲在**.meta文件中**，該**文件**在導入資產時由Unity創建。

![](.gitbook/assets/image%20%282%29.png)

### 1.從項目目錄中刪除“ Library”和“ Temp”文件夾 <a id="visible_meta_files"></a>

 Library與Temp在開啟專案時都可以被重新被Unity 生成。

![](.gitbook/assets/image%20%283%29.png)

### 1.將文件夾壓縮為Zip文件 <a id="visible_meta_files"></a>

 壓縮後索引項目變少 容量變少 ~

