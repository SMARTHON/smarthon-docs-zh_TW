# 物聯網案例 10: 節能街燈

程度: ![level](images/level4.png)
![auto_fit](images/Case10/case-10.png)<P>

## 目標
<HR>

製作一個能以指令開關的街燈<BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是節能街燈?</span><BR><P>
節能街燈是可以在指定時間自動開關的街燈，能夠同時兼顧節省能源及照明需求。<BR><P>
<span id="subtitle">運作原理</span><BR><P>
當從 WAN 收到指令，micro:bit 會根據指令控制街燈。所以只需要在不同時間及場合發送指令即可。<BR><P>
![auto_fit](images/Case10/Concept-diagram-Case10.png)<P>

## 所用部件
<HR>

![auto_fit](images/Case10/Case10_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
用 M4 螺絲及螺母把 LED 組裝到 I2 模型上。組裝 I1 至 I3 模型。<BR><P>
![auto_fit](images/Case10/Case10_ass1.png)<P>

<span id="subtitle">步驟二</span><BR><P>
組裝完成<BR><P>
![pic_40](images/Case10/Case10_ass2.png)<P>


## 線路連接
<HR>

* 連接 LED 和 IoT:bit 的 P0 端口<BR><P>
![auto_fit](images/Case10/Case10_hardware.png)<P>

*注意:*

>1. 根據顏色連接接線和端口<BR>
>2. P0 內建線路予蜂鳴器。在使用 P0 端口予其他外接設備時遇上問題，建
議查看位於 IoT:bit 右上的蜂鳴器開關狀態

## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，Iot:bit 和連接至 Wi-Fi</span><BR><P>
![auto_fit](images/Case10/Case10_p1.png)<P>

<span id="subtitle">步驟二 1. 在連接至 Wi-Fi 後顯示剔號及ID</span><BR><P>
![pic_60](images/Case10/Case10_p2.png)<P>

<span id="subtitle">步驟三. 接收 WAN 指令</span><BR><P>
* 把接收到的指令顯示出來
![pic_80](images/Case10/Case10_p3.png)<P>

<span id="subtitle">步驟四. 控制 LED 開關</span><BR><P>
* 加入”如果...那麼”
* ”WAN_Command = lighton”設為第一個條件
* 在 "如果" 裏加入`turn white LED to 1023 at P0`
* 點擊加號，在那添加第二個條件”WAN_Command = lightoff”
* 在第二個 "如果" 裏加入`turn white LED to 0 at P0`
![auto_fit](images/Case10/Case10_p4.png)<P>


<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_Ami5MkUsEDso](https://makecode.microbit.org/_Ami5MkUsEDso)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_Ami5MkUsEDso" width="100%" height="500" frameborder="0"></iframe>


## IoT (IFTTT)
<HR>

<span id="remarks">* 詳情參考 "附錄:IFTTT" <BR>
本案例一共需要兩個專案 *
</span><BR><P>

<span id="subtitle">步驟一. 在 IFTTT 開立新專案</span><BR><P>
<span id="subtitle">步驟二. 選擇”Date & Time” 為 IF THIS</span><BR><P>
<span id="subtitle">步驟三。 選擇時間間隔，時區，時間為上午6時</span><BR><P>
<span id="subtitle">步驟四。 選擇 Smarthon IoT:bit 為 Then That</span><BR><P>
<span id="subtitle">步驟五。 選擇指令</span><BR><P>	
<span id="subtitle">步驟六。 輸入指令和 Device ID後儲存</span><BR><P>
<span id="subtitle">步驟七。 重複以上動作，時間設為下午6時</span><BR><P>
![auto_fit](images/Case10/Case10_ifttt1.png)<P>


## 結果
<HR>

在IFTTT平台上會在每天早晚6時發送訊號，因此LED會在每天早晚6時開關。<BR><P>
![auto_fit](images/Case10/Case10_result.gif)<P>


## 思考
<HR>

Q1. 除了時間之外，IFTTT能否用其他條件觸發?
