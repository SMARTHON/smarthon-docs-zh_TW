# 案例 03: 智能垃圾桶

程度: ![level](images/level2.png)
![auto_fit](images/Case3/case-03.png)<P>


## 目標
<HR>

製作一個會根據內部當前容量改變 LED 顏色的智能垃圾桶。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是智能垃圾桶?</span><P>
垃圾桶上的 LED 可以告訴人們桶內的當前容量，收集工人可以輕易判斷有否需要清理垃圾。這樣可以減少更換垃圾袋的次數，從而減少膠袋用量。<BR><P>

<span id="subtitle">運作原理</span><P>
距離傳感器可以探測桶內垃圾高度，從而轉化為當前容量。彩色 LED 則會隨著容量轉變。<BR><P>
![pic_80](images/Case3/Concept-diagram-Case3.png)<P>

## 所用部件
<HR>

![pic](images/Case3/Case3_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><P>
用 M4\*10 毫米螺絲及螺母把超音波距離傳感器組裝到 C2 模型上。<BR><P>
![pic](images/Case3/Case3_ass1.png)<P>
<span id="subtitle">步驟二</span><P>
用 M4\*10 毫米螺絲及螺母把彩色 LED 組裝到 C1 模型上。<BR><P>
![pic](images/Case3/Case3_ass2.png)<P>
<span id="subtitle">步驟三</span><P>
組合 C1 和 C2<BR><P>
![pic_60](images/Case3/Case3_ass3.png)<P>
<span id="subtitle">步驟四</span><P>
組裝完成!<BR><P>
![pic_60](images/Case3/Case3_ass4.png)<P>

## 線路連接
<HR>

* 連接超音波距離傳感器和 IoT:bit 的 P14(trig)/P15(echo)端口<BR><P>
* 連接彩色 LED 和 IoT:bit 的 P1 端口<BR><P>
![pic](images/Case3/Case3_hardware.png)<P>


## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 定義新變數和啟動彩色 LED </span><P>
* 定義新變數”distance”並設值為 0
* 在”Neopixel”模組中加入”變數 strip 設為 NeoPixel at pin P1 with 1 leds as RGB(BGB) format”至”當啟動時”
* 插入”strip set brightness 50”
* 插入”等待 5 秒”
![auto_fit](images/Case3/Case3_p1.png)<P>

<span id="subtitle">步驟二. 讀取距離讀數</span><P>
* 在「重復無限次」加入”變數 distance 設為取得量度距離使用單位厘米 trig 接口 P14echo 接口 P15”
* 加入”如果...那麼”，設”distance ≤ 4”為前提
* 加入”等待一秒鐘”
![pic_90](images/Case3/Case3_p2.png)<P>

<span id="subtitle">步驟三. 根據回報距離顯示相應距離</span><P>
* 如果 distance ≤ 4， strip 會顯示紅色，否則綠色
![pic_90](images/Case3/Case3_p3.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_Dxz8Yhge0eph](https://makecode.microbit.org/_Dxz8Yhge0eph)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_Dxz8Yhge0eph" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

距離傳感器會傳回桶內垃圾與垃圾桶頂部的距離。<BR>LED 反映垃圾桶是否滿載。當滿載時，變為紅色，否則為綠色。<BR><P>
![pic](images/Case3/Case3_result.gif)<P>

## 思考
<HR>

Q1. 如何加入音效提示滿載?(例如利用蜂鳴器)<BR><P>
