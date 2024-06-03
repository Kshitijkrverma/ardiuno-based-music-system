# ardiuno-based-music-system
int ledPin1 = 7; 
int trigPin1 = A0; 
int echoPin1 = A1; 
int trigPin2 = A3; 
int echoPin2 = A2; 
void setup() 
{
//I declare whether I'm using the pins for input/output    
pinMode(7,OUTPUT);   
pinMode(A0,OUTPUT);   
pinMode(A1,INPUT);   
pinMode(A3,OUTPUT);   
pinMode(A2,INPUT);   
} 
int sp = 7; 
//Speaker Pin 
int tp1 = A0; 
int tp2 = A3;
//Trigger Pin 
int ep1 = A1; 
int ep2 = A2;
// Echo Pin 
int c = 520; 
int d = 590; 
int e = 660; 
int f = 700;     
//These are the frequency       
int g = 790;     
//values of the different notes 
int a = 900;    
int b = 1000; 
int c2 = 1100; 
void loop() 
{     
//This is the main loop, that keeps repeating   
int notes[] = {c,d,e,f,g,a,b,c2}; 
//An array storing all the notes. It's kind of like a dictionary.   
long duration, distance; 
//Variables to store the values of time and length   
digitalWrite(tp1,LOW);   
delayMicroseconds(2);            
digitalWrite(tp1,HIGH);      //This area sends out a pulse from the trigger   
delayMicroseconds(5);   
digitalWrite(tp1,LOW);                   
duration = pulseIn(ep1, HIGH); //The echo is recieved, and saved as the duration   
distance = (duration/2)/29.1; // We convert the time into distance in centimeters, using the speed of sound and other factors.   
if(distance>0&amp;&amp;distance&lt;40)   
{     
if(distance>0&amp;&amp;distance&lt;5)      //For a distance between 4 and 7, it plays C for 100 milliseconds       
tone(sp,notes[0],200);     
else        
if(distance>5&amp;&amp;distance&lt;10)         
tone(sp,notes[1],200);      //For a distance between 8 and 11, it plays D for 100 milliseconds     
else       
if(distance>10&amp;&amp;distance&lt;15)         
tone(sp,notes[2],200);      //For a distance between 12 and 15, it plays E for 100 milliseconds     
else       
if(distance>15&amp;&amp;distance&lt;20)         
tone(sp,notes[3],200);      //For a distance between 16 and 19, it plays F for 100 milliseconds     
else       
if(distance>20&amp;&amp;distance&lt;25)         
tone(sp,notes[4],200);      //For a distance between 20 and 23, it plays G for 100 milliseconds     
else       
if(distance>25&amp;&amp;distance&lt;30)         
tone(sp,notes[5],200);      //For a distance between 24 and 27, it plays A for 100 milliseconds     
else       
if(distance>30&amp;&amp;distance&lt;35)         
tone(sp,notes[6],200);      //For a distance between 28 and 31, it plays B for 100 milliseconds     
else       
if(distance>35&amp;&amp;distance&lt;40)         
tone(sp,notes[7],200);      //For a distance between 32 and 35, it plays high C for 100 milliseconds   
}      
digitalWrite(tp2,LOW);   
delayMicroseconds(2);            
digitalWrite(tp2,HIGH);      //This area sends out a pulse from the trigger   
delayMicroseconds(5);   
digitalWrite(tp2,LOW);                    
duration = pulseIn(ep2, HIGH); //The echo is recieved, and saved as the duration   
distance = (duration/2)/29.1; // We convert the time into distance in centimeters, using the speed of sound and other factors.   
if(distance>0&amp;&amp;distance&lt;40)   
{     
if(distance>0&amp;&amp;distance&lt;5)      //For a distance between 4 and 7, it plays C for 100 milliseconds       
tone(sp,notes[0],100);     
else        
if(distance>5&amp;&amp;distance&lt;10)         
tone(sp,notes[1],100);      //For a distance between 8 and 11, it plays D for 100 milliseconds     
else       
if(distance>10&amp;&amp;distance&lt;15)         
tone(sp,notes[2],100);      //For a distance between 12 and 15, it plays E for 100 milliseconds     
else       
if(distance>15&amp;&amp;distance&lt;20)         
tone(sp,notes[3],100);      //For a distance between 16 and 19, it plays F for 100 milliseconds     
else       
if(distance>20&amp;&amp;distance&lt;25)         
tone(sp,notes[4],100);      //For a distance between 20 and 23, it plays G for 100 milliseconds    
else       
if(distance>25&amp;&amp;distance&lt;30)         
tone(sp,notes[5],100);      //For a distance between 24 and 27, it plays A for 100 milliseconds     
else       
if(distance>30&amp;&amp;distance&lt;35)         
tone(sp,notes[6],100);      //For a distance between 28 and 31, it plays B for 100 milliseconds     
else       
if(distance>35&amp;&amp;distance&lt;40)         
tone(sp,notes[7],100);      //For a distance between 32 and 35, it plays high C for 100 milliseconds   
}  
}
