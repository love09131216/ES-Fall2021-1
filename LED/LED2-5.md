# B5 實作2-5: 按下按鍵, Green LED亮 & Red LED滅; 放開按鍵, Green LED滅 & Red LED亮 (思考方向: digitalRead(), digitalWrite(): 按鍵 +序列輸出 + LED), (互動5) 
![image](https://user-images.githubusercontent.com/89329219/134792142-019fb639-d32c-4242-bd49-730ceb6ae8bc.png)
````C
int buttonState = 0;
int GLED = 13;
int RLED = 8;

void setup()
{
  pinMode(2, INPUT);
  pinMode(GLED, OUTPUT); // GREEN
  pinMode(RLED, OUTPUT); // RED    
}

void loop()
{
  // read the state of the pushbutton value
  buttonState = digitalRead(2);
  // check if pushbutton is pressed.  if it is, the
  // buttonState is HIGH
  if (buttonState == HIGH) {
    // turn LED on  
    digitalWrite(GLED, HIGH);
    digitalWrite(RLED, LOW);    
  } else {
    // turn LED off    
    digitalWrite(GLED, LOW);
    digitalWrite(RLED, HIGH);
  }
  delay(10); // Delay a little bit to improve simulation performance
}
````
