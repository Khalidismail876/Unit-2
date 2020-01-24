
MARTIAN DECODER
===========================
A Communication method between Earth, Moon, and Mars in Arduino

Contents
-----
  1. [Planning](#planning)
  2. [Design](#design)
  3. [Development](#development)
  4. [Evalution](#evaluation)
  
  Planning 
  ----------
 
### Definition of the Problem

The year is 2050 and many people want to explore different planets, but one problem that they are facing is they can't communicate with other planets. This is happening due to lack of developing advance communicating tools. We are assigned to make a communicating tool that connect Earth, Moon, and Mars. Since its hard to transfer all the data from Earth to Mars, we made moon be the mediator of Earth and Mars. The people in Mars wanted all their communicaton system as Binary Code and for people in the moon to transfer the informaion from Earth to Binary Code they require the communication system from eath be Morse Code. The reverse has to happen to, Mars people will send binary Code to moon and moon peoeple will convert binary code to Morse code. 

A company called Mantion decided to send astronauts to moon and Mars but they are lucking one important componant to make their trip possible. This componant is communication, for the company to communicate with their astronauts and record all their discoveries and help them with their need, they strongly require a communication system. The owner of the Mantion seeked for communication developers and here he found us. After we had a little interview with him, we gathered that the communication system that he requires has to be developed in a way that his astronauts don't have to struggle learning it. This means that the communication system need to be simple. Another thing that we gathered after talking to him is that his communication system need to have only two buttons to limit number of buttons they will use. HE STATED THAT MORE INFORMATION ABOUT THE CRITERIA OF THE COMMUNICATION SYSTEM WILL ARRIVE. 

### Proposed Solution
As we have gathered enough information about the communication system, we decided to come up with a proposed solution. The communication system need to be created with Arduino rather than Bash, to check the reason why REFERT to Comparison between Bash and Arduino. We create a code that runs like a matrix and you use one of the buttons as to change the letters, numbers, SEND, SPACE, and DELETE. The other button, you use it to select the letter, number, SEND, SPACE, or DELETE when you are writing your message. One way we will make this possible is by using Binary system which will allow us to send those messages. Since the only way that the stations could communicate is by using our communication system, what would happen if the communication system fails? This will cause the astronauts to be out of communication and things could turn out not so great for them. So to avoid any communication system fails, We will install a 100W light on every station which they will turn on eveytime they recieve a message from another station. This will prevent the sender to worry if their messages are recieved or not. MORE SOLUTION WILL COME WHEN ALL THE CRITEA IS DELIVERED.

**Evaluation of Arduino and Bash**

Arduino is more simpler than bash. When it comes to coding, arduino seems to be easier and more understandable, while bash is a little bit complicated. One thing that makes Arduino more easeir is that the coding syntax is more relatable to other coding program like C and C++. But Bash has an advantage over Arduino, which is that you can use it anytime you want since its linked in your terminal. If you compare the varibales in Bash and Arduino, it feels like that Arduino's varaibles is a little bit complicated than Bash. When it comes to this communication system, Arduino has the advantage over Bash and the reason lies on 
the tools that Arduino provides. In arduino, you can find all the tools you need to make a communication system while in Bash you need to do more additional researches and convertions. You can code for arduino while you are checking if the communication system works which makes the programmer have easier time than using Bash. Overall, Arduino is more flexible than Bash when it comes to creating a physical object that is used for communication. 

Design
---------
### The system Diagram that we are creating will be set like figure 1.

![MartialDec](Twobuttons1.jpg)

**Fig. 1.** SYSTEM DIAGRAM 





### The flowchart in Figure 2 will show how the Code that converts English to Morse works. 

![MartialDec](page1.jpg)
![MartialDec](page2.jpg)

**Fig. 2.** English to Morse





### The Flowchart in figure 3 will show how the Code that converts Morse to English works.

![MartialDec](mortoeng.png)

**Fig. 3.** English to Morse




### The Flowchart in figure 3 will show how the Code that converts Binary to English works.

![MartialDec](FCbinToEng.jpg)

**Fig. 4.** Binary to English




### The Flowchart in figure 3 will show how the Code that converts English to Morse works.

![MartialDec](eng-bin.jpg)

**Fig. 5.** English to Binary


Development
--------

This code will print the table below in using LED.
The table in figure 1 give the user three buttons and also provides them the outputs if you press those buttons. For example, 
for the first row of the table, it shows that when you don't press any of the buttons, the output 1 and 2 are both 1 1, the outputs remain the same on the second row but this time you pressed button C. The remaing of the rows will follow the patterns.

![MartialDec](Table.png)

**Fig. 6.** Table which shows which lights are on are which ones are off
``` Arduino
int butA = 13;
int butB = 12;
int butC = 11;
int out1 = 3;
int out2 = 4;

void setup()
{
  pinMode(butA, INPUT);
  pinMode(butB, INPUT);
  pinMode(butC, INPUT);
  pinMode(out1, OUTPUT);
  pinMode(out2, OUTPUT);
}

void loop(){

  if(digitalRead(butA)== LOW && (butB) == LOW && (butB) == LOW){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, HIGH);
  }
  
  if(digitalRead(butA)== LOW && (butB) == LOW && (butB) == HIGH){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, HIGH);
  }
  if(digitalRead(butA)== LOW && (butB) == HIGH && (butB) == LOW){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, LOW);
  }
  if(digitalRead(butA) == LOW && (butB) == HIGH && (butB) == HIGH){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, LOW);
  }
  if(digitalRead(butA) == HIGH && (butB) == LOW && (butB) == LOW){
    digitalWrite(out1, LOW);
    digitalWrite(out2, HIGH);
  }
  if(digitalRead(butA) == HIGH && (butB) == LOW && (butB) == HIGH){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, HIGH);
  }
  if(digitalRead(butA) == HIGH && (butB) == HIGH && (butB) == LOW){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, HIGH);
  }
  if(digitalRead(butA) == HIGH && (butB) == HIGH && (butB) == HIGH){
    digitalWrite(out1, HIGH);
    digitalWrite(out2, HIGH);
  }
}
```


**Traficlight**

WE created a trafic light using arduino and the figures 2 and 3 shows how it works. The lights will change depending on 
the timer that is assigned. for example, the red light will be on for 10 seconds and then it will shift to yellow which will be on for 5 seconds and then it will shift to green which will last for 10 seconds, and the vice versa will happen again from green to yellow and from yellow to red. 

![MartialDec](Pic1.jpg)

**Fig. 7.** This figure shows an image of how the code below will turn out

![MartialDec](Pic2.jpg)

**Fig. 8.** This figure shows an image of how the code below will turn out 

Code for trafic light

``` Arduino
nt redLight = 13; 
int yellowLight = 12;
int greenLight = 11;

void setup() {
  // the code would only run once
  pinMode(redLight, OUTPUT);
  pinMode(yellowLight, OUTPUT);
  pinMode(greenLight, OUTPUT); 
}

void loop() {
  // the code would run repeatedly
  blinkColor(1000, redLight);
  blinkColor(500, yellowLight);
  blinkColor(1000, greenLight);
}

void blinkColor(int t, int color) {
  digitalWrite(color, HIGH);
  delay(t);
  digitalWrite(color, LOW);
  delay(t);

```

**Convertion**

This code will convert decimal to binary but through LED. In figure 2 and 3, it shows how the code below convert 31 into 
Binary number by using lights. We assigned each light to do something while showing a binary number, the assigned actions 
are the lights to be off when they are showing 0 and be on while showing 1. An example is number 7, when the lights are showing number 7 in binary number, the first three lights on the right will be on while the two lights on the right will be off, showing a number like this 00111. So When you run the code, the lights will start as all off which is 00000 and then 
00001 and it will continue showing all decimal numbers from 1 to 31 in binary form using the lights. 

![MartialDec](31dec.png)

**Fig. 9.** This figure shows an image of how to convert 31 decimal to binary

Code for convertion

``` Arduino 

int ALED = 13;

int BLED = 12;

int CLED = 11;

int DLED = 10;

int ELED = 9;




void setup()
{
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(9, OUTPUT);
  
}

void loop()
{
  for (int j = 0; j <= 31; j++){
    delay(1000);
    digitalWrite(ALED, LOW);
    digitalWrite(BLED, LOW);
    digitalWrite(CLED, LOW);
    digitalWrite(DLED, LOW);
    digitalWrite(ELED, LOW);
    
    if (j % 2 != 0){
      digitalWrite(ELED, HIGH);
    }
    if (j % 4 > 1) {
      digitalWrite(DLED, HIGH);
    }
    
    if (j % 8 > 3) {
      digitalWrite(CLED, HIGH);
    }
    if (j % 16 > 7) {
      digitalWrite(BLED, HIGH);
    }
    if (j % 32 > 15) {
      digitalWrite(ALED, HIGH);
    }
      }
}


```
This code will print all the numbers between 0 to 9 by using 
binary system. We have three buttons and using those three
buttons we need to turn the right lights to create the number that 
we want to show.

``` Arduino
int butA = 13;
int butB = 12;
int butC = 11;
int outa = 7;
int outb = 6;
int outc = 5;
int outd = 4;
int oute = 3;
int outf = 2;
int outg = 1;

void setup()
{
  pinMode(butA, INPUT);
  pinMode(butB, INPUT);
  pinMode(butC, INPUT);
  pinMode(outa, OUTPUT);
  pinMode(outb, OUTPUT);
  pinMode(outc, OUTPUT);
  pinMode(outd, OUTPUT);
  pinMode(oute, OUTPUT);
  pinMode(outf, OUTPUT);
  pinMode(outg, OUTPUT);
}

void loop()
{
  bool A = digitalRead(butA);
  bool B = digitalRead(butA);
  bool C = digitalRead(butA);
  
  bool eqa = B || (!A && !C) || (A && C);
    
  digitalWrite(outa, eqa);   
  
  
  bool eqb = !A || (C && B) || (!B && !C);
    
  digitalWrite(outb, eqb);  

  
  bool eqc = (!A && !B) || C || (A && !C);
    
  digitalWrite(outc, eqc);  
  
  bool eqd = (!A && !C) || (!A && B) || (B && !C) || (A && !B && C);
    
  digitalWrite(outd, eqd);  
  
  bool eqe = (!A && !C) ||  (!A && B);
    
  digitalWrite(oute, eqe);  
  
  bool eqf = (A && !B) || !C;
    
  digitalWrite(outf, eqf);  
  
  bool eqg = (A && !C);
    
  digitalWrite(outg, eqg);  
}

```
**The Code for the Metrix**

The code below shows the metrix that the astronauts will use to send messages.
They will need to use two buttons, one for changing characters, and the other 
one for selecting the character. 

``` Arduino
/*This program will print the chosen letters and action through 
selecting the provided String.*/
String text = "";
int index = 0; 
// add all the letters and digits to the keyboard
String keyboard[]={"E", "T", "A", "O", "I", "N", "S", "R", "H", "L", "D", "C", "U", "M", "SENT", "DEL", "SPACE", "F", "P", "G", "W", "Y", "B", "V", "K", "X", "J", "Q", "Z", "O", "1", "2", "3", "4", "5", "6", "7", "8", "9"};
int numOptions = 39; 

void setup()
{
  Serial.begin(9600);
  attachInterrupt(0, changeLetter, RISING);//button A in port 2
  attachInterrupt(1, selected, RISING);//button B in port 3
}

void loop()
{
  Serial.println("Option (Select:butB, Change:butA): " + keyboard[index]);
  Serial.println("Message: "+ text);
  delay(100);
}

//This function changes the letter in the keyboard
void changeLetter(){
  index++;
/* This if function brings the index to 0 whenever the 
numOptions exceeds the fixed number that is used for the coding,
This will prevent the index to not exceed the numOption 
because there will not be anything after the fixed number 
of numOption */  
  if(keyboard == “DEL”){
     int len= text.length();
     text.remove(len-1);
  }

  else if(keyboard == “SEND”){
     Serial.println(“Message sent”);
     text=””:
  }

  else {
      text += key:
  }
  index=0:
}
```

### Code for English to Morse.

This code was designed for the people in both Earth and Moon station. The first thing that the code will require is for the user to put in the message that they need to send by using the two buttons. After the message is send, a light bulb will show a morse code and the message is identical to that of the English one. The Earth or Moon station will recieve the message through light and translate it. 

**As shown in Figure 2 flowchart, code will convert English to Morse** 

```
// This program serves as an input method for the english language, using only 2 buttons. 
// When button A is pressed, the selection in focus is changed, through a rotation in a list. 
// If button B is pressed, the character or action is selected, and catenated to the final word. 
// “SEND” and “DEL” are actions. 
#include <LiquidCrystal.h>

String text = "";
int index = 0; 
// add all the letters and digits to the keyboard
String keyboard[] = {"E", "T", "A", "O", "I", "N", "S", "R", "H", "L", "D", "C", "U", "M", "F", "P", "G", "W", "Y", "B", "V", "K", "X", "J", "Q", "Z", "SPACE", "DEL", "SEND", "0", "1", "2", "3", "4", "5", "6", "7", "8", "9"};

int letter;
int numOptions = 39; 
int Aled = 10;


LiquidCrystal lcd(13, 12, 7, 6, 5, 4);

void setup()
{
  Serial.begin(9600);
  lcd.begin(16, 2);
  attachInterrupt(0, changeLetter, RISING);//button A in port 2
  attachInterrupt(1, selected, RISING);//button B in port 3
  pinMode(Aled, OUTPUT);
  lcd.setCursor(0, 1);
  lcd.print("Starting");
  delay(1000);
  lcd.clear();
  
  
}

void loop()
{
  
  lcd.setCursor(0, 0);
  lcd.print(keyboard[index]);
  
  lcd.setCursor(0, 1);
  lcd.print(text);
  delay(100);
  lcd.clear();
  
}



void changeLetter(){
  index++;
  // The if condition is checking if the user has gone through the whole list
  // If yes, the character selection is reset to the first index (0).
  if (index>numOptions){
  	index=0; 
  } 
}


void selected(){
  String key = keyboard[index];
  // If DEL key is selected, remove last appended char to text
  if (key == "DEL") {
    int len = text.length();
    text.remove(len-1);
  }
  // If SEND is selected, reset the text variable to ""
  else if (key == "SEND") {
    Serial.println("Message sent");
    lcd.clear();
    lcd.print("Message sent");
    
    
    for (int i=0; i<text.length(); i++){
      letter = text[i];
      Serial.print(letter);
      switch (letter) {
    	case 'A':
        	dot();
      		dash( );
        	delay(600000);
            break;
    	case 'B':
     		dash();
        	dot();
        	dot();
        	dot();
        	delay(600000);
            break;
    	case 'C':
      		dash();
         	dot();
      		dash();
         	dot();
        	delay(600000);
            break;
    	case 'D':
       		dash();
          	dot();
          	dot();
        	delay(600000);
            break;
    	case 'E':
         	dot();
        	delay(600000);
            break;
    	case 'F':
        	dot();
        	dot();
     		dash();
        	dot();
        	delay(600000);
            break;
    	case 'G':
     		dash();
     		dash();
       		dot();
        	delay(600000);
            break;
    	case 'H':
       		dot();
       		dot();
       		dot();
       		dot();
        	delay(600000);
            break;
    	case 'I':
       		dot();
       		dot();
        	delay(600000);
            break;
    	case 'J':
        	dot();
     		dash();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case 'K':
     		dash();
        	dot();
     		dash();
        	delay(600000);
            break;
    	case 'L':
        	dot();
     		dash();
       		dot();
       		dot();
        	delay(300000);
            break;
    	case 'M':
     		dash();
     		dash();
        	delay(600000);
            break;
    	case 'N':
     		dash();
        	dot();
        	delay(600000);
            break;
    	case 'O':
     		dash();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case 'P':
       		dot();
     		dash();
     		dash();
       		dot();
        	delay(600000);
            break;
    	case 'Q':
     		dash();
     		dash();
        	dot();
     		dash();
        	delay(600000);
            break;
    	case 'R':
        	dot();
     		dash();
      		dot();
        	delay(600000);
            break;
    	case 'S':
      		dot();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case 'T':
     		dash();
        	delay(600000);
            break;
    	case 'U':
      		dot();
      		dot();
     		dash();
        	delay(600000);
            break;
    	case 'V':
      		dot();
      		dot();
      		dot();
     		dash();
        	delay(600000);
            break;
    	case 'W':
      		dot();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case 'X':
     		dash();
      		dot();
      		dot();
     		dash();
        	delay(600000);
            break;
    	case 'Y':
     		dash();
      		dot();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case 'Z':
     		dash();
     		dash();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case '0':
     		dash();
     		dash();
     		dash();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case '1':
      		dot();
     		dash();
     		dash();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case '2':
      		dot();
      		dot();
     		dash();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case '3':
      		dot();
      		dot();
      		dot();
     		dash();
     		dash();
        	delay(600000);
            break;
    	case '4':
      		dot();
      		dot();
      		dot();
      		dot();
     		dash();
        	delay(600000);
            break;
    	case '5':
      		dot();
      		dot();
      		dot();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case '6':
     		dash();
      		dot();
      		dot();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case '7':
     		dash();
     		dash();
      		dot();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case '8':
     		dash();
     		dash();
     		dash();
      		dot();
      		dot();
        	delay(600000);
            break;
    	case '9':
        	dash();
         	dash();
         	dash();
         	dash();
         	dot();
        	delay(600000);
            break;
      }
    }
    text  = "";
  }else if (key == "SPACE") {
   text+= " ";
  }
  else {
    text += key; // Append char to message
  }
  // Always reset index of array after selection
  index = 0;
}
    
void dot(){
  //in this function blink the light for one second
  Serial.print("I am at dot function");
  digitalWrite(Aled, HIGH);
  delay(100000);
  digitalWrite(Aled, LOW);
  delay(100000);
}
    
void dash(){
  //in this function blink the light for three second
    Serial.print("I am at dash function");

  digitalWrite(Aled, HIGH);
  delay(300000);
  digitalWrite(Aled, LOW);
  delay(100000);  
}
```


### Morse to English

This code will convert Morse message into English. It's used both in Earth and Moon station and it's only used when they recieve a message by either stations. They put in the Morse code into the arduino and the code will bring back the actual message that the sending station wanted to send. The message is displayed on a LCD. 

***As shown in figure 3 flowchart, this code will convert Morse to English***

```
// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 7, 6);
String text = " ";
int butA = 3;
int butB = 2;
int counter = 0;
String letter = " ";

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("Enter morse msg");
  pinMode(butA, INPUT);
  pinMode(butB, INPUT);
  attachInterrupt(1, dot, RISING);
  attachInterrupt(0, dash, RISING);
}

void loop() {
  delay(100);
  counter++;
  if(counter == 20){
    translate();
  }
  else if(counter == 50){
    send();
  }
}
 
void dot()
{
  lcd.clear();
  letter += ".";
  lcd.print(letter);
  counter = 0;
}

void dash()
{
  lcd.clear();
  letter += "-";
  lcd.print(letter);
  counter = 0;
}
  
// IRVIN DO THIS PART
void translate()
{
  //A
  if (letter == " .-"){
    text += "a";
  }
  
  //B
  if (letter == " -..."){
    text += "b";
  }
  
  //C
  if (letter == " -.-."){
    text += "c";
  }
  
  //D
  if (letter == " -.."){
    text += "d";
  }
  
  //E
  if (letter == " ."){
    text += "e";
  }
  
  //F
  if (letter == " ..-."){
    text += "f";
  }
  
  //G
  if (letter == " --."){
    text += "g";
  }
  
  //H
  if (letter == " ...."){
    text += "h";
  }
  
  //I
  if (letter == " .."){
    text += "i";
  }
  
  //J
  if (letter == " .---"){
    text += "j";
  }
  
  //K
  if (letter == " -.-"){
    text += "k";
  }
  
  //L
  if (letter == " .-.."){
    text += "l";
  }
  
  //M
  if (letter == " --"){
    text += "m";
  }
  
  //N
  if (letter == " -."){
    text += "n";
  }
  
  //O
  if (letter == " ---"){
    text += "o";
  }
  
  //P
  if (letter == " .--."){
    text += "p";
  }
  
  //Q
  if (letter == " --.-"){
    text += "q";
  }
  
  //R
  if (letter == " .-."){
    text += "r";
  }
  
  //S
  if (letter == " ..."){
    text += "s";
  }
  
  //T
  if (letter == " -"){
    text += "t";
  }
  
  //U
  if (letter == " ..-"){
    text += "u";
  }
  
  //V
  if (letter == " ...-"){
    text += "v";
  }
  
  //W
  if (letter == " .--"){
    text += "w";
  }
  
  //X
  if (letter == " -..-"){
    text += "x";
  }
  
  //y
  if (letter == " -.--"){
    text += "y";
  }
  
  //Z
  if (letter == " --.."){
    text += "z";
  }
  
  //1
  if (letter == " .----"){
    text += "1";
  }
  
  //2
  if (letter == " ..---"){
    text += "2";
  }
  
  //3
  if (letter == " ...--"){
    text += "3";
  }
  
  //4
  if (letter == " ....-"){
    text += "4";
  }
  
  //5
  if (letter == " ....."){
    text += "5";
  }
  
  //6
  if (letter == " -...."){
    text += "6";
  }
  
  //7
  if (letter == " --..."){
    text += "7";
  }
  
  //8
  if (letter == " ---.."){
    text += "8";
  }
  
  //9
  if (letter == " ----."){
    text += "9";
  }
  
  //0
  if (letter == " -----"){
    text += "";
  }
  
  //.
  if (letter == " .-.-.-"){
    text += ".";
  }
  
  //,
  if (letter == " --..--"){
    text += ",";
  }
  
  //?
  if (letter == " ..--.."){
    text += "?";
  }
  lcd.setCursor(0,1);
  lcd.print(text);
  letter = " ";
}

void send()
{
  lcd.clear();
  lcd.print(text);
  text = " ";
  letter = " ";
}


```


### English to Binary

This code will translate English to Binary, and its only used in both Mars and Moon stations. Either Mars or Moon station will use this code to send a message to each other. This message will first be written down in English, then the program will convert it into Binary message and send it to either one of them. 

***As shown in Figure 5 flowchart, this code will convert English messages into Binary. 

```
#include <LiquidCrystal.h>
int index = 0; 
// add all the letters and digits to the keyboard
String keyboard[]={"SEND","A", "B","C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z", "0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "SEND", "DEL", "SPACE"};
String text = "";
int numOptions = 40;
int ledPort=8;
int ledPort2=9;
char letters;



// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 7, 6, 5, 4);

void setup() {
  // set up the LCD's number of columns and rows:
  Serial.begin(9600);
  lcd.begin(16,2);
  // Print a message to the LCD.
  attachInterrupt(0, changeLetter, RISING);//button A in port 2
  attachInterrupt(1, selected, RISING);//button B in port 3
  pinMode(ledPort, OUTPUT);
  pinMode(ledPort2, OUTPUT);
  
   
 
  
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print(keyboard[index]);
  lcd.setCursor(0, 1);
  lcd.print(text);
  delay(100);
  digitalWrite(13, HIGH);
}

//This function changes the letter in the keyboard
void changeLetter(){
  static unsigned long last_interrupt_time = 0;
  unsigned long interrupt_time = millis();
  if (interrupt_time - last_interrupt_time > 200)
  {
  
    last_interrupt_time = interrupt_time;// If interrupts come faster than 200ms, assum
    index++;
      //check for the max row number
    if(index==numOptions){
      index=0; //loop back to first row
    } 
 }
}

//this function adds the letter to the text or send the msg
void selected(){
  static unsigned long last_interrupt_time = 0;
  unsigned long interrupt_time = millis();
  if (interrupt_time - last_interrupt_time > 200)
  {
  
    last_interrupt_time = interrupt_time;// If interrupts come faster than 200ms, assum
    
    String key = keyboard[index];
    if (key == "DEL")
    {
      int len = text.length();
      text.remove(len-1);
    }
    else if(key == "SEND")
    {
      convertbin();
      text="";
    }
    else if(key == "SPACE")
    {
     text += " ";
    }else{
      text += key;
    }
    index = 0; //restart the index
  }
  
}

void convertbin(){

// if 2 lights ON = 1, if 1 light ON = 0
// if 2 lights OFF break
// if 1 light ON 1s  = 0, if 1 lights ON 2s = 00…
//  if 2 light ON 1s  = 1, if 1 lights ON 2s = 11…
  
  String code; 
  for(int i=0; i<text.length();i++){
    letters = text[i];
    Serial.print(letters);
      switch (letters) {

         case 'A':
           //code  = "001010";

         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         
         break;
      
       case 'B':
         //code = "001011"; 
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
         
       case 'C':
         //code = "001100";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
         
       case 'D': 
         //code = "001101";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
         
       case 'E': 
         //code = "001110";
          digitalWrite(ledPort, LOW);
          digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'F': 
         //code = "001111";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
       case 'G': 
         //code = "010000";
          digitalWrite(ledPort, LOW);
          digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'H': 
         //code = "010001";
          digitalWrite(ledPort, LOW);
          digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
     
       case 'I': 
         //code = "010010";
          digitalWrite(ledPort, LOW);
          digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'J': 
         //code = "010011";
          digitalWrite(ledPort, LOW);
          digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'K': 
         //code = "010100";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'L': 
         //code = "010101";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'M': 
         //code = "010110";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'N':
         //code = "010111"; 
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'O':
         //code = "011000";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'P':
         //code = "011001";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'Q':
         //code = "011010";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'R':
         //code = "011011";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'S':
        //code = "011100";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'T':
        //code = "011101";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
    
       case 'U':
         //code = "011110";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'V':
         //code= "011111";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'W':
         //code = "100000";
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'X':
         //code = "100001";
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'Y':
         //code = "100010";
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case 'Z':
         //code = "100011"; 
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
       
       case '0': 
         //code = "000000";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
        
       case '1': 
         //code = "000001"; 
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '2': 
         //code = "000010";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '3': 
         //code = "000011";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '4': 
         //code = "000100";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);        
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '5': 
       //code = "000101";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '6': 
         //code = "000110";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '7': 
         //code = "000111";
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, LOW);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000); 
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
      
       case '8': 
        //code = "001000";
        digitalWrite(ledPort, LOW);
        digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;
                      
       case '9': 
        //code = "001001";  
      digitalWrite(ledPort, LOW);
      digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
       digitalWrite(ledPort, HIGH);
       digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, HIGH);
         digitalWrite(ledPort2, HIGH);
         delay(200000);
         digitalWrite(ledPort, LOW);
         digitalWrite(ledPort2, LOW);
         delay(200000);
         break;

         case 'space':
           //code = 000000
           digitalWrite(ledPort2, LOW);
           digitalWrite(ledPort2, LOW);
           delay(500000);



      }
  }
}


```


### Binary to English

This code will convert the Message encoded with Binary to English. This code will also be used in Moon and Mars stations. After recieving a message from either Mars or Moon to the other one, this code will be used to translate that received code into English. 

***As shown in Figure 4 flowchart, this code will convert Binary into English***

```
// include the library code:
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 9, 8);
int but1 = 3;
int but2 = 2;


String letter = "";

String msg = "";



void setup() {
  Serial.begin(9600);
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  
  pinMode(but1, INPUT);
  pinMode(but2, INPUT);
  
  attachInterrupt(0, add0, RISING);
  attachInterrupt(1, add1, RISING);
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 0);
  lcd.print("M: " + msg);
  
  lcd.setCursor(0, 1);
  lcd.print("Input: " + letter);
  
  delay(100);
  
  if (letter.length() == 6) {

    storeChar(letter);
    letter = "";
    clearDisplay();
    
  }
}


// FUNCTIONS -----------------------------

void clearDisplay() {
  lcd.clear();
}

void add0() {
  letter += "0";
}


void add1() {
  letter += "1";
}

void storeChar(String character) {
  
  if (character == "000000") {
    msg += "0";
  } else if (character == "000001") {
    msg += "1";
  } else if (character == "000010") {
    msg += "2";
  } else if (character == "000011") {
    msg += "3";
  } else if (character == "000100") {
    msg += "4";
  } else if (character == "000101") {
    msg += "5";
  } else if (character == "000110") {
    msg += "6";
  } else if (character == "000111") {
    msg += "7";
  } else if (character == "001000") {
    msg += "8";
  } else if (character == "001001") {
    msg += "9";
  } else if (character == "001010") {
    msg += "A";
  } else if (character == "001011") {
    msg += "B";
  } else if (character == "001100") {
    msg += "C";
  } else if (character == "001101") {
    msg += "D";
  } else if (character == "001110") {
    msg += "E";
  } else if (character == "001111") {
    msg += "F";
  } else if (character == "010000") {
    msg += "G";
  } else if (character == "010001") {
    msg += "H";
  } else if (character == "010010") {
    msg += "I";
  } else if (character == "010011") {
    msg += "J";
  } else if (character == "010100") {
    msg += "K";
  } else if (character == "010101") {
    msg += "L";
  } else if (character == "010110") {
    msg += "M";
  } else if (character == "010111") {
    msg += "N";
  } else if (character == "011000") {
    msg += "O";
  } else if (character == "011001") {
    msg += "P";
  } else if (character == "011010") {
    msg += "Q";
  } else if (character == "011011") {
    msg += "R";
  } else if (character == "011100") {
    msg += "S";
  } else if (character == "011101") {
    msg += "T";
  } else if (character == "011110") {
    msg += "U";
  } else if (character == "011111") {
    msg += "V";
  } else if (character == "100000") {
    msg += "W";
  } else if (character == "100001") {
    msg += "X";
  } else if (character == "100010") {
    msg += "Y";
  } else if (character == "100011") {
    msg += "Z";
  } else if (character == "100100") {
    msg += " ";
  } else if (character == "111111") {
    clearDisplay();
    lcd.print("Clearing");
    lcd.setCursor(0, 1);
    lcd.print("Message");
    delay(3000);
    msg = "";
    clearDisplay();
  } else {
    clearDisplay();
    lcd.print("Error.");
    lcd.setCursor(0, 1);
    lcd.print("Wrong input.");
    delay(3000);
    clearDisplay();
  }
}
 


```

### Usibility
According to Techopedia [1] "Usability is the degree of ease with which products such as software and Web applications can be used to achieve required goals effectively and efficiently."
### Discoveribility Feedback
To understand Discoveribility Feedback you need to first understand the words individually and then it will make sense when 
you combine them together. Discoveribility is the idea of "What do I do", this happens when you encounter a product, system or an object. Understanding what to do with a product or system is a major thing for the developers who want to produce a new
product into the world, and that is how Discoveribilty is important. Feedback comes when you make your product or create your new system. The developers need to understand what happened to their new product or their new system, and that is when feedback comes. It informs everything that happened to their products and how they need to improve it in the future for their clients. Discoveribility Feedback is the process of coming up with an idea then making it possible through a series of feedback that would improve the product. 



Evaluation
-----------
(coming soon )


## Reference
-----------

[1] “What Is Usability? - Definition from Techopedia.” Techopedia.com, https://www.techopedia.coum/definition/4919/usability.
[2] "What is Discoveribility Feeback - Definition from envatotuts+." webdesign.tutsplus.com, https://webdesign.tutsplus.com/articles/discoverability-and-feedback-in-web-design--cms-25487.



