# 章節 8: HTTP 功能

HTTP代表超文本傳輸協議。它是全球資訊網數據通訊的基礎。HTTP在客戶端-服務器計算模型中作為請求-回應協議運作。它用於在網頁瀏覽器（客戶端）和網頁服務器之間傳輸超媒體文件，例如HTML頁面、圖像和其他資源。HTTP的工作方式是客戶端向服務器發送請求，然後服務器回應所請求的資源，並附帶一個HTTP狀態碼，該狀態碼指示請求的成功或失敗。在本章中，您將學習如何使用Iot:bit發送HTTP請求並接收回應。<br>
 
![](images/Ch8_v2/HTTP_intro.png)<br>

| 功能 | 有Body | 沒有Body |
| -- | -- | -- | 
| GET |<b>#Body 不會被送出，最終會被忽略</b>| 正常運作 |	
| POST | 正常運作 | *會送出空字串 "" 作為 body |

<b># HTTP 規範指出，使用 HTTP GET 包含 body 不是一個好主意。</b><br>
<b>* 這僅在韌體版本 4.2 之後支援</b><br>

## 示範場景
<HR>

<span id="subtitle">目標：<BR><P>

此範例旨在透過HTTP從服務器獲取字串內容。<br>

<span id="subtitle">詳情：<BR><P>

在此範例中，涉及兩個部分。<br>

- 在第一部分中，我們需要創建一個承載字串的HTTP服務器。<br>
- 在第二部分中，我們對micro:bit進行編程，使其發送HTTP請求並接收來自服務器的回應。<br>

![](images/Ch8_v2/HTTP_scenario.png)<br>

## 第一部分：創建HTTP API服務器
<HR>

<span id="subtitle">目標：<BR><P>

我們使用一個免費的服務器服務來設置一個包含字串內容的服務器進行測試。<br>

<span id="subtitle">第一步：<BR><P>

前往 [https://ptsv3.com](https://ptsv3.com)輸入一個獨特的ID以找到一個未被占用的Toilet（訪問路徑），例如“smarthon”。<br>

![](images/Ch8_v2/http_3.png)<br>
 
<span id="subtitle">第二步：<BR><P>

修改配置，使服務器以JSON格式返回回應。修改完成後，點擊“Update Toilet Config”。<br>
 
 ![](images/Ch8_v2/http_4_1.png)<br>

例子 JSON:<br>
{"server":"ptsv3","user":"smarthon","msg":{"date":"19/4/2024","time":"13:00","content":"hello"}}<br>

![](images/Ch8_v2/http_5.png)<br>

## 第二部分：編程
<hr>


<span id="subtitle">目標：<BR><P>

向服務器發送HTTP請求並提取內容<br>


<span id="subtitle">第一步：連接WiFi<BR><P>
- 在獲取內容之前，我們需要連接到網絡。我們在第一章中已經學習了如何連接到WiFi。<br>

 ![](images/Ch8_v2/http_6.png)<br>
 

<span id="subtitle">第二步：複製URL<BR><P>

- 通過右鍵點擊 -> 複製鏈接，複製Post URL。<br>
![](images/Ch8_v2/http_7.png)<br>
 
<span id="subtitle">第三步：使用POST功能去更新數據<BR><P>
- 將 `當按鈕A被按下` 塊拖入編輯器<br>
- 前往 IoT:bit -> IoT服務，並拖入 `發送HTTP請求` 塊<br>
- 將URL貼入該塊中<br>
- 在此範例中我們使用POST<br>

**在Body中放入數據**
- 例子 JSON:<br>
- {"server":"ptsv3","user":"smarthon","msg":{"date":"21/07/2025","time":"12:00","content":"hello"}}<br>
- 時間和日期會被改變<br>

![](images/Ch8_v2/http_8.png)<br>
 
<span id="subtitle">第四步：使用 GET 方法獲取數據<BR><P>

- 將 `當按下按鈕 B` 塊拖入編輯器<br>
- 前往 IoT:bit -> IoT 服務，拖入 `發送HTTP請求` 塊<br>
- 將 URL 貼到該塊中<br>
- 本例中使用 GET 方法，因此將 Body 留空<br>
 ![](images/Ch8_v2/http_9.png)<br>


<span id="subtitle">第五步：創建回應處理程序<BR><P>

- 前往 IoT:bit -> IoT服務，並將 `當接收到HTTP回復` 塊拖入編輯器<br>
- 在OLED上顯示 `HTTP_Status_Code`<br>
![](images/Ch8_v2/http_10.png)<br>

<span id="subtitle">第六步：設置JSON提取函數<BR><P>

- 前往 IoT:bit -> IoT服務，並拖入 `獲取鍵的值` 塊<br>
- 根據JSON填入鍵名<br>
- 將 `data` 拖入 `JSON字串`<br>

![](images/Ch8_v2/http_11.png)<br>

- 當需要訪問多層級JSON時，嵌套這些塊，直到訪問到目標層級為止。<br>

![](images/Ch8_v2/http_12.png)<br>


- 備註：`HTTP_Status_Code` 會返回一個表示發送結果的代碼，例如 200（成功）、404（未找到）、502（錯誤網關），更多資訊請參閱 [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)<br>

## 完整答案
<HR>

MakeCode: [https://makecode.microbit.org/S67494-15951-48626-85113](https://makecode.microbit.org/S67494-15951-48626-85113)
您也可以從以下網站下載HEX檔案：<br>

<iframe src="https://makecode.microbit.org/S67494-15951-48626-85113" width="100%" height="500" frameborder="0"></iframe>

## 結果
<HR>

連接到 Wi-Fi 後，按下按鈕 A，將 body 資訊 POST 到網頁伺服器，並更改 body 部分。如果伺服器的 body 部分有任何變更，按下按鈕 B，將 GET body 資訊到 micro:bit。<br>
![](images/Ch8_v2/http_14.png)<br>
![](images/Ch8_v2/http_16.png)<br>
![](images/Ch8_v2/http_15.jpg)<br>

  

 
