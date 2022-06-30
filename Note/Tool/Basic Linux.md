## `tar`
-   _-c_ 打包檔案
-   _-x_ 解開壓縮檔
-   _-t_ 檢視壓縮檔的內容
-   _-z_ 使用 gzip 壓縮
-   _-v_ 顯示執行過程
-   _-P_ 使用絕對路徑
-   _-f_ 指定壓縮檔的檔案名稱。此參數的後面要接檔案名稱，因此要注意參數的順序 (通常是把 f 參數寫在最後一個，或是與其它參數分開使用)

```
.tar  
打包：tar cvf FileName.tar DirName  
解包：tar xvf FileName.tar
.tar.gz  
壓縮：tar zcvf FileName.tar.gz DirName  
解壓：tar zxvf FileName.tar.gz
```