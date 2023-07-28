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

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

My first milestone was achieved when I finished physically building the RC Car and tested the motors to show that they worked. To build the RC Car, I had an instruction sheet that acted as a blueprint, showing me where every part should go and how to connect everything. However, I did have trouble connecting some of the parts occasionally since I needed to screw M1.6 * 16 cross screws into M1.6 nuts, and both of these parts are very tiny. I was able to overcome this challenge, though, by simply using a wrench I have at home, even though it still took a while to screw everything in.
  
After finishing with building the RC Car, I moved on to the portion of time I needed to test the motors. To do this, I first decided to turn on my RC Car with its battery pack and try to move it with the remote control it came with. However, this is where I faced another setback; the RC Car would not move when I clicked any button on the remote. Even though nothing was moving on the car, I could tell that the RC Car was receiving some sort of signal from the remote since a light would glow on the Arduino every time I clicked a button on the remote. Eventually, I figured out that the reason why the car would not move was most likely due to the fact that I added a new code to the Arduino yesterday in order to test it and see if it works. This probably messed up the original code that the Arduino came with, so in order to fix this and just test the motors, I needed to upload a new motor testing code to the Arduino.
    
So, with some help from my instructor, I found and visited a link on a website called Sparkfun that contained a downloadable library of code to test motors with. Next, I simply downloaded said link and then needed to upload it to my Arduino IDE app on my MacBook. I started doing that by opening the zip file to make it a folder. Then, I created a new folder in my Arduino document folder called “libraries” and I moved the folder containing the motor testing code into the library folder (the Arduino was connected to my computer at this time through a USB cable). After this, all I did was reset my Arduino IDE app and went under the “examples” category under file (at the top of my screen) to search for the new library of code. After finding it, I selected it and opened it up to upload it to the Arduino on my RC Car. Then, I simply unplugged the USB port connecting my RC Car to my computer, turned on the car’s battery pack, and watched the motor testing code run in the car. The RC Car’s motors did end up working, since they were able to move in every direction that the motor testing code told them to move in.
    
My next step in this project is to upload a code that lets me tell the car where to go from the remote control instead of having just a motor testing code uploaded to the Arduino.

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

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

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
