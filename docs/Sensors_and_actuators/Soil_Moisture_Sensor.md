土壤濕度傳感器
==============
![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_1.png)
## 簡介
<HR>
這款土壤濕度傳感器透過感測電容來監測土壤的濕度。每當電容器正負極之間的區域有水，傳感器就可以探測出濕度，讀數介乎 0 至 100%。<br><br>

## 原理
<HR>
土壤濕度傳感器上有一個外露的電容器，由正極板和負極板組成。當我們將傳感器插入土壤中，土壤就變成了介電質。<br>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_2_2.png)<br>

電容器可以透過在兩塊極板上累積電荷來在電場中儲存電能，這種儲存電荷的能力稱為電容。<br>

由於水的介電常數（電容率）比空氣高，因此它在電場中比空氣更容易極化。 當土壤潮濕時，電容就會上升。<br>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_3_1.png)<br>

透過測量電容的變化，即可得知土壤濕度。<br>

## 規格
<HR>
供電電壓：5V<br>
介面：模擬<br>
原始值回傳：0 - 1023 <br>
Makecode 擴展回傳：0 - 100% <br><br>

## 針腳
<HR>

| 針腳 | 功能 |
| -- | -- |
| G | 接地 |
| V | 電源供應 |
| S | 訊號輸出（模擬） |

## 外觀及大小
<HR>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_4.jpg)<br>

大小：35mm X 70mm<br>

## 快速指引
<HR>
- 連接土壤濕度傳感器到開發板上（使用連接線材）<br>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_5.png)<br><br>

- 打開Makecode，使用 <https://github.com/SMARTHON/pxt-smartplant> 擴展<br>
![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_6.png)<br><br>

- 啟動 OLED 螢幕並顯示土壤濕度的讀數。 <br>
![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_7.png)<br>

- 讀數的範圍介乎 0 到 100。<br>

## 結果
<HR>
當傳感器偵測不到水時<br>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_8.jpg)<br><br>
當傳感器變濕時<br>

![](images/Soil_Moisture_Sensor/Soil_Moisture_Sensor_9.jpg)<br><br>

## FAQ
<HR>
Q：為什麼我給植物澆水後傳感器的讀數仍然很低？<br>
A：傳感器與土壤充分接觸可以獲得更準確的濕度讀數，請檢查土壤是否有覆蓋外露的電容器。<br><br>

Q：我可以使用傳感器來檢測其他介質的濕度嗎？<br>
A：此傳感器僅設計用於檢測土壤中的濕度，它不適用於其他情況。<br>


