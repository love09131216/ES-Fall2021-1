# 實作2-1, analogWrite(): 並且觀查LED亮度變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?
## 全彩模組
![4dabe03fb2547cee471236bdb4dc1d95_30204203954226](https://user-images.githubusercontent.com/89329219/132114859-9b72644d-912a-450e-8a8e-ed84ac35e49b.jpg)

![image](https://user-images.githubusercontent.com/89329219/132114727-4ce71b57-883d-4f29-85a8-cecb62ea9b45.png)
````C
void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
````
# 實作2-2, RGB LED燈全彩模組, 分別讓LED輪流表現正紅、正綠、正藍，三個顏色，時間間隔1秒鐘。
![image](https://user-images.githubusercontent.com/89329219/132114668-6458b64d-56e2-48a3-9c0e-151f7364b2fb.png)
## int R = 9   int G = 10   int B = 11;
````C
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
![image](https://user-images.githubusercontent.com/89329219/132115140-cc835314-45aa-424d-a7b9-aa057e561889.png)

