# 進階物聯網案例 13：語音聲控風扇

難度：![level](images/level5.png)


## 目標
<HR>

製作一個能藉語音助手遙距控制的風扇。


## 背景
<HR>

<span id="subtitle">甚麼是語音聲控風扇？</span><BR><P>
語音聲控風扇是一個連接上了互聯網的風扇，可以藉由語音助手使用語音指令喚醒。用戶可以定義不同的語音指令來控制風扇的速度或模式。在本案例中，用戶可以用語音指令打開和關閉風扇。<BR><P>

<span id="subtitle">運作原理</span><BR><P>
在程序中，micro:bit 會連接到 WIFI 並獲取設備 ID。通過設置接收到的指令（turn_on_fan 和 turn_off_fan），可以打開和關閉風扇摩打。<BR>
在 IFTTT 平台的 Smarthon IoT:bit 擴展中，可以預先設置指令，當用戶對語音助手說出特定短語時，它將通過互聯網將指令發送到風扇並觸發打開或關閉的操作。<BR><P>
![pic](images/Case13/Case13_flowchart.png)<P>

<span id="subtitle">了解更多：什麼是語音助手？</span><P>
語音助手，也稱為智能虛擬助理 (IVA) 或智能個人助理 (IPA)，是一種軟件程序，可以根據用戶的命令或問題執行任務或提供服務。有時會用「聊天機器人」來稱呼那些網上聊天的虛擬助手。Amazon Alexa、Google Assistant和 Apple Siri 是常見的例子。<P>
語音助手可以進行語音交互、播放音樂、創建待辦事項列表、設置鬧鐘、串流播客、播放有聲讀物，並提供天氣、交通、體育和其他實時信息，例如新聞。它們還可以控制多種智能設備，充當家庭自動化系統。<P>
如今，為了讓家居更智能，Amazon Echo Dot、Google Home 和 Apple HomePod 作為家用中央控制設備，內置了語音助手，用戶可以通過語音指令輕鬆控制不同的電子設備。

![pic](images/Case13/Case13_iot_device.png)<P>


## 所用部件
<HR>

![pic_90](images/Case13/Case13_parts.png)<P>

## 組裝步驟
<HR>

<span id="subtitle">步驟一</span><BR><P>
這個案例以「大房子模型」作為基礎。
<BR><P>
![pic_90](images/Case13/Case13_ass1.png)<P>

<span id="subtitle">步驟二</span><BR><P>
對準 A 和 B3 模型上的孔，將 E1 模型組裝到 A 模型上。
<BR><P>
![pic_90](images/Case13/Case13_ass2.png)<P>

<span id="subtitle">步驟三</span><BR><P>
用 M4*10 毫米螺絲及螺母把風扇馬達安裝到 F 模型上，連接線可以穿過旁邊的孔。
<BR><P>
![pic_90](images/Case13/Case13_ass3.png)<P>

<span id="subtitle">步驟四</span><BR><P>
把 F 模型裝到 B3、B4 模型上以搭建一個風扇架。
<BR><P>
![pic_90](images/Case13/Case13_ass4.png)<P>

<span id="subtitle">步驟五</span><BR><P>
我們來製作一張沙發。將兩個 K3 模型裝到 K1 模型的兩側。
<BR><P>
![pic_90](images/Case13/Case13_ass5.png)<P>

<span id="subtitle">步驟六</span><BR><P>
將 K2 模型與 K1-K3 模型組裝到一起。
<BR><P>
![pic_90](images/Case13/Case13_ass6.png)<P>


<span id="subtitle">步驟七</span><BR><P>
沙發完成！
<BR><P>
![pic_90](images/Case13/Case13_ass7.png)<P>

<span id="subtitle">步驟八</span><BR><P>
把沙發放在風扇旁邊。
<BR><P>
![pic_90](images/Case13/Case13_ass8.png)<P>

<span id="subtitle">步驟九</span><BR><P>
把 H 模型裝在 B3 模型上，作為裝飾擺設。
<BR><P>
![pic_90](images/Case13/Case13_ass9.png)<P>

<span id="subtitle">步驟十</span><BR><P>
組裝完成！
<BR><P>
![pic_90](images/Case13/Case13_ass10.png)<P>

<H3><u>可選：</u></H3>
<span id="subtitle">步驟一</span><BR><P>
將 Amazon Alexa/Google Nest Mini/Apple Homepod mini 放在客廳。在本案例中，我們放了 Amazon Alexa。
<BR><P>
![pic_90](images/Case13/Case13_ass_ex_1.png)<P>

<span id="subtitle">步驟二</span><BR><P>
組裝完成！
<BR><P>
![pic_90](images/Case13/Case13_ass_ex_2.png)<P>


## 線路連接
<HR>

1. 連接風扇馬達到 P1 端口
![pic_80](images/Case13/Case13_hardware.png)<P>

## 編程（MakeCode）
<HR>

<span id="subtitle">步驟一. 初始化OLED、IoT:bit；連接WiFi</span><BR><P>
* 在`當啟動時`加入`OLED 初始化寬128高64`
* 加入`初始化IoT:bit TX P16 RX P8`
* 加入`連接到 WiFi 名稱 密碼`並輸入 WiFi 名稱和密碼
![pic_70](images/Case13/Case13_p1.png)<P>

