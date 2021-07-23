
﻿# FSAE Racing
 
Why watch drive to survive when you can spend all year making your own F1 car instead!!!

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Jesse Klineman | University of Maryland | Mechanical Engineering | Incoming Senior

![Car in Action](https://media.giphy.com/media/Z9D7qnRG7xEgy2TWsP/giphy.gif)
![ezgif com-gif-maker](https://user-images.githubusercontent.com/56967237/125086366-8f13f500-e099-11eb-8973-2b9b11e32c91.gif)


![](https://user-images.githubusercontent.com/56967237/122599782-e09e0680-d03c-11eb-8cf8-70be20d15932.jpg)
<img src="https://user-images.githubusercontent.com/56967237/122599782-e09e0680-d03c-11eb-8cf8-70be20d15932.jpg" width="100" height="100">





  
# Final Milestone
My final milestone is to have a competition level FSAE car!

[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1623446497/video_to_markdown/images/youtube--gC7nPNMq_IM-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=gC7nPNMq_IM "Final Milestone"){:target="_blank" rel="noopener"}

# Code
```c++
void setup() {
  // put your setup code here, to run once:
pinMode(7,OUTPUT);
pinMode(13,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(13,HIGH);
tone(7,329,500);
delay(1000);
tone(7,261,500);
digitalWrite(13,LOW);
delay(1000);

}
```
