
﻿# FSAE Racing
 
Why watch drive to survive when you can spend all year making your own F1 car instead!!!

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Jesse Klineman | University of Maryland | Mechanical Engineering | Incoming Senior

![Car in Action](https://media.giphy.com/media/Z9D7qnRG7xEgy2TWsP/giphy.gif)

![](https://user-images.githubusercontent.com/56967237/122599782-e09e0680-d03c-11eb-8cf8-70be20d15932.jpg)
<img src="https://user-images.githubusercontent.com/56967237/122599782-e09e0680-d03c-11eb-8cf8-70be20d15932.jpg" width="100" height="100">





  
# Final Milestone
My final milestone is to have a competition level FSAE car!

[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1623446497/video_to_markdown/images/youtube--gC7nPNMq_IM-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=gC7nPNMq_IM "Final Milestone"){:target="_blank" rel="noopener"}

<pre>
<font color="#434f54">&#47;&#47;#include &lt;analogWrite.h&gt;</font>

<font color="#5e6d03">#include</font> <font color="#005c5f">&#34;BluetoothSerial.h&#34;</font>

<font color="#5e6d03">#if</font> <font color="#434f54">!</font><font color="#000000">defined</font><font color="#000000">(</font><font color="#000000">CONFIG_BT_ENABLED</font><font color="#000000">)</font> <font color="#434f54">||</font> <font color="#434f54">!</font><font color="#000000">defined</font><font color="#000000">(</font><font color="#000000">CONFIG_BLUEDROID_ENABLED</font><font color="#000000">)</font>
<font color="#5e6d03">#error</font> <font color="#000000">Bluetooth</font> <font color="#000000">is</font> <font color="#5e6d03">not</font> <font color="#000000">enabled</font><font color="#434f54">!</font> <font color="#000000">Please</font> <font color="#d35400">run</font> <font color="#000000">`make</font> <font color="#000000">menuconfig`</font> <font color="#000000">to</font> <font color="#5e6d03">and</font> <font color="#000000">enable</font> <font color="#000000">it</font>
<font color="#5e6d03">#endif</font>

<font color="#000000">BluetoothSerial</font> <font color="#000000">SerialBT</font><font color="#000000">;</font>


<font color="#00979c">float</font> <font color="#000000">num</font><font color="#000000">;</font>
<font color="#00979c">float</font> <font color="#000000">num2</font><font color="#000000">;</font>
<font color="#00979c">float</font> <font color="#000000">num3</font><font color="#000000">;</font>
<font color="#00979c">String</font> <font color="#000000">command</font><font color="#000000">;</font>
<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">pin</font><font color="#434f54">=</font><font color="#000000">2</font><font color="#000000">;</font>
<font color="#00979c">void</font> <font color="#5e6d03">setup</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#000000">115200</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">SerialBT</font><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#005c5f">&#34;ESP32test&#34;</font><font color="#000000">)</font><font color="#000000">;</font> <font color="#434f54">&#47;&#47;Bluetooth device name</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;The device started, now you can pair it with bluetooth!&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">pin</font><font color="#434f54">,</font><font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
<font color="#000000">}</font>

<font color="#00979c">void</font> <font color="#5e6d03">loop</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>

 &nbsp;<font color="#434f54">&#47;&#47;If data has been sent from esp write the data that has been sent</font>
 &nbsp;<font color="#5e6d03">while</font><font color="#000000">(</font><font color="#000000">SerialBT</font><font color="#434f54">.</font><font color="#d35400">available</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;String dummynum = SerialBT.readStringUntil(&#39;,&#39;);</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;String dummynum2 = SerialBT.readStringUntil(&#39;\n&#39;);</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#00979c">String</font> <font color="#000000">dummynum</font> <font color="#434f54">=</font> <font color="#000000">SerialBT</font><font color="#434f54">.</font><font color="#d35400">readStringUntil</font><font color="#000000">(</font><font color="#00979c">&#39;\n&#39;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">SerialBT</font><font color="#434f54">.</font><font color="#d35400">write</font><font color="#000000">(</font><font color="#000000">1</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#00979c">int</font> <font color="#000000">num</font> <font color="#434f54">=</font> <font color="#000000">dummynum</font><font color="#434f54">.</font><font color="#000000">toFloat</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;float num2 = dummynum2.toFloat();</font>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">num</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;Serial.print(&#34;,&#34;);</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;Serial.println(num2);</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">&gt;=</font> <font color="#000000">1.0</font><font color="#000000">)</font><font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">pin</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Yay!&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">else</font> <font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">&lt;=</font> <font color="#000000">1.0</font><font color="#000000">)</font><font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">pin</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Yay!!&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">delay</font><font color="#000000">(</font><font color="#000000">20</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">SerialBT</font><font color="#434f54">.</font><font color="#d35400">write</font><font color="#000000">(</font><font color="#000000">1</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 &nbsp;<font color="#000000">}</font>
 &nbsp;
 &nbsp;<font color="#434f54">&#47;&#47;analogWrite(pin,255);</font>
<font color="#000000">}</font>

</pre>
