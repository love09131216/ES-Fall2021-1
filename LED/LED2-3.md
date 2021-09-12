# 實作2-3, 讓你的RGB LED燈全彩模組也可會"呼吸", LED顏色變化是否有像"呼吸的效果"和示波器的波形有什麼關連性
![image](https://user-images.githubusercontent.com/89329219/132970804-e108a3a2-0c53-4bdf-9bcf-7d7cbe6c0ac0.png)
````C
int R = 9;
int G = 10;
int B = 11;

int DR = 2;
int DG = 4;
int DB = 7;

void setup()
{
  pinMode(13, OUTPUT); // pin 13
  
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
  
  pinMode(DR, OUTPUT);
  pinMode(DG, OUTPUT);
  pinMode(DB, OUTPUT);   
}

void loop()
{
  // digitalWrite: 2 state (i.e., 0, 1) Only
  digitalWrite(13, 1); // LED @ pin 13, ON
  
  delay(1000); 
  
  digitalWrite(DR, 1);
  digitalWrite(DG, 0);
  digitalWrite(DB, 0);
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 1);
  digitalWrite(DB, 0);  
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 0);
  digitalWrite(DB, 1);  
  delay(1000);

  digitalWrite(13, 0); // OFF
  digitalWrite(DR, 0); // OFF
  digitalWrite(DG, 0); // OFF
  digitalWrite(DB, 0); // OFF  
  delay(1000);
  
  // analogWrite: The brightness can be adjusted with 256 levels
  for (int i = 0; i<= 255; i++)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10);
  } // from dark to bright 

  for (int i = 255; i>= 0; i--)
  {
  	analogWrite(R, i);
	analogWrite(G, 0);
	analogWrite(B, 0);
    delay(10); // 10ms = 0.01s
  }  // from bright to dark
  delay(1000);

}
````
