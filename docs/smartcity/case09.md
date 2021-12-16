# 物聯網案例 09: 遙距智能門控制

程度: ![level](images/level4.png)
![auto_fit](images/Case9/case-09.png)<P>

## 目標
<HR>

用 App Inventor 製作一個能遙控開關門的應用程式。 <BR><P>

## 背景
<HR>

<span id="subtitle">甚麼是 app inventor?</span><BR><P>
這是一個能讓用家自行開發智能電話程式的工具，Android及IOS都能夠使用。<BR><P>
<span id="subtitle">智能門控制原理</span><BR><P>
當 microbit 收到”opendoor”訊號，舵機會自動轉動。當收到”closedoor”，門會自動關閉。<BR><P>
![auto_fit](images/Case9/Concept-diagram-Case9.png)<P>

## 所用部件
<HR>

![auto_fit](images/Case9/Case9_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
用 M3 螺絲及螺母把 L字-模型組裝到 H1 模型上。<BR><P>
![auto_fit](images/Case9/Case9_ass1.png)<P>
<span id="subtitle">步驟二</span><BR><P>
用M2\*7.5毫米螺絲把轉動臂固定在舵機,把 180ᵒ舵機組裝到 H1 模型。<BR><P>
![auto_fit](images/Case9/Case9_ass2.png)<P>
<span id="subtitle">步驟三</span><BR><P>
把萬字夾剪成長度 4.2 厘米，並連接及扣到 L字-模型。<BR><P>
![auto_fit](images/Case9/Case9_ass3.png)<P>
<span id="subtitle">步驟四</span><BR><P>
組裝所有模型。<BR><P>
![auto_fit](images/Case9/Case9_ass4.png)<P>
<span id="subtitle">步驟五</span><BR><P>
組裝完成!<BR><P>
![pic_50](images/Case9/Case9_ass5.png)<P>


## 線路連接
<HR>

連接 180ᵒ舵機和 IoT:bit 的 P2 端口<BR><P>

Micro:bit P2|舵機
-:-|-:-
S (黃)|S (橙)
V (紅)|V (紅)
G (黑)|G (棕)

![auto_fit](images/Case9/Case9_hardware.png)<P>

## 編程 (MakeCode)
<HR>

<span id="subtitle">步驟一. 啟動 OLED，Iot:bit 和連接至 Wi-Fi</span>
![pic_60](images/Case9/Case9_p1.png)<P>

<span id="subtitle">步驟二. 設定舵機初始位置</span><BR><P>
* 加入`turn servo to 180 degree at P2`
![pic_60](images/Case9/Case9_p2.png)<P>

<span id="subtitle">步驟三. 在連接至 Wi-Fi 後顯示剔號及ID</span><BR><P>
![pic_60](images/Case9/Case9_p3.png)<P>

<span id="subtitle">步驟四. 接收 WAN 指令</span><BR><P>
* 在`On WiFI received`加入清除顯示
* 新行顯示` "字串組合"Command” WAN_Command” `
![pic_80](images/Case9/Case9_p4.png)<P>

<span id="subtitle">步驟五. 以 WAN 指令開關門</span><BR><P>
* 如接收到”opendoor”，舵機轉向 45 度
* 如接收到”closedoor”，舵機轉向 180 度
![pic_80](images/Case9/Case9_p5.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_LtLRgxMVHMvc](https://makecode.microbit.org/_LtLRgxMVHMvc)<BR><P>
你可以在以下網頁下載HEX檔案:<BR>
<iframe src="https://makecode.microbit.org/#pub:_LtLRgxMVHMvc" width="100%" height="500" frameborder="0"></iframe>

 
## IoT (App Inventor)
<HR>

<span id="remarks">*詳情參考”附錄..App Inventor 2*</span><BR><P>


<span id="subtitle">步驟一</span><BR><P>
創建新頁面<BR><P>
* On Designer:
* 在左邊界面拖出元素 
* 把”Web”拖到最下面
![auto_fit](images/Case9/Case9_iot1.png)<P>


<span id="subtitle">步驟二</span><BR><P>
編程
* On Blocks: 
* The WAN control command URL is: 
[http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand](http://control.smarthon.cc/publish?id=DeviceID&msg=ControlCommand)

* 當 button1 被點撃，以下指令會被執行
![auto_fit](images/Case9/Case9_iot2.png)<P>
* 當 button2 被點撃，以下指令會被執行
![auto_fit](images/Case9/Case9_iot3.png)<P>
* 下載程式至手機
![auto_fit](images/Case9/Case9_iot4.png)<P>
 
## 結果
在框內輸入 device ID，點選”opendoor”或”clodedoor”<BR><P>
![auto_fit](images/Case9/Case9_result1.png)<P>

 
![auto_fit](images/Case9/Case9_result3.png)<P>

透過App Inventor，可以很輕易地控制門的開關<BR><P>
![auto_fit](images/Case9/Case9_result4.gif)<P>


## 思考
<HR>

Q1. 能否增加密碼驗證才開門?<BR><P>
Q2. 舵機還能在智能家居的什麼地方應用?<BR><P>
