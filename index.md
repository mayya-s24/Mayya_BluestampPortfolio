# Remote Control Car
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails! WRITE THIS AT THE END!!!

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Mayya S | Los Gatos High School | Mechanical Engineering | Incoming Junior

![IMG_2767](https://github.com/mayya-s24/Mayya_BluestampPortfolio/assets/140424606/97e0b81d-9ef0-4ebf-9a47-123eb392999d)

# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/No7-U9r60Jc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

My second milestone was achieved when I finished adding and modifying the code for making the RC Car work properly with its IR remote. What I mean by this is that I was able to figure out how to get the remote that came with the RC Car to control it properly by going in different directions based on the arrows on the remote. Not only did I use the arrows to control it with the code, but I also was able to get the car to stop by using the OK button and to curve in four different angles with four buttons with number labels on them (1, 4, 3, and 6). I was able to do all of this by starting off with a base code for the IR remote and IR receiver from the Sunfounder website (it is linked in my resources section below). This file included code for the actual IR items and code for the decoded key values. With these two tabs of code open in my Arduino application, I was able to edit them and fit them to my RC Car’s needs.

I started doing this by editing the decoded key values to match the hexadecimal numbers that the arrows and OK button on the remote output into the serial monitor on my Arduino application. After changing the hexadecimal numbers from the original Sunfounder code to the ones that my IR remote uses, I moved on to labeling the hex numbers so I could remember what number or word correlates to what button on the remote. I wrote these down so I would not forget them. Next, I went into the main code and checked to make sure that the movements under the void loop section are correlated to the correct label. For example, I would check to make sure that the right arrow button’s label was correlated with the `moveRight(speed);` command. I then verified the code and uploaded it onto my Arduino to test it and see if it works. 

However, once I uploaded it and started pressing the buttons on my IR remote, the motors would not move the wheels or even start up. I did get confirmation that my IR remote was working, though, since my serial monitor said, “REMOTE CONTROL START.” My IR receiver was also working since every time that I clicked any button on my remote, a light glowed on my Arduino. So even though nothing was moving, I knew I was getting somewhere since the IR remote and receiver worked. Nonetheless, the next thing I had to do was figure out what went wrong. With help from my instructor and working on the code a bit more, I was able to make sense of what went wrong. What happened was that the Sunfounder code I found was meant for another type of RC Car with different motors and buttons on its IR remote. So, it made sense that my vehicle did not move at all. To fix this issue, I brought movement code from the Sparkfun library (from the motor testing code I used in milestone one) into the code I had and replaced Sunfounder’s movement and motor code with Sparkfun’s movement and motor codes. Here is the code that I added from Sparkfun at that time:

```c++

#include <SparkFun_TB6612.h>

#define AIN1 7
#define BIN1 8
#define AIN2 1
#define BIN2 2
#define PWMA 5
#define PWMB 6
#define STBY 3

Motor motor1 = Motor(AIN1, AIN2, PWMA, offsetA, STBY);
Motor motor2 = Motor(BIN1, BIN2, PWMB, offsetB, STBY);

} else if (key == "2") {
forward(motor1, motor2,75);
} else if (key == "5") {
right(motor1, motor2, 115);
} else if (key == "6") {
left(motor1, motor2, 115);
} else if (key == "OK") {
brake(motor1, motor2);
} else if (key == "8") {
back(motor1, motor2, -75);

```

Since this only contains the bits of code I added from Sparkfun, these pieces of code shown above are only a part of the whole code (which is pasted below). I also removed the speed variable and decided to make a custom speed for each movement. Plus, I deleted all of the “analogWrite” functions at the bottom of the original code. Then, I verified and uploaded the new code onto my Arduino and tested it. This code only had five working buttons, but they were the most important ones: “OK” to make the motors stop, the right arrow to make the car turn right in one position, the left arrow to make the car turn left in one position, the forward arrow to make the motors accelerate forward, and the backward arrow to make the motors accelerate backward. All five of these movement commands ended up working when I tested them, so the problem of the motors not being connected correctly was solved. However, I did not want to stop here. The code from the Sparkfun library that I used from the motor testing code had more movements than just move forward, move backward, turn left, and turn right. So, I wanted to implement these into my RC Car as well. Even though I only had a number pad left to work with for buttons on my IR remote (1-9), I simply picked out four that somewhat correlated to the direction I wanted the car to go in. These directions were curving forward right, curving forward left, curving back right, and curving back left. Here are the pieces of code I used to make the RC Car move in these directions:

```c++

} else if (key == "1") {
motor1.drive(127.5,500);
} else if (key == "3") {
motor2.drive(127.5,500);
} else if (key == "4") {
motor1.drive(-127.5,500);
} else if (key == "7") {
motor2.drive(-127.5,500);

```

This code was also tested and it worked very well. Right now, this is where my code and project as a whole is at. Since my general movement code is pretty much done for now, I want to start working on the hardware a bit more with adjusting the wheels to gain more traction and to stabilize them more. I will most likely be using lock nuts for this. I also would like to do a little bit more with the software and eventually make an object avoidance code. 

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/Vfw5lBs4yPw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

My first milestone was achieved when I finished physically building the RC Car and tested the motors to show that they worked. To build the RC Car, I had an instruction sheet that acted as a blueprint, showing me where every part should go and how to connect everything. However, I did have trouble connecting some of the parts occasionally since I needed to screw M1.6 * 16 cross screws into M1.6 nuts, and both of these parts are very tiny. I was able to overcome this challenge, though, by simply using a wrench I have at home, even though it still took a while to screw everything in.
  
After finishing with building the RC Car, I moved on to the portion of time I needed to test the motors. To do this, I first decided to turn on my RC Car with its battery pack and try to move it with the remote control it came with. However, this is where I faced another setback; the RC Car would not move when I clicked any button on the remote. Even though nothing was moving on the car, I could tell that the RC Car was receiving some sort of signal from the remote since a light would glow on the Arduino every time I clicked a button on the remote. Eventually, I figured out that the reason why the car would not move was most likely due to the fact that I added a new code to the Arduino yesterday in order to test it and see if it works. This probably messed up the original code that the Arduino came with, so in order to fix this and just test the motors, I needed to upload a new motor testing code to the Arduino.
    
So, with some help from my instructor, I found and visited a link on a website called Sparkfun that contained a downloadable library of code to test motors with. Next, I simply downloaded said link and then needed to upload it to my Arduino IDE app on my MacBook. I started doing that by opening the zip file to make it a folder. Then, I created a new folder in my Arduino document folder called “libraries” and I moved the folder containing the motor testing code into the library folder (the Arduino was connected to my computer at this time through a USB cable). After this, all I did was reset my Arduino IDE app and went under the “examples” category under file (at the top of my screen) to search for the new library of code. After finding it, I selected it and opened it up to upload it to the Arduino on my RC Car. Then, I simply unplugged the USB port connecting my RC Car to my computer, turned on the car’s battery pack, and watched the motor testing code run in the car. The RC Car’s motors did end up working, since they were able to move in every direction that the motor testing code told them to move in.
    
My next step in this project is to upload a code that lets me tell the car where to go from the remote control instead of having just a motor testing code uploaded to the Arduino.

# Schematic 
![Dazzling Jarv-Hango](https://github.com/mayya-s24/Mayya_BluestampPortfolio/assets/140424606/ba9b8d08-76ef-4752-9061-dc9f2e6aac0f)

# Code

```c++
//This is the beginning of the _main code_
//Keep this in its own tab while you're working on it

#include <IRremote.h>
#include <SparkFun_TB6612.h>
const int recvPin = 9;
IRrecv irrecv(recvPin);
decode_results results;

#define AIN1 7
#define BIN1 8
#define AIN2 1
#define BIN2 2
#define PWMA 5
#define PWMB 6
#define STBY 3

const int offsetA = 1;
const int offsetB = 1;

Motor motor1 = Motor(AIN1, AIN2, PWMA, offsetA, STBY);
Motor motor2 = Motor(BIN1, BIN2, PWMB, offsetB, STBY);

const int ledPin = 13;

void setup() {
  Serial.begin(9600);
   brake(motor1, motor2);
   delay(1000);

  //UR remote
  irrecv.enableIRIn();
  Serial.println("REMOTE CONTROL START");

  //LED
  pinMode(ledPin, OUTPUT);
}

void loop() {

  if (irrecv.decode(&results)) {
        Serial.println(results.value,HEX);
    String key = decodeKeyValue(results.value);
    if ( key != "ERROR")
    {
      Serial.println(key);
      blinkLED();
      if (key == "+") {
        //speed += 50;
      } else if (key == "-") {
        //speed -= 50;
      } else if (key == "2") {
        forward(motor1, motor2,75);
      } else if (key == "1") {
        motor1.drive(127.5,500);
      } else if (key == "3") {
        motor2.drive(127.5,500);
      } else if (key == "4") {
        motor1.drive(-127.5,500);
      } else if (key == "5") {
        right(motor1, motor2, 115);
      } else if (key == "6") {
        left(motor1, motor2, 115);
      } else if (key == "7") {
        motor2.drive(-127.5,500);
      } else if (key == "9") {
        //backRight(speed);
      } else if (key == "OK") {
        brake(motor1, motor2);
      } else if (key == "8") {
        back(motor1, motor2, -75);
      }
    }
    irrecv.resume();
  }
}

void blinkLED() {
  for (int i = 0; i < 3; i++) {
    digitalWrite(ledPin, HIGH);
    delay(50);
    digitalWrite(ledPin, LOW);
    delay(50);
  }
}
```

```c++
//This is the beginning of the _decode key values_
//Keep this in its own tab while you're working on it
//All of these extra values are commented out just in case you want to add more movement code to the car. This way, you will have a starting point and can simply change a commented out value.

String decodeKeyValue(long result)
{
  switch(result){
    //case 0xFF6897:
    //  return "0";
    case 0xFF6897:
      return "1"; 
    case 0xFF629D:
      return "2"; 
    case 0xFFB04F:
      return "3"; 
    case 0xFF30CF:
      return "4"; 
    case 0xFF22DD:
      return "5"; 
    case 0xFFC23D:
      return "6"; 
    case 0xFF7A85:
      return "7"; 
    case 0xFFA857:
      return "8"; 
    //case 0xFFA857:
    //  return "9"; 
    case 0xFF02FD:
      return "OK"; 
    //case 0xFF02FD:
    //  return "-"; 
    //case 0xFFE01F:
    //  return "EQ"; 
    //case 0xFFB04F:
    //  return "U/SD";
    //case 0xFF9867:
    //  return "CYCLE";         
    //case 0xFF22DD:
    //  return "PLAY/PAUSE";   
    //case 0xFF02FD:
    //  return "BACKWARD";   
    //case 0xFFC23D:
    //  return "FORWARD";   
    //case 0xFFA25D:
    //  return "POWER";   
    //case 0xFFE21D:
    //  return "MUTE";   
    //case 0xFF629D:
    //  return "MODE";       
    case 0xFFFFFFFF:
      return "ERROR";   
    default :
      return "ERROR";
    }
}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources
Here are some of the outside sources I used for the code and build of my project.
- [Motor Testing Code from Sparkfun](https://learn.sparkfun.com/tutorials/tb6612fng-hookup-guide?_ga=2.67160402.2105495080.1686588805-674468134.1671124267&_gac=1.150684356.1686763051.CjwKCAjwyqWkBhBMEiwAp2yUFoz7lbp_jOUGI2bSCq_Bj9TRHZ_t6pfO7qw7H3x4ezKhMXuIkfPRuhoCOdEQAvD_BwE)
- [Sunfounder Base Code for IR Remote](https://docs.sunfounder.com/projects/3in1-kit/en/latest/car_project/car_remote_control.html#car-remote)
- [Tinkercad for Creating Schematics](https://www.tinkercad.com)
