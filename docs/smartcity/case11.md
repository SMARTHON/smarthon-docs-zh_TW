# 物聯網案例 11: 自動天台簷篷系統

程度: ![level](images/level4.png)
![auto_fit](images/Case11/case-11.png)<P>

## 目標
<HR>

製作一個會在天氣改變時自動開關的簷篷，避免衣物被雨水沾濕。

## 背景
<HR>

<span id="subtitle">為什麼我們需要自動天台簷篷系統?</span><BR><P>
這樣當下雨時人們再不需要衝上天台把衣服收回。<BR><P>
<span id="subtitle">運作原理</span><BR><P>
Micro:bit通過IFTTT平台上的天氣預報系統，取得指令內容開關簷篷。<BR><P>
![auto_fit](images/Case11/Concept-diagram-Case11.png)<P>

## 所用部件
<HR>

![auto_fit](images/Case11/Case11_parts.png)<P>
 
## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
把雨水傳感器組裝至 H2 模型。<BR><P>
![auto_fit](images/Case11/Case11_ass1.png)<P>
<span id="subtitle">步驟二</span><BR><P>
把 H1 和 H3 模型組裝。<BR><P>
![auto_fit](images/Case11/Case11_ass2.png)<P>
<span id="subtitle">步驟三</span><BR><P>
組裝所有模型。<BR><P>
![auto_fit](images/Case11/Case11_ass3.png)<P>
<span id="subtitle">步驟四</span><BR><P>
用 M2 螺絲及螺母把舵機組裝到 H5 模型。  <BR><P>
![auto_fit](images/Case11/Case11_ass4.png)<P>
<span id="subtitle">步驟五</span><BR><P>
組裝 H4-H5 和 H6-H7模型<BR><P>
![pic_60](images/Case11/Case11_ass5.png)<P>
![auto_fit](images/Case11/Case11_ass6.png)<P>
<span id="subtitle">步驟六</span><BR><P>
組裝完成!<BR><P>
![pic_40](images/Case11/Case11_ass7.png)<P>


## 線路連接
<HR>

連接180°舵機和 IoT:bit 的 P1 端口<BR><P>

Micro:bit P1|舵機
:-: | :-: 
S (黃) |S (橙)
V (紅)	| V (紅)
G (黑) | G (棕)

![auto_fit](images/Case11/Case11_hardware.png)<P>

## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，IoT:bit 和連接 Wi-Fi</span><BR><P>
![pic_60](images/Case11/Case11_p1.png)<P>

<span id="subtitle">步驟二. 在連接 Wi-Fi 後顯示剔號及ID</span><BR><P>
![pic_50](images/Case11/Case11_p2.png)<P>

<span id="subtitle">步驟三. 接收指令</span><BR><P>
* 每次接收時都先清除顯示
* 把接收到的拍令用顯示字串 "Command: WAN_Command" 顯示出來
![pic_70](images/Case11/Case11_p3.png)<P>

<span id="subtitle">步驟四. 以指令控制開關</span><BR><P>
* 加入 ”如果...那麼” ，以 ”WAN_Command = Rain” 為條件
* 在第一個 "那麼" 裡添加`Turn Servo to 90 degree at P1`
* 點擊加號，以”WAN_Command = Clear” 為第二條件
* 在第二個 "那麼" 裡添加`Turn Servo to 180 degree at P1`
![auto_fit](images/Case11/Case11_p4.png)<P>

<span id="subtitle">步驟五. 按 A 以開啟簷篷</span><BR><P>
* 當按A按鈕時，轉動舵機
![pic_50](images/Case11/Case11_p5.png)<P>

<span id="subtitle">步驟六. 按 B 以開啟簷篷</span><BR><P>
* 當按B按鈕時，向另一角度轉動舵機
![pic_50](images/Case11/Case11_p6.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_h133LW5miXY9](https://makecode.microbit.org/_h133LW5miXY9)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_h133LW5miXY9" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">* 詳情參考 附錄:IFTTT</span><BR><P>

<span id="subtitle">步驟一. 創建新專案(共需要兩個專案)，選擇 weather underground<BR><P>
<span id="subtitle">步驟二. 選擇”Current condition changes to”<BR><P>
<span id="subtitle">步驟三. 選擇地點和觸發條件<BR><P>
<span id="subtitle">步驟四. 選擇 Snarthon IoT:Bit 為 Then<BR><P>
<span id="subtitle">步驟五. 選擇指令<BR><P>
<span id="subtitle">步驟六. 輸入 ID和指令(Rain)<BR><P>
<span id="subtitle">步驟七. 重複以上動作，觸發條件和指令改為晴天和clear

![auto_fit](images/Case11/Case11_iot1.png)<P>


## 結果
<HR>
IFTTT會依照地點的天氣發送指令。<BR>
當 micro:bit 收到”RAIN"指令，簷篷會關上。反之則開啟。<BR><P>

![auto_fit](images/Case11/Case11_result.gif)<P>

## 思考
<HR>

Q1. 除了雨天和晴天，能否根據其他天氣狀態作出反應?<BR><P>
