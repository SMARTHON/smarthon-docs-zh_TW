# 物聯網案例 06: 智慧天氣監測站

程度: ![level](images/level2.png)
![auto_fit](images/Case6/case-06.png)<P>

## 目標
<HR>

製作一個能收集雨水，溫度及濕度傳感器數據的智慧天氣監測站，並自動把數據送上ThingSpeak 平台。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是 Thingspeak?</span><BR><P>
ThingSpeak 是一個物聯網數據分析平台，提供即時數據圖表分顯然及分析。在這個案例，我們會使用該平台製作數據圖表。<BR><P>

<span id="subtitle">運作原理</span><BR><P>
實時收集溫度、濕度和雨水數據並上傳至 ThingSpeak，令分析數據更輕鬆。<BR><P>
![auto-fit](images/Case6/Concept-diagram-Case6.png)<P>

## 所用部件
<HR>

![auto_fit](images/Case6/Case6_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle"> 步驟一</span><BR><P>
用M4\*10毫米螺絲及螺母把雨水傳感器組裝到 F2 模型上。<BR><P>
![auto_fit](images/Case6/Case6_ass1.png)<P>
<span id="subtitle"> 步驟二</span><BR><P>
用M4\*10毫米螺絲及螺母把溫度及濕度傳感器組裝到 F2 模型上。
![auto_fit](images/Case6/Case6_ass2.png)<P>
<span id="subtitle">步驟三</span><BR><P>
組裝 F1 和 F2 模型。
![auto_fit](images/Case6/Case6_ass3.png)<P>
<span id="subtitle">步驟四</span><BR><P>
組裝完成!
![pic_60](images/Case6/Case6_ass4.png)<P>

## 線路連接
<HR>

* 連接雨水傳感器和 IoT:bit 的 P0 端口<BR><P>
* 連接溫度及濕度傳感器和 IoT:bit 的 P2 端口<BR><P>
![auto_fit](images/Case6/Case6_hardware.png)<P>

*注意

>1. 根據顏色連接接線和端口<BR>
>2. P0 內建線路予蜂鳴器。在使用 P0 端口予其他外接設備時遇上問題，建議查看位於 IoT:bit 右上的蜂鳴器開關狀態


## IoT (ThingSpeak)
<HR>

<span id="remarks">*詳細步驟參考* 附錄..上傳資料至 ThingSpeak”</span><BR><P>

<span id="subtitle">步驟一</span><BR><P>
訪問 [https://thingspeak.com](https://thingspeak.com/)， 選擇 Channels -> My Channels -> New Channel<BR><P>
![auto_fit](images/Case6/Case6_iot1.png)<P>
  
<span id="subtitle">步驟二</span><BR><P>
輸入 `Channel name`， `Field1`， `Field2`，點擊 Save Channel<BR><P>
* `Channel name`: Smart Weather Station
* `Field 1`: temperature
* `Field 2`: humidity
* `Freld 3`: raindrop


<span id="subtitle">步驟三</span><BR><P>
選擇 your channel >> API Keys，複製 API key<BR><P>
![auto_fit](images/Case6/Case6_iot2.png)<P>


## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動OLED，IoT:bit 和 Wi-Fi</span><BR><P>
* 初始化OLED，IoT:bit 和 Wi-Fi
* 宣告新變數 `raindrop`，`humidity`，`temperature`並設值為0
![auto_fit](images/Case6/Case6_p1.png)<P>

<span id="subtitle">步驟二.連上網絡</span><BR><P>
* 在連上網絡後於 OLED上顯示剔號
![auto_fit](images/Case6/Case6_p2.png)<P>

<span id="subtitle">步驟三.讀取溫度、濕度和雨水讀數</span><BR><P>
* 在「重復無限次」加入”如果...那麼”，`WiFi連接狀態`為前設
* 設`humidity`為`DHT11 讀取濕度接口 P2`
* 設`temperature`為`DHT11 讀取溫度接口 P2`
* 設`raindrop`為`取得雨水傳感器數值接口 P0`
![auto_fit](images/Case6/Case6_p3.png)<P>

<span id="subtitle">步驟四. 在 OLED 上顯示讀數</span><BR><P>
* 加入”清除顯示”
* 新行顯示”Temperature: `temperature`， Humidity: `humidity`， Raindrop:
`raindrop`”
![auto_fit](images/Case6/Case6_p4.png)<P>

<span id="subtitle">步驟五. 上傳資料至 ThingSpeak</span><BR><P>
* 在”如果...那麼”加入”發送到ThingSpeak key...”及輸入API key
* 在 Field value 分別放入 `temperature`， `humidity`， `raindrop`
* 等待 15 秒
![auto_fit](images/Case6/Case6_p5.png)<P>

<span id="subtitle">步驟六. 顯示上傳狀態</span><BR><P>
* 加入`當上傳到Thingspeak後`
* 新行顯示”ThingSpeak: `Status`， Error: `Error_code`”
![auto_fit](images/Case6/Case6_p6.png)<P>



<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_E2dUpj07a03j](https://makecode.microbit.org/_E2dUpj07a03j)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_E2dUpj07a03j" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

當 micro:bit 連到了互聯網，它會開始從傳感器讀取數據並上傳至 ThingSpeak。<BR><P>
![auto_fit](images/Case6/Case6_result.gif)<P>
在 ThingSpeak 上設立的三個 fields 會反映實時數據。<BR><P>
![auto_fit](images/Case6/Case6_result2.png)<P>

## 思考
<HR>

Q1. 我們可以怎上傳其他種類的數據至 ThingSpeak?<BR><P>
