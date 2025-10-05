[![](https://github.com/TechTutoPPT/GDP-Pocket-2-Install-CasaOS/blob/main/IMG_8260.PNG)](https://youtu.be/AHhOXTfAEwo)

又來拯救舊裝置的影片, 今次的主角是GPD Pocket 2, 一部帶7寸屏細小的筆電, 雖然已是2019年的產物, 
但搭載Intel Celeron 3965Y處理器, 8GB內存和256GB SSD硬盤, 到現在要處理一般文書工作還挺適合的.
而我最喜愛它的地方除了體積細小外, 還有能以microSD啟動及耗電量非常低的優點, Windows運行高負荷工作才2x瓦, 
Linux待機只需2瓦...由於它能以microSD卡啟動, 那就能大大簡化了安裝雙系統的操作難度, 只要microSD卡刷上另一系統,
於BIOS選以microSO卡作為啟動便能達成. 今次我便透過microSD安裝MiniOS+CasaOS讓它成為一台輕便可移動的NAS.

準備材料:
GPD Pocket 2
一張建議128GB高速的microSD卡
```
MiniOS: https://minios.dev/
```
```
Rufus: https://rufus.ie/en/
```
CasaOS(不要被它的名字誤導, 它不是一個真成的電腦系統, 想像它是一個帶友善介面及應用商店的Docker管理面板)

先將MiniOS刷寫到microSD卡:
啟動Rufus>揀選microSD卡作為寫入裝置>揀選MiniOS的ISO映像檔>檔案系統選FAT32>點選執行, 以ISO映模式寫入>大功告成!
然後重啟電腦, 按F12可臨時選用microSD卡作為啟動, 亦可選Enter Setup進入BIOS將microSD卡永久設為啟動的首選.

進入MiniOS桌面環境後, 先調整屏幕方向及大小:
打開Settings Manager>Display>Scale: 2.00, Rotation: Right

再進行連網設定:
點擊右下方工作列的網絡圖示>Available networks>揀選自己的WiFi SSID輸入密碼後按Connect連線

安裝CasaOS:
按Ctrl+Alt+t開啟終端機並執行:
```
curl -fsSL https://get.casaos.io | sudo bash
```
等待跑碼後, 當顯示CasaOS v0.4.15 is running at:下方的IP網址便是進入CasaOS的入口.
以瀏覽登入該網址, 首次登入需創建管理員帳戶, 登入後你便可愉快地使用CasaOS了.

以下是一些應用例子:
點擊主頁應用程式中的Files>瀏覽到目標資料夾, 這時你可點擊右上方的上傳或建立按鈕去上載檔案或創建資料夾.
指向某檔案圖示右上角會出現3點, 可執行下載, 複製, 刪除等操作, 
指向某資料夾的圖示按那3點, 更可進行共用, 這時會彈出分享的網址路徑, 於內聯網中其他裝置的瀏覽器中輸入那網址便能存取這資料夾資源.

而應用程式中的App Store圖示便是打開應用商店的入口,那裡有著非常多的應用可提供安裝, 大家按需要去選用吧.
再提供一個技巧, github上有一第三方應用資源, 網址為:
```
https://github.com/Cp0204/CasaOS-AppStore-Play
```
使用方法是點擊App Store主頁中間位置右方的"352 apps"下選菜單(不一定是這個數目)>選新增應用商城來源>
再貼上https://play.cuse.eu.org/Cp0204-AppStore-Play.zip這路徑再安Enter便可.完成安裝第三方應用庫後, 可安裝的應用數量會增多.

