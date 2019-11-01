# garbagemonitoringsystem

To read about his project https://medium.com/@iomkarsurve/garbage-monitoring-system-overcome-overflowing-dustbins-could-this-be-future-907303bc87ef?postPublishedType=initial
code for garbage monitoring system
In this article i am going to talk about my first projects i made in field of internet of things (IOT).
India is facing a large problem of garbage handling, when you drive around the city of Mumbai you will find garbage dustbins overflowing. Many places follow a fixed timing for garbage collection, some at mornings (like where I live) some at evening and few places have garbage collection both times.
Lets take example of a park , on a crowded day dustbins in park will get full but as the timing to pick up trash is fixed they won't be cleared. This eventually leads to garbage overflow.
To overcome this we made this project "Garbage monitoring System". This system aims to alert the authorities about the dustbin getting full so they can arrange for pick up.
Demo system Consist of : <br>
Arduino UNO 1 
ultrasonic sensor 1
GSM module 1
Breadboard 1
Wires
Dustbin / bucket for demo
We choose to go with GSM module but this can be replaced with a wifi module and interfaced using BLINK app.
Reason to use GSM to make the system free from constrain that the area of deployment should be having a wifi hotspot available to connect.
Ultrasonic sensor was used to detect the distance between garbage in dustbin and top of the dustbin.
Arduino UNO was used as micro-controller board.
How will system work ?
Demo setup of projectSensor valuesWhen we throw garbage in dustbin the sensor will calculate the distance and determine if there is space left in dustbin or not.Once Arduino detects that distance between sensor and garbage is less, it sends a message via GSM board notifying that dusting is about to get full.
Dustbin full demonstrationSensor value ≤5Message send by demo systemOne issue with sending message when sensor value detection is it keeps sending message on every instance of detection. This will cause continuous messages to be kept sending.
To overcome this we implemented a delay of 1 hour and for demonstration purpose delay was reduced to 1 min. So every 1 minute a message is send as seen in image below.In real world scenario delay will be 1 hour.
2nd message after 1 minFlaws in system ?
As the demo model was a bucket so it had open top so main flaw this system had was if a person throws something and keeps it in vertical position so as there is still some space. This space won't get detected by sensor due to placement and it will send signal to authority to collect a single piece of wood.
One more flaw was that if a can with soda for example is thrown inside dustbin and soda splash on the sensor there is possibility that sensor may fail.
How to overcome this ?
Solution i came up with is
1 ) by using a close lid dustbin with opening to one side like a post box.
2) by using 2 sensors one at each side this will ensure that dustbin is actually full and not a false alarm.
By using 1 solution we also defeat problem of sensor failure to some extend.
Code for this project:
iomkarsurve/garbagemonitoringsystem
codes for garbage monitoring system. Contribute to iomkarsurve/garbagemonitoringsystem development by creating an…github.com
Reference :
Security System Using Ultrasonic Sensor and Gsm Module https://www.instructables.com/id/Security-System-Using-Ultrasonic-Sensor-and-Gsm-Mo/?source=post_page-----907303bc87ef----------------------
include #define trigPin 9 #define echoPin 10 #define piezoPin 8 SoftwareSerial mySerial(2, 3); int normalDistance…www.instructables.com
Ultrasonic Sensor HC-SR04 and Arduino Tutorial
In this Arduino Tutorial we will learn how the HC-SR04 Ultrasonic Sensor works and how to use it with the Arduino…howtomechatronics.com https://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/?source=post_page-----907303bc87ef----------------------
This project is our small contribution towards "Clean India" initiative.
