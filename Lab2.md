
# 嵌入式系統 - 實作2: 會呼吸的RGB LED, 按鍵控制, 狀態輸出

## 1 實作2-1, analogWrite(): 並且觀查LED亮度變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?
![image](https://user-images.githubusercontent.com/89717270/132114578-fe87ad79-35eb-4e23-9677-bba42a8449c9.png)

程式
````c
void setup()
{
  pinMode(13, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(1000); 
 
  digitalWrite(13, LOW);
  delay(1000); 
}
````

## 實作2-2, RGB LED燈全彩模組, 分別讓LED輪流表現正紅、正綠、正藍，三個顏色，時間間隔1秒鐘。並且觀查LED顏色和波形或是電壓有什麼關連性? 可將個人說明在更新GitHub時一起加入
![image](https://user-images.githubusercontent.com/89717270/132115021-b14f4842-e892-4884-947d-8353a85049fd.png)

程式
````c
int R = 9;
int G = 10;
int B = 11;

void setup()
{
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
}

void loop()
{
	analogWrite(R, 255);
	analogWrite(G, 0);
	analogWrite(B, 0);
  	delay(1000);
	analogWrite(R, 0);
	analogWrite(G, 255);
	analogWrite(B, 0);
  	delay(1000);
	analogWrite(R, 0);
	analogWrite(G, 0);
	analogWrite(B, 255);
  	delay(1000);  
}
````

## 實作2-3, 讓你的RGB LED燈全彩模組也可會"呼吸", LED顏色變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?
![image](https://user-images.githubusercontent.com/89717270/132971483-a2f6b2f2-bc75-47fb-be6a-6a9970a4af90.png)

程式
````c
int brightness = 0;
int Red = 9;
int Blue = 11;
int Green = 10;
void setup()
{
  pinMode(Red, OUTPUT);
  pinMode(Blue, OUTPUT);  
  pinMode(Green, OUTPUT);  
  
  Serial.begin(9600); 
}
void loop()
{
  Serial.println("START");

  for (brightness = 0; brightness <= 255; brightness += 5) {
    analogWrite(Red, brightness);
    delay(50); 
  }
  for (brightness = 255; brightness >= 0; brightness -= 5) {
    analogWrite(Red, brightness);
    delay(50); 
  }
  delay(1000); 
  

  for (brightness = 0; brightness <= 255; brightness += 5) {
    analogWrite(Blue, brightness);
    delay(50); 
  }
  for (brightness = 255; brightness >= 0; brightness -= 5) {
    analogWrite(Blue, brightness);
    delay(50); 
  }  
  delay(1000); 
  

  for (brightness = 0; brightness <= 255; brightness += 5) {
    analogWrite(Green, brightness);
    delay(50); 
  }
  for (brightness = 255; brightness >= 0; brightness -= 5) {
    analogWrite(Green, brightness);
    delay(50); 
  }  
  delay(1000);   
  Serial.println("END");  
}
````

## 實作2-4 analogRead(), 1024解析度 (i.e.,10-bit): 可變電阻 + 序列監視器與輸出; 當你改變可變電阻的阻值(e.g., 10K-ohm)時，序列監視器輸出的數值有什麼改變? 數值又有什麼意義呢?
![image](https://user-images.githubusercontent.com/89717270/132971858-fce80a39-b456-4b9d-95e7-88ba745c4c7c.png)

程式
````c
void setup() {
  Serial.begin(9600);
}

void loop() {
  // read the input on analog pin 0:
  int sensorValue = analogRead(A0);
  // Convert the analog reading (which goes from 0 - 1023) to a voltage (0 - 5V):
  float voltage = sensorValue * (5.0 / 1023.0);
  // print out the value you read:
  Serial.println(voltage);
}
````
