# 實作2-4 analogRead(), 1024解析度 (i.e.,10-bit): 可變電阻 + 序列監視器與輸出; 當你改變可變電阻的阻值(e.g., 10K-ohm)時，序列監視器輸出的數值有什麼改變?
![image](https://user-images.githubusercontent.com/89329219/132971523-cf3086ce-69da-4490-9c08-ed8f1f467bb0.png)
````C
int sensorValue = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);

}

void loop()
{
  // read the input on analog pin 0:
  sensorValue = analogRead(A0);
  // print out the value you read:
  Serial.println(sensorValue);
  delay(10); 
}
````
## 加上LED
![image](https://user-images.githubusercontent.com/89329219/132971760-9e3654f1-bce8-4ee8-9539-ee366d749d5e.png)
