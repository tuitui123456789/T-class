
# 嵌入式系統 - 實作4: 七段顯示器, LCD 顯示器 + 超音波感測器 

## Lab 4-1 用七段顯示器來顯示數字"8."
![chrome-capture (2)](https://user-images.githubusercontent.com/89717270/137610071-62caad73-6efa-4e0b-a0eb-a17adda37d09.gif)

程式
````C
void setup()
{
for(int x = 1; x < 9; x++) {
pinMode(x,OUTPUT);
}
}

void seg71(int a, int b, int c, int d, int e, int f, int g, int h)
{
digitalWrite(1, a);
digitalWrite(2, b);
digitalWrite(3, c);
digitalWrite(4, d);
digitalWrite(5, e);
digitalWrite(6, f);
digitalWrite(7, g);
digitalWrite(8, h);
delay(500);
}

void loop()
{
seg71(0, 0, 0, 0, 0, 0, 0, 0); 
seg71(1, 1, 1, 1, 1, 1, 1, 1); 
}
````

## Lab 4-2 如下圖的Demo, 用七段顯示器, 顯示 . →1→ ... → 9 → 0 → 全滅, 狀態改變的間隔時間為0.5秒
![chrome-capture (1)](https://user-images.githubusercontent.com/89717270/137610014-9d2ad57b-1b0b-401d-a17b-42d38269b5d2.gif)

程式
````C
void setup()
{
  for(int x = 1; x < 9; x++)
  {
  	pinMode(x,OUTPUT);
  }
}

void seg71(int a, int b, int c, int d, int e, int f, int g, int h)
{
  digitalWrite(1, a);
  digitalWrite(2, b);
  digitalWrite(3, c);
  digitalWrite(4, d);
  digitalWrite(5, e);
  digitalWrite(6, f);
  digitalWrite(7, g);
  digitalWrite(8, h);
  delay(500);
}

void loop()
{
  seg71(0, 0, 0, 0, 0, 0, 0, 0); 
  seg71(1, 1, 1, 1, 1, 1, 0, 1); 
  seg71(0, 1, 1, 0, 0, 0, 0, 1); 
  seg71(1, 1, 0, 1, 1, 0, 1, 1); 
  seg71(1, 1, 1, 1, 0, 0, 1, 1); 
  seg71(0, 1, 1, 0, 0, 1, 1, 1); 
  seg71(1, 0, 1, 1, 0, 1, 1, 1); 
  seg71(1, 0, 1, 1, 1, 1, 1, 1); 
  seg71(1, 1, 1, 0, 0, 0, 0, 1); 
  seg71(1, 1, 1, 1, 1, 1, 1, 1); 
  seg71(1, 1, 1, 1, 0, 1, 1, 1); 
}
````

## Lab 4-3 LCD顯示"Hello" + 你的英文名字 (e.g., "Hello TUI")
![chrome-capture (3)](https://user-images.githubusercontent.com/89717270/137610428-523fe16e-d9bc-42f1-83b1-9436dc9d6502.gif)

程式
````C
// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("Hello, TUI!");
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(millis() /100);
}
````
