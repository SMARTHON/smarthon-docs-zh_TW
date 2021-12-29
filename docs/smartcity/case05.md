# 案例 05: 車速檢測器

程度: ![level](images/level3.png)
![auto_fit](images/Case5/case-05.png)<P>

## 目標
<HR>

製作一個車速檢測器。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是車速檢測器?</span><P>
檢測系統能根據車輛在一定時間內移動距離得出其車速。 安裝檢測系統用以檢控有效減少交通意外發生。<BR><P>

<span id="subtitle">運作原理</span><P>
超音波距離傳感器可以在兩個時間點測量車輛與其之間的距離，從而計算其速率。 <BR><P>
每 0.5 秒，傳感器會量度車輛與其之間距離。 <BR><P>
![auto_fit](images/Case5/Case5_des1.png)<P>
根據物理學，速率 = (距離一 – 距離二)， 這時候可得知有三種情況。<BR>
* 距離一 > 距離二.. 車輛正靠近<BR>
* 距離一 = 距離二.. 車輛已停止移動/路面沒有車輛<BR>
* 距離一 < 距離二.. 車輛正轉向/駛離，此情況無視<BR>
這速率可以在 micro:bit LED 以圖表表達車速..<BR><P>
![auto_fit](images/Case5/Case5_des2.png)<P>

![pic_80](images/Case5/Concept-diagram-Case5.png)<P>
## 所用部件
<HR>

![auto_fit](images/Case5/Case5_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><P>
用 M2\*10 毫米螺絲及螺母把 OLED顯示屏 組裝到 D1 模型上。<BR><P>
![auto_fit](images/Case5/Case5_ass1.png)<P>
<span id="subtitle">步驟二</span><P>
組裝 D1 和 D2。<BR><P>
![auto_fit](images/Case5/Case5_ass2.png)<P>
<span id="subtitle">步驟三</span><P>
底座組裝完成!
![pic_40](images/Case5/Case5_ass3.png)<P>
<span id="subtitle">步驟四</span><P>
用 M4\*10 螺絲及螺母把超音波距離傳感器組裝到 E1 模型。<BR><P>
![auto_fit](images/Case5/Case5_ass4.png)<P>
<span id="subtitle">步驟五</span><P>
組裝 E1 和 E2 模型。<BR><P>
![auto_fit](images/Case5/Case5_ass5.png)<P>
<span id="subtitle">步驟六</span><P>
組裝完成。!<BR><P>
![pic_40](images/Case5/Case5_ass6.png)<P>

## 線路連接
<HR>

* 連接超音波距離傳感器和 IoT:bit 的 P14(trig)/P15(echo)端口 <BR><P>
* 把 OLED 連到 IoT:bit 的 I2C 端口 <BR><P>
![auto_fit](images/Case5/Case5_hardware.png)<P>

## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED 顯示屏</span><P>
* 初始化OLED顯示屏(128闊64高)
* 宣告新變數`distance1`，`distance2`，`speed`為0
![auto_fit](images/Case5/Case5_p1.png)<P>

<span id="subtitle">步驟二. 宣告函式(calculate_Speed)</span><P>
* 在進階模塊「函式」宣告新函式 `calculate_Speed`
* 從`取得距離...`中取得數值，分別放入`distance1`和`distance2`
* 根據速率公式，設`speed` 為”(distane1 – distance2) / 0.5”
![auto_fit](images/Case5/Case5_p2.png)<P>

<span id="subtitle">步驟三. 計算車速</span><P>
* 在「重復無限次」叫喚`calculate_Speed`
* 加入”如果...那麼”，”speed ≥ 0”為前設
* 在邏輯中加入`點亮長條圖 顯示值為 speed 最大值為 20`
* 加入`清除顯示`，`新行顯示字符串(Distance1: distance1)，(Distance2: distance2)， (Speed: speed)`
![auto_fit](images/Case5/Case5_p3.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_Ro5fAyhMdRvX](https://makecode.microbit.org/_Ro5fAyhMdRvX)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_Ro5fAyhMdRvX" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

超音波距離傳感器會持續監察車輛的距離。車速經計算後會顯示在 OLED 顯示屏，同時以圖表形式表現在 LED 上。<BR><P>
![auto_fit](images/Case5/Case5_result.gif)<P>

## 思考
<HR>

Q1. 如何設定音效提示以警示超速?<BR><P>