<span id="subtitle">步驟二. WiFi連線後顯示圖示`勾號`和裝置ID</span><BR><P>
* 放入一個`當WiFi連接成功後`
* 在裡面加入`顯示圖示勾號`，以在連線後顯示勾號
* 將`當WiFi連接成功後`上的變數`Device_ID`拉到`新行顯示字符串`上
![pic_70](images/Case13/Case13_p2.png)<P>

<span id="subtitle">步驟三. 接收指令</span><BR><P>
* 放入一個`當從互聯網接收到指令`，在 OLED 顯示屏上顯示指令
* 加入`清除顯示`以在每次刷新前清除顯示
* 用`新行顯示字符串 字串組合 Command: WAN_Command`顯示`WAN_Command`並附上文字說明
![pic_70](images/Case13/Case13_p3.png)<P>

<span id="subtitle">步驟四. 指令執行相應動作</span><BR><P>
* 加入一個巢狀的`如果`語句
* 將第一個條件設為`WAN_Command = turn_off_fan`
* 在第一個`如果`段中，用`開啟風扇馬達至速度 0 接口 P1`來關閉風扇
* 將第二個條件設為`WAN_Command = turn_on_fan`
* 在第二個`如果`段中，用`開啟風扇馬達至速度 1023 接口 P1`來打開風扇
![pic_70](images/Case13/Case13_p4.png)<P>

