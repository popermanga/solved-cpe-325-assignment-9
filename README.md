Download Link: https://assignmentchef.com/product/solved-cpe-325-assignment-9
<br>
<h2>Assignment</h2>

You are given a program for the MSP430F2013 microcontroller in a binary form (source code is not available to you). This program implements a simple beacon, controlled via the SPI interface. The beacon works as follows:

<ul>

 <li>LED3 is turned on during one time slot (one time slot lasts for 32 milliseconds). After that first time slot, there is a pause when LED3 is turned off. This pause lasts for P time slots. After that, the cycle repeats.</li>

 <li>When the program receives a number from the range 1-100 via SPI, it sets P to that value, allowing to change how often the beacon blinks.</li>

 <li>When the program receives 0, it replies with the current value of P through SPI.</li>

 <li>When the program receives 255, it turns LED3 off completely.</li>

 <li>The program ignores all other numbers received through SPI.</li>

</ul>




Load that program to MSP430F2013 and do the following assignment:

<ol>

 <li>Write a program for MSP430FG4618 that asks the user to enter P in Putty/MobaXterm as follows: <strong>“Beacon pause: “</strong>.</li>

</ol>

When a number from 1 to 100 is entered and the ENTER key is pressed, the program converts the entered value to a number (you can use atoi function for this) and sends this value to MSP430F2013 via SPI to change the pause of the beacon. Display a new message when the user hits ENTER.

If the user enters <strong>“?”</strong> instead of a number, your program should send 0 to MSP430F2013 and read the response (the current length of the pause). Display the received value in Putty/MobaXterm at the new line as follows: <strong>“Current pause: &lt;pause&gt;”</strong>.

If <strong>“-”</strong> is entered, the master device sends 255 to the beacon to turn it off.

If an invalid string or number is entered, the program prints <strong>“Invalid pause entered”</strong>

<ol start="2">

 <li>Implement your own version of the program for MSP430F2013 with the same functionality. You can start with this part and not use the given program if you want.</li>

</ol>




<strong>Hints:</strong>

<ul>

 <li>You can reuse the functions that you made in the previous lab for UART communication as well as functions SpiGetState and SpiSetState from demo code.</li>

 <li>You can use the Watchdog Timer of MSP430F2013 in the same way as you did it with MSP430FG4618. Do not use ACLK: this clock source is not available in this microcontroller.</li>

</ul>




<ul>

 <li>Make a delay of a hundred clock cycles between SpiGetState and SpiGetState function calls when you request the current value of pause.</li>

</ul>

<h2>Bonus</h2>

<ol>

 <li> will be given to students who demonstrate their assignment by establishing Bluetooth connection between MSP430FG4618 and PC rather than using RS-232 connection.</li>

 <li> will be given to students who use DMA to copy data to the transmission buffer for UART communication instead of using a loop.</li>

</ol>


