# 物聯網案例 07: 智能家居防盜系統

程度: ![level](images/level3.png)
![auto_fit](images/Case7/case-07.png)<P>

## 目標
<HR>

製作一個能在附近有可疑活動時自動發出警報和提示的智能家居防盜系統。<BR><P>

## Background
<HR>

<span id="subtitle">甚麼是 IFTTT?</span><BR><P>
IFTTT 可以把用家的應用程式和設備連接並容許它們進行交流以完成特定工作。<BR><P>
<span id="subtitle">運作原理</span><BR><P>
運動傳感器回饋訊號至主板，若 TRUE 則主板激活蜂鳴器並自動發出電郵提示用家。
同時 OLED 顯示屏會反映有可疑人士。<BR><P>
![auto_fit](images/Case7/Concept-diagram-Case7.png)<P>

## 所用部件
<HR>

![auto_fit](images/Case7/Case7_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
用M4\*10毫米螺絲及螺母把運動傳感器組裝至 F1 模型。
![auto_fit](images/Case7/Case7_ass1.png)<P>
![auto_fit](images/Case7/Case7_ass2.png)<P>
<span id="subtitle">步驟二</span><BR><P>
組裝 F1 和 F2 卡板。
![auto_fit](images/Case7/Case7_ass3.png)<P>
<span id="subtitle">步驟三</span><BR><P>
組裝完成!
![pic_60](images/Case7/Case7_ass4.png)<P>


## 線路連接
<HR>

* 連接運動傳感器和 IoT:bit 的 P1 端口<BR><P>
* 檢查 IoT:bit 上的蜂鳴器開關<BR><P>
![auto_fit](images/Case7/Case7_hardware.png)<P>

 <B><I>請把蜂鳴器開關 "下拉" ，用以連接蜂鳴器</I></B>

## IoT (IFTTT)
<HR>

<span id="remarks">* *詳情參考* 附件..IFTTT 設定” </span><BR><P>

<span id="subtitle">步驟一</span><BR><P>
訪問 [https://ifttt.com](https://ifttt.com/) ，創建新專案 (if webhooks then Email)<BR><P>
![auto_fit](images/Case7/Case7_iot1.png)<P>


<span id="subtitle">步驟二</span><BR><P>
依次點擊“My services” >> “Webhooks”，select “Documentation” ，複製 Applet Key。<BR><P>
![auto_fit](images/Case7/Case7_iot2.png)<P>

## 編程(MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，Iot:bit 和連接至 Wi-Fi</span><BR><P>
![auto_fit](images/Case7/Case7_p1.png)<P>

<span id="subtitle">步驟二. 顯示剔號以表示連接至 Wi-Fi</span><BR><P>
![auto_fit](images/Case7/Case7_p2.png)<P>

<span id="subtitle">步驟三. 讀取運動傳感器讀數</span><BR><P>
* 在「重復無限次」裏加入”如果...那麼”，以`WiFi connected?`為前設
* 在上述邏輯再加一個”如果...那麼”，以”取得運動傳感器數值接口 P1 = TRUE”為前設
![auto_fit](images/Case7/Case7_p3.png)<P>
 
<span id="subtitle">步驟四. 當有人經過時自動發出警示</span><BR><P>
* 在”如果...那麼”加入”演奏音階中音 C 持續 1 拍
* LED 顯示”Monster”圖示
* 加入”Send IFTTT key... event_name...”
![auto_fit](images/Case7/Case7_p4.png)<P>

<span id="subtitle">步驟五. 在無人經過時顯示”smile”圖示</span><BR><P>
* 在”否則”加入”smile”圖示
* 在”WiFI connected?” 內加入等待 1 秒
![auto_fit](images/Case7/Case7_p5.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_DyU6CsXYE7fx](https://makecode.microbit.org/_DyU6CsXYE7fx)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_DyU6CsXYE7fx" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

當連上了 Wi-Fi，如果門旁邊有可疑活動，蜂鳴器會被激活並發出電郵，同時
micro:bit 上的 LED 會顯示”monster”圖示。<BR><P>
![auto_fit](images/Case7/Case7_result1.png)

![auto_fit](images/Case7/Case7_result2.gif)


## 思考
<HR>

Q1. 如何避免短時間內重複發送了大量電郵? <BR><P>
Q2. 能否加強辨認經過的人是否陌生人?<BR><P>

