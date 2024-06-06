# 案例 03：智能環保風扇

難度：![level](images/level2.png)
![auto_fit](images/Case3/intro.png)<P>


## 目標
<HR>

製作一個能透過偵測周遭環境而調整風速的智能環保風扇。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是智能環保風扇？</span><P>
智能環保風扇是一個能夠自動調整風速及開關的風扇，用以節省電力。<BR><P>

<span id="subtitle">運作原理</span><P>
在屋內安裝溫度及濕度傳感器，用以持續測量周遭環境。當溫度正常或太低時，風扇會自動調低強度或關閉；當溫度太高時則會調高。<BR><P>

![pic_80](images/Case3/Case3_flowchart.png)<P>


## 所用部件
<HR>

![pic_90](images/Case3/Case3_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
首先組裝大房子模型。<BR><P>
![auto_fit](images/Case3/Case3_ass1.png)<P>
<span id="subtitle">步驟二</span><BR><P>
把 E4 模型裝到 A 模型上作為牆壁，以在家裡右側建造一個小的客廳。<BR><P>
![auto_fit](images/Case3/Case3_ass2.png)<P>
<span id="subtitle">步驟三</span><BR><P>
用 M4 * 10 毫米螺絲及螺母把溫度及濕度傳感器安裝到 E3 模型上。<BR><P>
![auto_fit](images/Case3/Case3_ass3.png)<P>
<span id="subtitle">步驟四</span><BR><P>
用 M2 * 10 毫米螺絲及螺母把 OLED 顯示屏安裝到 E3 模型上。<BR><P>
![auto_fit](images/Case3/Case3_ass4.png)<P>
<span id="subtitle">步驟五</span><BR><P>
用 M4 * 10 毫米螺絲及螺母把風扇馬達安裝到 F 模型上，連接線可以穿過旁邊的孔。<BR><P>
![auto_fit](images/Case3/Case3_ass5.png)<P>
<span id="subtitle">步驟六</span><BR><P>
把 F 模型裝到 B3、B4 模型上以搭建一個風扇架。<BR><P>
![auto_fit](images/Case3/Case3_ass6.png)<P>
<span id="subtitle">步驟七</span><BR><P>
把 I1 模型裝到三個 I2 模型上以建造一張桌子。<BR><P>
![auto_fit](images/Case3/Case3_ass7.png)<P>
<span id="subtitle">步驟八</span><BR><P>
桌子完成了！<BR><P>
![auto_fit](images/Case3/Case3_ass8.png)<P>
<span id="subtitle">步驟九</span><BR><P>
把桌子放入客廳。<BR><P>
![auto_fit](images/Case3/Case3_ass9.png)<P>
<span id="subtitle">步驟十</span><BR><P>
組裝完成！<BR><P>
![auto_fit](images/Case3/Case3_ass10.png)<P>




## 線路連接
<HR>

1. 連接溫度及濕度傳感器（DHT11）到 P2 端口
2. 連接擴展 OLED 顯示屏到 I2C 端口
3. 連接風扇馬達到 P1 端口
![pic_80](images/Case3/Case3_hardware.png)<P>

## 編程（MakeCode）
<HR>

<span id="subtitle">步驟一. 初始化OLED顯示屏</span><P>
* 把`OLED 初始化 寬128 高64`加入到`當啟動時`，以初始化 OLED顯示屏
![pic_70](images/Case3/Case3_p1.png)<P>

<span id="subtitle">步驟二. 建立變數</span><P>
* 建立一個名為`temperature`的變數
![pic_50](images/Case3/Case3_p2.png)<P>

<span id="subtitle">步驟三. 讀取並顯示 DHT11的讀數</span><P>
* 在`重複無限次`中，用`讀取溫濕度傳感器數值接口P2`讀取數據
* 從數據中提取溫度值，並用`變數temperature設為取得溫度數值攝氏`將其儲存到變數中
* 建議每次都先清除 OLED 顯示屏上的顯示才更新屏幕資訊
* 用`清除顯示`來清除顯示。
* 然後用`新行顯示字符串字符組合溫度: temperature`來以編排好的文本顯示溫度值
![pic_70](images/Case3/Case3_p3.png)<P>

<span id="subtitle">步驟四. 檢查溫度</span><P>
* 在`重複無限次`加入一個巢狀的`如果-否則`語句
* 第一個條件為`temperature < 22`
* 在第一個`如果`段中，用`開啟風扇馬達至速度 0 接口 P1`來關閉風扇
* 第二個條件為`temperature < 26`
* 在第二個`如果`段中，用`開啟風扇馬達至速度 600 接口 P1`來以一半速度運行風扇
* 第三個條件為`temperature ≥ 26`
* 在第三個`如果`段中，用`開啟風扇馬達至速度 1023 接口 P1`來以全速運行風扇
![pic_70](images/Case3/Case3_p4.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_1m42k8eh9a2q](https://makecode.microbit.org/_1m42k8eh9a2q)<BR><P>
你可以從以下網頁中下載HEX檔案：<BR>
<iframe src="https://makecode.microbit.org/#pub:_1m42k8eh9a2q" width="100%" height="500" frameborder="0"></iframe>


## 結果
<HR>

當室內溫度變化時，會符合三個條件其中一個，然後風扇馬達會根據溫度以不同的速度運行或關閉。<BR><P>
![pic](images/Case3/Case3_result.gif)<P>

## 思考
<HR>

Q1. 除了開風扇還有什麼方法可以降溫？<BR><P>
