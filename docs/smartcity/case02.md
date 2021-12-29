# 案例 02: 智慧停車場閘杆

程度: ![level](images/level2.png)
![auto_fit](images/Case2/case-02.png)<P>

## 目標
<HR>

製作一個會根據停車場內車位狀況和是否有來車自動開閉的智慧停車場閘杆。<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是智慧停車場閘杆?</span><P>
智慧停車場閘杆能為人們帶來便利。通過自動偵測停車場內車位狀況，它能夠節省司機等候閘杆開啟和尋找車位的時間。<BR><P>

<span id="subtitle">運作原理</span><P>
180° 舵機控制閘杆的開關。如果停車場內尚有空位，閘杆會在有車駛近時自動開啟。若然已無車位，即使有車到訪，閘杆也不會開啟。<BR><P>
![pic_80](images/Case2/Concept-diagram-Case2.png)<P>
從上述示意圖可見，在「重復無限次」裡會一直檢測到訪車輛和場內空位。

## 所用部件
<HR>

![auto_fit](images/Case2/Case2_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
用 M4\*10 毫米螺絲及螺母把距離傳感器裝到 B1 模型上。 <BR><P>
![auto_fit](images/Case2/Case2_ass1.png)<P>
<span id="subtitle">步驟二</span><BR><P>
用 M2\*10 毫米螺絲及螺母把 180° 舵機組裝到 B1 模型上。<BR><P>
![auto_fit](images/Case2/Case2_ass2.png)<P>
<span id="subtitle">步驟三</span><BR><P>
用M2\*7.5 毫米尖頭螺絲 把 B2 模型安裝到舵機。 把 B3 模型放在
B1 卡模型下。<BR><P>
![auto_fit](images/Case2/Case2_ass3.png)<P>
<span id="subtitle">步驟四</span><BR><P>
組裝完成!<BR><P>
![pic_60](images/Case2/Case2_ass4.png)<P>


## 線路連接
<HR>

* 連接運動傳感器和 IoT:bit 上的 P14(trig)/P15(echo) 端口<BR><P>
* 連接光度傳感器和 IoT:bit 上的 P0 端口<BR><P>
* 連接 180° 舵機和 IoT:bit 上的 P2 端口<BR><P>
![auto_fit](images/Case2/Case2_hardware.png)<P>

*注意<BR>

>1.根據顏色連接接線和端口<BR>
>2.P0 內建線路予蜂鳴器。在使用 P0 端口予其他外接設備時遇上問題，建議查
看位於 IoT:bit 右上的蜂鳴器開關狀態

## 編程 (MakeCode)

<span id="subtitle">步驟一. 定義新變數和舵機起始位置</span><BR><P>
* 定義新變數”distance”和”light2”
* 在「當啟動時」裡設”distance” 和”light2” 數值為 0，”轉動舵機到 0 度 接口 P2”
![pic_50](images/Case2/Case2_p1.png)<P>

<span id="subtitle">步驟二. 讀取距離和光度數值</span><BR><P>
* 在「重復無限次」把”distance”變數設為 “取得量度距離使用單位厘米 trig 接口 P14echo 接口 P15”

* 把”light2”變數設為”取得亮度傳感器數值接口P0”

![pic_90](images/Case2/Case2_p2.png)<P>

<span id="subtitle">步驟三. 以光度值決定開閘與否</span><BR><P>
* 在「重復無限次」加入”如果...那麼”，前提設為”distance ≤ 5”
* 在上述邏輯內再加一個”如果...那麼”，前提設為”light2 > 20”
![pic_90](images/Case2/Case2_p3.png)<P>

<span id="subtitle">步驟四. 設定舵機位置</span><BR><P>
* 在”light2 > 20”內加入” 轉動舵機到 90 度接口 P2”
* 等待 5 秒
* 轉動舵機到 0 度接口 P2
![pic_90](images/Case2/Case2_p4.png)<P>

*注意

>1.如果舵機轉動角度/方向與程式不符，重設舵機至 0 度再嘗試<BR>
>2.如果遭遇錯誤，嘗試分開測試光度傳感器和距離傳感器並決定讀數是否正確。<BR>
>3.查看接線是否正確<BR>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_TMD3WXE2pKkA](https://makecode.microbit.org/_TMD3WXE2pKkA)<BR><P>
你可以在以下網頁中下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_TMD3WXE2pKkA" width="100%" height="500" frameborder="0"></iframe>

## 結果
<HR>

透過光度傳感器，成功得知有沒有空缺的車位。當車經過超音波距離傳感器時，因應車位的空缺狀況就能控制180° 舵機轉動來打開閘杆5秒，讓車輛駛進停車場。<BR><P>
![auto_fit](images/Case2/Case2_result.gif)<P>

## 思考
<HR>

Q1. 你可以怎麼在 OLED 顯示屏上顯示光和距離讀數?<BR><P>
Q2. 試在 Micro:bit的LED陣列上顯示停車場內狀況。<BR><P>
