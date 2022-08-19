RGB-Matrix-P3.0-64x64 from seengreat:www.seengreat.com
  ======================================
# Instructions
## 1.1、verview
This product RGB Matrix P3.0-64x64 is on-board 4096 full-color display LEDs with 3.0mm pitch,which supports the use of Raspberry Pi developing board. The product is provided with open development resources, suitable for the electronic makers and the related learners to learn or DIY. <br>  
## 1.2、Features
On-board 64 * 64 = 4096 full-color display LEDs<br>   
3.0mm pitch, displaying text, animation and colorful image<br>  
Onboard two HUB75 headers, respectively  for signal input and output. It can be cascaded multi-screen<br> 
Providing open development resources and tutorials  for the use of Raspberry Pi<br>  

## 1.3、Specifications
|DIMENSIONS|192mm(Length)*192mm(Width)*15mm(Height)|
|---------------|-------------------------------------------------|
|PIXELS|64*64|
|PITCH|3.0mm|
|PIXEL FORM|1R1G1B|
|VIEWING ANGLE|≥160°|
|HEADER|HUB75|
|CONTROL TYPE|synchronization|
|DRIVING|1/32 scan|
|POWER SUPPLY|5V/4A|
|POWER PORT|VH4 header input|
# Usage
# Note: The internal RGB definition of this screen is actually GBR, so we provide two solutions: the first solution is to use the standard demo codes on the Internet according to the wiring definition we provided; the second solution is the normal wiring, and then use our modified demo codes. Both solutions can ensure that the screen is displayed normally.For the details of the two solutions, please refer to the contents of chapters 2.1 and 2.2 respectively.<br>  
## 2.1、RGB-Matrix-P3.0-64x64-wiring-as-we-provided
### 2.1.1、Usage of demo for Raspberry Pi
This product is mainly used with the main-board of Raspberry Pi, with HUB75 for signal input and output of dot matrix screen. <br>                      
Definitions of Raspberry Pi and wiring pin of signal input interface:<br>

The wiring pins definitions of signal input for Raspberry Pi and RGB LED Matrix Panel as following:<br> 
|Label	|Pins Description	|BCM number |Pins Function	|Label	|Pins Description      |BCM number   |Pins Function|
|-----------|----------------------|----------------|-----------------|-----------|----------------------|-----------------|--------------|
|R1	|R higher bit data	|7	       |CE1   	|G1	|G higher bit data	|11	|SCLK |
|B1	|B higher bit data	|27	       |P2	                |GND	|Ground	                |GND	|GND|
|R2	|R lower bit data	|10	       |MOSI                |G2	|G lower bit data	|8	|CE0|
|B2	|B lower bit data	|9	       |MISO	|E	|E line selection	|15	|RXD|
|A	|A line selection	|22	       |P3	                |B	|B line selection	|23	|P4|
|C	|C line selection	|24	       |P5	                |D	|D line selection	|25	|P6|
|CLK	|Clock input	|17	       |P0	                |LAT	|Latch pin	|4	|P7|
|OE	|Output enable	|18	       |P1	                |GND	|Ground	|GND	|GND|

Usage of demo<br> 
This display uses the open source code on github to demonstrate. Please access the Raspberry Pi terminal, and then enter the following commands in turn:<br> 
sudo git clone https://github.com/hzeller/rpi-rgb-led-matrix<br> 
cd rpi-rgb-led-matrix<br> 
sudo make<br> 
cd examples-api-use<br> 
sudo ./demo -D 9 --led-rows=64 --led-cols=64<br> 
For more details about the demo, please read the contents of the README.md file carefully.<br> 
Cautions of demo<br> 
_1、Turn off onboard audio_<br> 
Please modify the content of /boot/config.txt into dtparam=audio=off,because the on-board audio and the timing circuitry required by RGB-Matrix cannot be run simultaneously.<br> 
2、Please do not run any programs that run in parallel with the GPIO pins.<br> 
3、Disable the 1-wire interface:raspi-config -> Interface Options -> 1-Wire<br> 
4、Add the isolcpus=3 statement at the end of the /boot/cmdline.txt file, separated by spaces<br> 

## 2.1.2、Usage of demo for Rasperry Pi Pico
The wiring pins definitions of signal input for Pico and RGB LED Matrix Panel as following:<br> 
|Label	|Pins Description	|Pico Pins	|Label	|Pin Description	|Pico Pins|
|-----------|----------------------|-----------|-----------|----------------------|----------|
|R1	|R higher bit data	|GP04	|G1	|G higher bit data	|GP02|
|B1	|B higher bit data	|GP03	|GND	|Ground	                |GND|
|R2	|R lower bit data	|GP09	|G2	|G lower bit data	|GP05|
|B2	|B lower bit data	|GP08	|E	|E line selection	|GP22|
|A	|A line selection	|GP10	|B	|B line selection	|GP16|
|C	|C line selection	|GP18	|D	|D line selection	|GP20|
|CLK	|Clock input	|GP11	|LAT	|Latch pin                 |GP12|
|OE	|Output enable	|GP13	|GND	|Ground	                |GND|

_Usage of Demo：_<br>
After wiring the Pico and the display, open the Thonny Python IDE, access the Pico-RGB Matrix LED_64x64 folder in the demo codes in the "File" window (View -> File), and upload all the files and folders in the folder to In Pico, then double-click to open the main.py file, and click the "run" icon in the menu to run the current code.<br>