<span id="subtitle">完整答案<BR><P>
MakeCode: [https://makecode.microbit.org/_XE7bMKA8xRfF](https://makecode.microbit.org/_XE7bMKA8xRfF)<BR><P>
你可以從以下網頁中下載HEX檔案：<BR>
<iframe src="https://makecode.microbit.org/#pub:_XE7bMKA8xRfF" width="100%" height="500" frameborder="0"></iframe>


## 物聯網（Alexa, 雲端控制, IFTTT）
<HR>

### 第一部分. 設置 Amazon Alexa
1. 取得 Amazon Alexa App。<BR>
![pic_90](images/Case13/Case13_Alexa_1.png)<P>
2. 建立 Amazon 帳戶（如果未有 Amazon 帳戶）並登入。 <BR>
![pic_90](images/Case13/Case13_Alexa_2.png)<P>
3. 可選：<P>
設定 Alexa 裝置並連接到 Amazon 帳戶。<BR>

### 第二部分. 設置 IFTTT

1. 取得 IFTTT App。 <BR>
![pic_100](images/Case13/Case13_Alexa_3.png)<P>
2. 打開並登入 IFTTT。<BR>
3. 按下「create」來創建一個 applet。<BR>
4. 在「If」中，搜尋「alexa」並選擇「Amazon Alexa」，然後選擇「Say a specific phrase」。<BR>
![pic_90](images/Case13/Case13_Alexa_4.png)<P>
5. 它會自動檢測 Amazon Alexa App中的已經登入了的帳戶。然後，在紅框位置輸入短語。在這個例子中，我們輸入「turn on the fan」。<BR>
![pic_90](images/Case13/Case13_Alexa_5.png)<P>
6. 在「Then」中，搜尋「smarthon iot」並選擇「Smarthon IoT (micro:bit)」。<BR>
![pic_90](images/Case13/Case13_Alexa_6.png)<P>
7. 選擇「Control Command」，然後填寫「Device ID」，「Command」的名稱根據 micro:bit 的程式填寫，然後按下「Continue」就完成了！<BR>
![pic_90](images/Case13/Case13_Alexa_7.png)<P>


### 結果
<HR>

1. 打開 Amazon Alexa App，使用連接了 IFTTT 的 Alexa 帳戶。<BR>
2. 按一下右下角的按鈕與 Alexa 對話，然後說「Trigger turn on the fan」。<BR>
![pic_100](images/Case13/Case13_Alexa_8.png)<P>
3. 第一次會詢問您是否開啟對話服務。按下「Turn on」並再次說出短語。短語應觸發 IFTTT 並使指令傳送至 Iot:bit。<BR>
![pic_90](images/Case13/Case13_Alexa_9.png)<P>
4. 當說「Alexa trigger turn on the fan」時，風扇就會打開； 當說「Alexa trigger turn off the fan」時，風扇就會關閉。<BR>
![pic_100](images/Case13/Case13_Alexa_10.png)<P>
5. 可選：<P>
您可以將真實設備 <u>Amazon echo dot</u> 連接到這個 App，以便使用真實的語音控制器進行語音控制。<BR>
![pic_100](images/Case13/Case13_Alexa_11.png)<P>


## 物聯網（Google Assistant）
<HR>

### 第一部分. 設置 Google Home 和 Google Assistant App

1. 取得 Google Home 和 Google Assistant App。<BR>
![pic_100](images/Case13/Case13_Google_1.png)<P>
2. 登入您的 Google 帳戶。<BR>
3. 打開 Google Home App，切換到您的 Google 帳戶。<BR>
4. 按下「settings」，選擇「Works with Google」。 <BR>
![pic_100](images/Case13/Case13_Google_2.png)<P>
5. 搜尋並選擇「IFTTT」，授權 Google 存取 IFTTT 服務。<BR>
![pic_100](images/Case13/Case13_Google_3.png)<P>
6. 連結後，IFTTT 會出現在列表中。<BR>
![pic_100](images/Case13/Case13_Google_4.png)<P>

### 第二部分. 設置 IFTTT

1. 取得 IFTTT App。
![pic_100](images/Case13/Case13_Google_5.png)<P>
2. 打開並登入 IFTTT。
3. 按下「create」來創建一個 applet。
4. 在「If」中，搜尋「google assistant」並選擇「Google assistant V2」。
![pic_100](images/Case13/Case13_Google_6.png)<P>
5. 在「Activate scene」中輸入觸發指令的短語。在案本例中，我們輸入「fan on」。
![pic_100](images/Case13/Case13_Google_7.png)<P>
6. 在「Then」中，搜尋「smarthon iot」並選擇「Smarthon IoT (micro:bit)」。
![pic_100](images/Case13/Case13_Google_8.png)<P>
7. 選擇「Control Command」，然後填寫「Device ID」以及指令「turn_on_fan」。
![pic_100](images/Case13/Case13_Google_9.png)<P>
8. 最後按下「Continue」和「Finish」以保存。
![pic_90](images/Case13/Case13_Google_10.png)<P>

### 結果

1. 打開 Google Home 或 Google Assistant App。確保登入的 Google 帳戶已連接到先前在 Google Home App上設定的 IFTTT。
2. 說「Hey google, activate (您設定的短語)」或按下按鈕然後說「Activate (您設定的短語)」。
![pic_100](images/Case13/Case13_Google_11.png)<P>
3. 短語應觸發 IFTTT 並使指令傳送至 Iot:bit。
![pic_90](images/Case13/Case13_Google_12.png)<P>
4. 風扇就會打開。
![pic_100](images/Case13/Case13_Google_13.png)<P>
5. 可選： <P>
您可以將真實設備 <u>Google Nest Mini</u> 或 <u>Google Home</u> 連接到這個 App，以便使用真實的語音控制器進行語音控制。<BR>
![pic_100](images/Case13/Case13_Google_14.png)<P>

## 物聯網（Apple Siri）
<HR>

### 第一部分. 設置 IFTTT
1. 取得 IFTTT App。
![pic_100](images/Case13/Case13_Apple_1.png)<P>
2. 打開並登入 IFTTT。
3. 按下「create」來創建一個 applet。
4. 在「If 」中，搜尋「iOS Shortcuts」，然後選擇「Shortcut automation started」。
![pic_100](images/Case13/Case13_Apple_2.png)<P>
5. 在「Then」中，搜尋「smarthon iot」並選擇「Smarthon IoT (micro:bit)」。
![pic_100](images/Case13/Case13_Apple_3.png)<P>
6. 選擇「Control Command」，然後填寫「Device ID」，「Command」的名稱根據 micro:bit 的程式填寫，然後按下「Continue」就完成了！
![pic_100](images/Case13/Case13_Apple_4.png)<P>

### 第二部分. 在 iPhone 上設定 IOS Shortcuts
1. 開啟 Shortcuts App，然後按下右上角的加號按鈕 (+)。
![pic_50](images/Case13/Case13_Apple_5.png)<P>
2. 按下 Add Action > App > IFTTT。
![pic_100](images/Case13/Case13_Apple_6.png)<P>
3. 選擇 Trigger Applet，按一下 Select an Applet 旁邊的藍色箭頭 ( > )，然後按下 Choose。
![pic_100](images/Case13/Case13_Apple_7.png)<P>
4. 選擇您想要利用此捷徑執行的 Applet（請注意，只有使用了「iOS Shortcuts - Shortcut automation started trigger」的 Applet 才會出現在此清單中）。
![pic_70](images/Case13/Case13_Apple_8.png)<P>
5. 點擊屏幕頂部的「Trigger Applet」來命名您的捷徑，這將成為用來觸發該 Applet 的自訂短語。
![pic_100](images/Case13/Case13_Apple_9.png)<P>
6. 保存捷徑。
![pic_90](images/Case13/Case13_Apple_10.png)<P>

### 結果
1. 按一下該捷徑，或者按住 iPhone 上的按鈕，然後說「Turn on the fan」或「Hi Siri turn on the fan」。
![pic_100](images/Case13/Case13_Apple_11.png)<P>
2. Applet 會觸發。
![pic_100](images/Case13/Case13_Apple_12.png)<P>
3. 可選：<P>
您可以將真實設備 <u>Apple Homepod</u> 連接到 <u>Apple Home App</u>，以便使用真實的語音控制器進行語音控制。<BR>
![pic_100](images/Case13/Case13_Apple_13.png)<P>



## 思考
<HR>

Q1. 除了「Say a specific phrase」這個 Alexa 在 IFTTT 上的觸發器之外，還有其他 Alexa 觸發器可以使用嗎？<BR>
