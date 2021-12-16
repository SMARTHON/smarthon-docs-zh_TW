# 物聯網案例 08: 智能交通燈

程度: ![level](images/level5.png)

<span id="remarks">* 詳情參考 附錄:物件與物件間的溝通<BR>
* 本案例分為兩部分:發送者及接收者。要完成這案例，需要兩套組裝。</span>
![auto_fit](images/Case8/case-08_1.png)<P>

## 發送者
<HR>

### 目標
<HR>

製作一個可以向其他設備反映該地區有沒有塞車的系統。<BR><P>

### 背景
<HR>

<span id="subtitle">如何向其他 micro:bit 傳送訊號?</span><P>
發送者和接收者連接至同一個頻道，容許 Wi-Fi 訊號在之間傳遞。當發送者發出”trafficjam”，接收者會因應訊號作出反應。<BR><P>

<span id="subtitle">發出者運作原理</span><P>
當光度傳感器長期回饋過低數值，這代表有車停在此處，即公路上有塞車發生。發送者傳送”trafficjam”至 microbit。反之則發送”nojam”。<BR><P>
![auto_fit](images/Case8/Concept-diagram-Case8_sender.png)<P>

### 所有部件
<HR>

![auto_fit](images/Case8/Case8a_parts.png)<P>


### 線路連接
<HR>

* 連接光度傳感器和 IoT:bit 的 P0 端口。<BR><P>
![auto_fit](images/Case8/Case8a_hardware.png)<P>

*注意

>1. 根據顏色連接接線和端口<BR>
>2. P0 內建線路予蜂鳴器。在使用 P0 端口予其他外接設備時遇上問題，建議查看位於 IoT:bit 右上的蜂鳴器開關狀態


### 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，IoT:bit 和連接至 Wi-Fi</span><P>
* 啟動 OLED，IoT:bit 和連接至 Wi-Fi
* 宣告新變數`light2`並設值為 0 
![auto_fit](images/Case8/Case8a_p1.png)<P>

<span id="subtitle">步驟二. 在連接至 Wi-Fi 後顯示剔號</span><P>
![pic_60](images/Case8/Case8a_p2.png)<P>

<span id="subtitle">步驟三. 檢查交通狀況</span><P>
* 在「重復無限次」加入”如果...那麼”並以`WiFi connected?`為前設
* 設`light2` 為`取得光傳感器數值接口 P0`
* 清除顯示
* 新行顯示”字串組合 Light: `light2`”
* 等待 6 秒
![auto_fit](images/Case8/Case8a_p3.png)<P>

