# 案例 08：智能太陽檢測窗簾

難度：![level](images/level3.png)
![auto_fit](images/Case8/intro.png)<P>


## 目標
<HR>

製作一個會偵測屋外陽光並自動開關的智能太陽檢測窗簾。<BR><P>


## 背景
<HR>

<span id="subtitle">甚麼是智能太陽檢測窗簾？</span><P>
智能太陽檢測窗簾會根據偵測到的陽光量自動收起或放下來。<BR><P>

<span id="subtitle">運作原理</span><P>
在屋外安裝一個光度傳感器，當它偵測到強光（Light > 70）時，代表會有陽光照射到房屋。 於是窗簾會放下來，以減少熱能傳導到屋內。如此一來可以減少能量損失，並節省空調的能源。<BR><P>

![auto_fit](images/Case8/Case8_flowchart.png)<P>

## 重點知識

在這個案例的編程部分，會運用到一個「flag」的概念。這是用來檢查窗簾是否已經放了下來，避免繼續放下窗簾。

## 所用部件
<HR>

![pic_90](images/Case8/Case8_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
這個案例以「大房子模型」作為基礎。<BR><P>
![auto_fit](images/Case8/Case8_ass1.png)<P>

<span id="subtitle">步驟二</span><BR><P>
用縲絲批將窗簾鐵杆安裝到360ᵒ舵機上，以製作窗簾。
<BR><P>
![pic_90](images/Case8/Case8_ass2.png)<P>

<span id="subtitle">步驟三</span><BR><P>
將窗簾紙布剪成 8cm*8cm 的正方形。<BR><P>
![pic_90](images/Case8/Case8_ass3.png)<P>

<span id="subtitle">步驟四</span><BR><P>
用膠水將剪好的紙布黏在窗簾鐵杆上。<BR><P>
![pic_90](images/Case8/Case8_ass4.png)<P>

<span id="subtitle">步驟五</span><BR><P>
把萬用黏土膠搓成長條。<BR><P>
![pic_90](images/Case8/Case8_ass5.png)<P>

<span id="subtitle">步驟六</span><BR><P>
將捏好的萬用黏土膠黏在窗簾的底部。<BR><P>
![pic_90](images/Case8/Case8_ass6.png)<P>

<span id="subtitle">步驟七</span><BR><P>
用 M2*10 毫米螺絲及螺母把製作好的窗簾 (舵機) 安裝到 B1 模型上。<BR><P>
![pic_90](images/Case8/Case8_ass7.png)<P>

<span id="subtitle">步驟八</span><BR><P>
蓋上 B1 和 C1 模型。<BR><P>
![pic_90](images/Case8/Case8_ass8.png)<P>

<span id="subtitle">步驟九</span><BR><P>
用 M4*10 毫米螺絲及螺母把光度傳感器安裝到 C1 模型上。<BR><P>
![pic_90](images/Case8/Case8_ass9.png)<P>

<span id="subtitle">步驟十</span><BR><P>
組裝完成！<BR><P>
![pic_90](images/Case8/Case8_ass10.png)<P>


## 線路連接
<HR>

1. 連接光度傳感器到 P1 端口
2. 連接360ᵒ舵機到 P2 端口
![pic_80](images/Case8/Case8_hardware.png)<P>

## 編程（MakeCode）
<HR>

<span id="subtitle">步驟一. 初始化 OLED顯示屏並建立變數</span><P>
* 把`OLED 初始化 寬128 高64`加入到`當啟動時`，以啟動 OLED 顯示屏
* 建立變數`curtainOn`，並將其設為`false`
![auto_fit](images/Case8/Case8_p1.png)<P>

<span id="subtitle">步驟二. 建立窗簾控制函式「openCurtain」</span><P>
* 建立函式`openCurtain`
* 在函式裡，控制連接端口上的 360°舵機的速度和方向，例如`轉動360度舵機以順時針方向速度高接口 P2`
* 加入暫停讓它有幾秒鐘的時間轉動 (取決於您設定的速度)
* 用同樣方式停止 360°舵機，例如`轉動360度舵機以順時針方向速度停止接口 P2`
* 將變數`curtainOn`設為`true`
![pic_80](images/Case8/Case8_p2.png)<P>

<span id="subtitle">步驟三. 建立窗簾控制函式「closeCurtain」</span><P>
* 建立函式` closeCurtain`
* 這個函式與上一個函式相似，但方向和狀態相反
* 控制連接端口上的 360°舵機的速度和方向，例如`轉動360度舵機以逆時針方向速度高接口 P2`
* 加入暫停讓它有幾秒鐘的時間轉動 (取決於您設定的速度)
* 用同樣方式停止 360°舵機，例如`轉動360度舵機以逆時針方向速度停止接口 P2`
* 將變數`curtainOn`設為`false`
![pic_80](images/Case8/Case8_p3.png)<P>

<span id="subtitle">步驟四. 取得光度數值</span><P>
* 在`重複無限次`中，用`變數 light 設為取得光度傳感器數值接口 P1`
* 透過`清除顯示`在每次刷新前先清除顯示
* 用`顯示數字 light`在顯示屏上顯示數值
![pic_90](images/Case8/Case8_p4.png)<P>

<span id="subtitle">步驟五. 檢查光度數值並作出反應</span><P>
* 在`重複無限次`加入一個巢狀的`如果`語句
* 將第一個條件設為`light ≥ 70 且 curtainOn = true`
* 第一個 If 段代表陽光較強，需關掉窗簾，所以加入`呼叫closeCurtain`
* 將第二個條件設為`light < 40 且 curtainOn = false`
* 第二個 If 段代表陽光較弱，需打開窗簾，所以加入`呼叫openCurtain`
![pic_90](images/Case8/Case8_p5.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_d184i0bPygjJ](https://makecode.microbit.org/_d184i0bPygjJ)<BR><P>
你可以從以下網頁中下載HEX檔案：<BR>
<iframe src="https://makecode.microbit.org/#pub:_d184i0bPygjJ" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

當光度傳感器感測到屋外的光度較強時，舵機會轉動放下窗簾。而當光度不強時，舵機會反方向轉動，收起窗簾。<BR><P>
![auto_fit](images/Case8/Case8_result.gif)<P>

## 思考
<HR>

Q1. 除了陽光量之外，還有什麼條件可以用來決定收起還是放下窗簾呢？
