# Arduino_linesensor

### 7번 핀과 GND 연결

```언어
#define ledPin 13   // LED는 디지털 핀 13에 연결됨
#define inPin 7     // pusbutton은 디지털 핀 7에 연결됨 
int val = 0;        // 읽은 값을 저장할 변수

void setup() {
  pinMode(ledPin, OUTPUT);      // 디지털 핀 13을 출력으로 설정
  pinMode(inPin, INPUT);        // 디지털 7을 입력으로 설정
  Serial.begin(9600);
}


void loop() {
  val = digitalRead(inPin);     //입력 핀으로부터 읽기  , 7번 핀에서 voc 연결 또는 GND 연결

  Serial.print("Input data ");
  Serial.println(val);
  digitalWrite(ledPin, val);    // LED 를 버튼의 값으로 설정
}
```

### 7번 핀과 5V 연결

```언어
#define ledPin 13  // LED는 디지털 핀 13에 연결됨
int linesensor_data[5] = {0,0,0,0,0};   //읽은 값을 저장할 변수
int linesensor_pin[5] = {2,3,4,5,6};    //int형 배열
  
void setup() {
  int i;
  pinMode(ledPin, OUTPUT);    //디지털 핀 13을 출력으로 설정
  
  for(i=0;i<5;i++)
  {
      pinMode(linesensor_pin[i], INPUT);   //디지털 linesensor_pin들을 입력으로 설정
  }
  
  Serial.begin(9600);
}

void loop() {
  int i;
  for(i=0;i<5;i++)
  {
      linesensor_data[i] = digitalRead(linesensor_pin[i]);      // 디지털 linesensor_pin들로 부터 읽음
  }

  Serial.print("Input data =");
  for(i=0;i<5;i++)
  {
      Serial.print(linesensor_data[i]);
      Serial.print(" ");
  }
  Serial.println(" ");
}
```

### 라인센서와 GND,5V 연결

```언어
#define ledPin 13 //LED는 디지털 핀 13에 열결됨
int linesensor_data[5] = {0,0,0,0,0};
int linesensor_pin[5] = {2, 3, 4, 5, 6};


void setup() {
  int i;
  pinMode(ledPin, OUTPUT); //디지털 핀 13을 출력으로 설정
  for (i=0;i<5;i++);
  {
    pinMod(linesensor_pin[1], INPUT);
  }
  Serial.begin(9600);  
}

void loop() {
  int i;
  for(i=0;i<5;i++)
  {
    linesensor_data[i] = digitalRead(linesensor_pin[1]);
  }
  Serial.print("Input data ");
  for(i=0;i<5;i++)
  {
    Serial.print(linesensor_data[1]);
    Serial.print("  ");
  }
  Serial.print("  ")
}
```