<span id="subtitle">步驟四. 當交通擠塞發出提示</span><P>
* 在邏輯內加入新”如果...那麼”，以”ligh12 < 10”為前設
* 在 "如果...那麼" 裡面添加 `Wifi Sender send Channel`的訊息，分別依照交通情況來傳送 'trafficjam' 或 'nojam' 
![auto_fit](images/Case8/Case8a_p4.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_DDHataUJ04HY](https://makecode.microbit.org/_DDHataUJ04HY)<BR><P>
你可以在以下網頁下載HEX檔案<BR>
<iframe src="https://makecode.microbit.org/#pub:_DDHataUJ04HY" width="100%" height="500" frameborder="0"></iframe>


### 結果
<HR>

光度傳感器用以偵測有沒有出現塞車。當光度正常， "nojam" 會被送出。<BR><P>
![auto_fit](images/Case8/Case8a_result1.png)<P>
當光度過低， "trafficjam" 會被送出。<BR><P>
![auto_fit](images/Case8/Case8a_result2.png)<P>

### 思考
<HR>

Q1. 我們可以用超音波距離傳感器偵測有否塞車嗎?<BR><P>


## 接收者
<HR>

### 目標
<HR>

製作一個能接收訊號並控制交通燈的交通系統。<BR><P>

### 背景
<HR>

<span id="subtitle">如何接收另一個 micro:bit 的訊號?</span><P>
讓發送者和接收者連接至同一個頻道。然後讀取訊息。<BR><P>

<span id="subtitle">接收者運作原理</span><P>
當收到”trafficjam”訊號，代表有塞車狀況出現。交通燈會轉為紅色。反之則會維持綠色。<BR><P>
![auto_fit](images/Case8/Concept-diagram-Case8_receiver.png)<P>

### 所用物資
<HR>

![auto_fit](images/Case8/Case8b_parts.png)<P>

### 組裝步驟
<HR>

<span id="subtitle">步驟一</span><P>
用 M4\*10毫米螺絲及螺母把交通燈組裝到 G1 模型上。組裝 G1 和 G2。<BR><P>
![auto_fit](images/Case8/Case8b_ass1.png)<P>

<span id="subtitle">步驟二</span><P>
組裝完成!<BR><P>
![auto_fit](images/Case8/Case8b_ass2.png)<P>


### 線路連接
<HR>

* 連接交通燈和 IoT:bit 的 P0 端口<BR><P>
![auto_fit](images/Case8/Case8b_hardware.png)<P>

*注意:

>1. 根據顏色連接接線和端口<BR>
>2. P0 內建線路予蜂鳴器。在使用 P0 端口予其他外接設備時遇上問題，建議查
看位於 IoT:bit 右上的蜂鳴器開關狀態

### 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，IoT:bit 連接至 Wi-Fi</span><P>
* 啟動 OLED，IoT:bit 和連接至 Wi-Fi
* 宣告新變數`oldmsg`為” “。
![auto_fit](images/Case8/Case8b_p1.png)<P>

<span id="subtitle">步驟二. 加入”tsuenwan”頻道</span><P>
* 在”當WiFi連接後”加入剔號和”加入到頻道`tsuenwan`”
![auto_fit](images/Case8/Case8b_p2.png)<P>

<span id="subtitle">步驟三. 接收 Wi-Fi 訊息</span><P>
* 在”當從頻道收到訊息”加入清除顯示
* 新行顯示 ”字串組合”訊息: `receivedmessage`”""
![pic_70](images/Case8/Case8b_p3.png)<P>
 
<span id="subtitle">步驟四. 宣告新函式(TurnRed)</span><P>
* 在`TurnRed`函式中加入`Control traffic light at P1`
* 等待兩秒
* 轉顏色為黃色，等待兩秒
* 轉顏色為紅，等待兩秒
![auto_fit](images/Case8/Case8b_p4.png)<P>

<span id="subtitle">步驟五. 宣告新函式(TurnGreen)</span><P>
* 在`TurnGreen`函式中加入”Control traffic light at P1”
* 轉為紅色，等待兩秒
* 轉為黃色，等待兩秒
* 轉為綠色，等待兩秒
![auto_fit](images/Case8/Case8b_p5.png)<P>

<span id="subtitle">步驟六. 設定交通燈初始狀態</span><P>
* 在「當啟動時」加入`TurnGreen`
![pic_60](images/Case8/Case8b_p6.png)<P>

<span id="subtitle">步驟七. 轉變交通燈狀態</span><P>
* 在`On WiFi Receiver received`加入”如果...那麼”
* “receivedMessage ≠ oldmsg”為前設
* 設”oldmsg” = receivedMessage
* 在邏輯裏加入”如果...那麼”，”receivedMessage = trafficjam”為前設
* 呼叫`TurnRed`
* 將“receivedMessage = nojam”設為否則前設
* 在否則內呼叫`TurnGreen`
![auto_fit](images/Case8/Case8b_p7.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_K5eKdP1hMcdj](https://makecode.microbit.org/_K5eKdP1hMcdj)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_K5eKdP1hMcdj" width="100%" height="500" frameborder="0"></iframe>


### 結果
<HR>

交通燈會根據 Wi-Fi 訊息轉變顏色。<BR>
* 如接收到”nojam”，燈會轉綠。<BR>
* 如接收到”trafficjam”，燈會轉紅。<BR>
<BR><P>
![auto_fit](images/Case8/Case8b_result.gif)<P>

### 思考
<HR>

Q1. 試就顏色添加音效?<BR><P>
Q2. 如果我們不加入邏輯檢查新舊訊息，會發生甚麼?<BR>