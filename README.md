Feedback Nov 28 (you can delete this section later it will remain in the history)

|No.|How to improve        |
|-|------------- |
|①| The definition of the problem needs some work. You described the context very creatively, now invent a ficticious client. Answer the questions: Who is the client? Why is the product being developed? Then you can add at least 5 success criteria that are measurable. 
|②|Add the proposed solution justifying the choices of software (C) and tools (Arduino). here you can include your homework on comparing BASH and Arduino's C. Also add measurable success criteria.
|③| Under the development section, you are including all the source code for the programs. It is better if you include only small parts of the code that are new to you or that show an important algorithm. This is because the source code is anyway in the repo so no need to repeat. 

**For example:** The code below shows how to read the status of a button connected to port 13 in the Arduino:
```.c
bool A = digitalRead(13);
```
Note that the variable A was created of type Bool since the input is binary data.|

|No.|How to improve        |
|-|------------- |
|④| Your evidence of progress is limited to one picture without caption or description. Add figure caption to your figures and then explain what you see in them. Figures are quite ambiguous by themselves.| 

**For example:**

<img src="Pic1.jpg" width="50%" height="50%">


**Fig. 2.** Circuit used to create a traffic light system with 3 LEDs.

As shown in **Fig. 2**, the circuit used for... which includes... this demonstrates that

|No.|How to improve        |
|-|------------- |
|⑤| Keep working on the development section, adding references when you used online sources. I have added the Reference section at the end of this document. Use the references in the text. See example below.| 


----

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

Design
---------
(coming soon)



Development
--------

This code will print the table below in using LED

![MartialDec](Table.png)

**Fig. 1.** Table which shows which lights are on are which ones are off
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


This code will convert decimal to binary but through LED


![MartialDec](Pic1.jpg)

**Fig. 2.** This picture shows an image of how the code below will turn out
![MartialDec](Pic2.jpg)

**Fig. 3.** This picture shows an image of how the code below will turn out 

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

```
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
```
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
### Usibility
According to Techopedia [1] "Usability is the degree of ease with which products such as software and Web applications can be used to achieve required goals effectively and efficiently."
### Discoveribility Feedback
(need to understand more)



Evaluation
-----------
(coming soon )


## Reference
-----------

[1] “What Is Usability? - Definition from Techopedia.” Techopedia.com, https://www.techopedia.com/definition/4919/usability.


