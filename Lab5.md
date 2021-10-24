# 嵌入式系統 - 實作5: Servo伺服馬達, 溫度感應器 + LCD 顯示器

## Lab 5-1 請使用兩個伺服馬達同步從 0 度逐步掃描到 180 度之後再逐步掃描回0度, 每步的間隔時間為50ms (0.05秒), 細節請參考以下Demo.
![chrome-capture](https://user-images.githubusercontent.com/89717270/138579052-bc4eab39-6be1-4c02-b4b6-f08ec98235c3.gif)

CODE
````c
#include <Servo.h>

int pos = 0;

Servo servo_9;

void setup()
{
  servo_9.attach(9, 500, 2500);
  
}

void loop()
{
// 從 0 到 180 度逐步掃描伺服, 1度/步
  for (pos = 0; pos <= 180; pos += 1) {

    servo_9.write(pos);
       

    delay(50); // 等50ms (0.05秒)
  }
  
  for (pos = 180; pos >= 0; pos -= 1) {
// 從 180 到 0 度逐步掃描伺服, 1度/步
    servo_9.write(pos);
        

    delay(50); // 等50ms (0.05秒)
  }
}
````
