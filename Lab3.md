
# 嵌入式系統 - 實作3: 使用超音波感測器 + LED控制, 常用的C語言程式介紹

## Lab 3-1: Ultrasonic Sensor (3-pin) + 測距 (以公分顯示即可) + RS232 Output

![88](https://user-images.githubusercontent.com/89717270/134792769-7eabd026-aaa9-4aa3-9968-621f0fa25cb6.gif)

![chrome-capture](https://user-images.githubusercontent.com/89717270/134793142-4b1ba02e-e7a9-4f89-b46a-6eb0acbe36cd.gif)


程式
````C
int inches = 0;

int cm = 0;

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT); 
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  
  return pulseIn(echoPin, HIGH);
}

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  cm = 0.01723 * readUltrasonicDistance(7, 7);
  
  inches = (cm / 2.54);
  Serial.print(inches);
  Serial.print("in, ");
  Serial.print(cm);
  Serial.println("cm");
  delay(100);
}
````

## Lab 3-2: 超音波感測器 + LED (紅色LED:亮<70cm, 緑色LED: 亮>270cm, 藍色LED:亮, 介於70cm ~ 270cm之間) + RS232 Output

![chrome-capture (2)](https://user-images.githubusercontent.com/89717270/134793365-7dea43b4-8966-4d7a-8f2c-925102cc37a4.gif)

程式
````C
const int Red = 12;
const int Green = 8;
const int Blue = 10;

int inches = 0;

int cm = 0;

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT); 
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  return pulseIn(echoPin, HIGH);
}

void changColor(int type){
  analogWrite(Red,0);
  analogWrite(Green,0);
  analogWrite(Blue,0);
  switch (type){
    case 1:
    analogWrite(Red,255);
    analogWrite(Green,0);
    analogWrite(Blue,0);
    break;
    case 2:
    analogWrite(Red,0);
    analogWrite(Green,255);
    analogWrite(Blue,0);
    break;
    case 3:
    analogWrite(Red,0);
    analogWrite(Green,0);
    analogWrite(Blue,255);
    break;
  }
}

void setup()
{
  Serial.begin(9600);

}

void loop()
{
  
  cm = 0.01723 * readUltrasonicDistance(7, 7);

  if(cm <70)
  {
    changColor(1);
  }
  else if(cm>= 270)
  {
    changColor(2);
  }
  else if(cm>= 70&& cm<270)
  {
    changColor(3);
  }
  
  inches = (cm / 2.54);
  Serial.print(inches);
  Serial.print("in, ");
  Serial.print(cm);
  Serial.println("cm");
  delay(100); 
}
````