## 2.1.3、Usage of demo for Arduino Mega
The wiring pins definitions of signal input for Arduino mega and RGB LED Matrix Panel as following:<br> 
|Label       |Pins Description       |Arduino mega Pins	|Label        |Pin Description       |Arduino mega Pins|
|-----------|----------------------|----------------------|-----------|----------------------|---------------------|
|R1	|R higher bit data	|D26	                |G1	|G higher bit data	|D24|
|B1	|B higher bit data	|D25	                |GND	|Ground	                |GND|
|R2	|R lower bit data	|D29	                |G2	|G lower bit data	|D27|
|B2	|B lower bit data	|D28	                |E	|E line selection	|A4|
|A	|A line selection	|A0	                |B	|B line selection	|A1|
|C	|C line selection	|A2	                |D	|D line selection	|A3|
|CLK	|Clock input	|D11	                |LAT	|Latch pin   	|D10|
|OE	|Output enable	|D9	                |GND	|Ground	                |GND|

_Usage of Demo：_<br> 
After wiring the power cable to the display panel and connecting the signal cable according to Table 2-3, access the Arduino_Mega_RGB_Matrix_64x64 folder and double-click to open the Arduino_Mega_RGB_Matrix_64x64.ino file. Then click the Verify button, and then click the Upload button. The demo code realizes the function of displaying text and pictures in a loop<br>    


## 2.2、RGB-Matrix-P3.0-64x64-wiring-as-normal
If the wiring is normal according to the following 3 tables, you can use the modified code provided by us, the demo codes of Rasperry Pi Pico and Arduino Mega are in the folder "RGB-Matrix-P3.0-64x64-wiring-as-normal", And  The demo codes for Raspberry Pi platform we do not provide directly, but provide a way to modify the codes.<br>
### 2.2.1、Usage of demo for Raspberry Pi
The wiring pins definitions of signal input for Raspberry Pi and RGB LED Matrix Panel as following:<br> 
|Label	|Pins Description	|BCM number |Pins Function	|Label	|Pins Description      |BCM number   |Pins Function|
|-----------|----------------------|----------------|-----------------|-----------|----------------------|-----------------|--------------|
|R1	|R higher bit data	|11	       |SCLK  	|G1	|G higher bit data	|27	|P2|
|B1	|B higher bit data	|7	       |CE1	                |GND	|Ground	                |GND	|GND|
|R2	|R lower bit data	|8	       |CE0	                |G2	|G lower bit data	 |9	|MISO|
|B2	|B lower bit data	|10	       |MOSI	|E	|E line selection	|15	|RXD|
|A	|A line selection	|22	       |P3	                |B	|B line selection	|23	|P4|
|C	|C line selection	|24	       |P5	                |D	|D line selection	|25	|P6|
|CLK	|Clock input	|17	       |P0	                |LAT	|Latch pin	                |4	|P7|
|OE	|Output enable	|18	       |P1	                |GND	|Ground	                |GND	|GND|

Modify lines 44 to 49 in the rpi-rgb-led-matrix/lib/hardware-mapping.c file to:<br> 
    .p0_r1         = GPIO_BIT(27),  /*  Not on RPi1, Rev1; use "regular-pi1" instead*/<br> 
    .p0_g1         = GPIO_BIT(7),  /* masks:  SPI0_CE1  */<br> 
    .p0_b1         = GPIO_BIT(11),   /* masks: SPI0_SCKL */<br> 
    .p0_r2         = GPIO_BIT(9),   /* masks:  SPI0_MISO */<br> 
    .p0_g2         = GPIO_BIT(10),    /* masks: SPI0_MOSI  */<br> 
    .p0_b2         = GPIO_BIT(8),   /* masks: SPI0_CE0  */<br> 
Then recompile.<br> 
It can be easily seen that the pin number of r and g and b has actually been redefined.We use the "regular" wiring method, if the user involves other wiring methods, you can refer to this modification method<br> 
## 2.2.2、Usage of demo for Rasperry Pi Pico
The wiring pins definitions of signal input for Pico and RGB LED Matrix Panel as following:<br> 
|Label	|Pins Description	|Pico Pins	|Label	|Pin Description	|Pico Pins|
|-----------|----------------------|-----------|-----------|----------------------|----------|
|R1	|R higher bit data	|GP02	|G1	|G higher bit data	|GP03|
|B1	|B higher bit data	|GP04	|GND	|Ground	                |GND|
|R2	|R lower bit data	|GP05	|G2	|G lower bit data	|GP08|
|B2	|B lower bit data	|GP09	|E	|E line selection	|GP22|
|A	|A line selection	|GP10	|B	|B line selection	|GP16|
|C	|C line selection	|GP18	|D	|D line selection	|GP20|
|CLK	|Clock input	|GP11	|LAT	|Latch pin                 |GP12|
|OE	|Output enable	|GP13	|GND	|Ground	                |GND|

## 2.2.3、Usage of demo for Arduino Mega
The wiring pins definitions of signal input for Arduino mega and RGB LED Matrix Panel as following:<br> 
|Label       |Pins Description       |Arduino mega Pins	|Label        |Pin Description       |Arduino mega Pins|
|-----------|----------------------|----------------------|------------|---------------------|---------------------|
|R1	|R higher bit data	|D24	                |G1	|G higher bit data	|D25|
|B1	|B higher bit data	|D26	                |GND	|Ground	                |GND|
|R2	|R lower bit data	|D27	                |G2	|G lower bit data	|D28|
|B2	|B lower bit data	|D29	                |E	|E line selection	|A4|
|A	|A line selection	|A0	                |B	|B line selection	|A1|
|C	|C line selection	|A2	                |D	|D line selection	|A3|
|CLK	|Clock input	|D11	                |LAT	|Latch pin   	|D10|
|OE	|Output enable	|D9	                |GND	|Ground	                |GND|

# Data Resources
https://github.com/hzeller/rpi-rgb-led-matrix<br>


Thank you for choosing the products of Shengui Technology Co.,Ltd. For more details about this product, please visit:
www.seengreat.com 
