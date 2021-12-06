# 案例 04: 城市噪音檢測器

程度: ![level](images/level2.png)
![auto_fit](images/Case4/case-04_1.png)<P>

## 目標
<HR>

製作一個能夠偵查路邊噪音的檢測器。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是城市噪音檢測器?</span><P>
城市噪音檢測器能監測公路上的噪音污染，因為過大的噪音會降低周遭人們的生活水
平。<BR>安裝一個檢測器可以幫助工程師收集有關數據用於城市規劃。<BR><P>

<span id="subtitle">運作原理</span><P>
聲音傳感器可以偵測公路上的噪音水平，數據可以以圖表形式顯然。<BR><P>
![pic_70](images/Case4/Concept-diagram-Case4.png)<P>


## 所用部件
<HR>

![pic](images/Case4/Case4_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><P>
用 M2\*10 毫米螺絲及螺母把 OLED顯示屏 組裝至 D1 模型。<BR><P>
![pic](images/Case4/Case4_ass1.png)<P>
<span id="subtitle">步驟二</span><P>
用 M4\*10 毫米螺絲及螺母把聲音傳感器組裝至 D1 模型。<BR><P>
![pic](images/Case4/Case4_ass2.png)<P>
<span id="subtitle">步驟三</span><P>
組裝 D1 和 D2。<BR><P>
![pic](images/Case4/Case4_ass3.png)<P>
<span id="subtitle">步驟四</span><P>
組裝完成!<BR><P>
![pic_40](images/Case4/Case4_ass4.png)<P>

## 線路連接
<HR>

* 連接聲音傳感器和 IoT:bit 的 P1 端口<BR><P>
* 把 OLED顯示屏 接到 I2C 端口<BR><P>
![pic](images/Case4/Case4_hardware.png)<P>

## 編程(MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED 顯示屏和宣告新變數</span><p>
* 初始化 OLED (128闊64高)
* 宣告變數”Noise”並設值為 0
![auto_fit](images/Case4/Case4_p1.png)<P>

<span id="subtitle">步驟二. 在 OLED 上顯示噪音數值</span><P>
* 在「重復無限次」加入`將變數 Noise 設為四捨五入取得聲音傳感感器數值接口 P1`
* 在「燈光」模塊中加入點亮長條圖顯示值為 Noise， 最大值為 100
* 等待 0.5 毫秒
![auto_fit](images/Case4/Case4_p2.png)<P>

<span id="subtitle">步驟三. 在 OLED 上顯示噪音數值</span><P>
* 加入”清除顯示”
* 加入`顯示字符串(字申組合(“Noise: ‵Noise‵ dB”))`
![auto_fit](images/Case4/Case4_p3.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_ECbThsUkx5M3](https://makecode.microbit.org/_ECbThsUkx5M3)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_ECbThsUkx5M3" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

在初始化 IoT:bit 和 OLED 後，將會顯示噪音的圖表。<BR><P>
![pic](images/Case4/Case4_result.gif)<P>
![pic](images/Case4/Case4_result2.png)<P>

## 思考
<HR>

Q1. 當噪音太大可以如何發出提示?<BR><P>

