# 超音波距離傳感器

![pic_70](images/Ultrasonic_Distance_Sensor_0.jpg)
## 簡介
距離傳感器使用超音波原理進行與前方目標距離的檢測。大部分情況下,超音波能夠提供一個快速而準確的距離測量結果。
<P>


## 原理
距離傳感器使用超音波去量度目標物與傳感器之間的距離。當傳感器向前方發出超音波的時候,超音波(聲波的一種)開始透過空氣傳播直到碰撞上目標物,然後反彈回來被傳感器偵測。<BR>因聲波在空氣中傳播的速度大約為340米/秒, 所以利用發送及接收之間的時間間距就能計算出距離。 <P>
![auto_fit](images/Ultrasonic_Distance_Sensor_1.png)


## 規格
* 操作電壓: 5V
* 工作頻率: 40kHz
* 檢測距離: 3cm 至 4m
* 量度角度: 小於15°

## 針腳

|針腳|功能|
|--|--|
|GND|接地|
|VCC|電源供應|
|Trig|觸發訊號輸入|
|Echo|接收訊號輸出|

## 外觀及大小
![pic_70](images/Ultrasonic_Distance_Sensor_2.png)

大小: 41mm X 25mm

## 快速指引

* 連接傳感器到開發板(使用連接線)
![auto_fit](images/Ultrasonic_Distance_Sensor_3.png)<P>

* 打開Makecode, 使用https://github.com/smarthon/pxt-smartcity 擴展 <P>
![auto_fit](images/Ultrasonic_Distance_Sensor_4.png)<P>

* 初始化OLED顯示屏,然後把傳感器讀取的數值在顯示屏上顯示
![auto_fit](images/Ultrasonic_Distance_Sensor_5.png)

## 結果

讀取到的距離數值會隨著手掌的遠離而增加。
![pic_70](images/Ultrasonic_Distance_Sensor_6.png)


## FAQ

Q: 為什麼我不能正確讀取與目標物的距離?<BR>
A: 因為發射及接收端都處於傳感器上,受限於物理大小, 反射角度成為聲波能否成功反射回來的關鍵之一。在測量相對遠的距離時,因目標物擁有不同的反射面,視情況可能發生即使很小的反射角度差距也能夠令接收點產生巨大的位移,這會影響計算成功的機率,所以在遇上這情況時請調整角度。

