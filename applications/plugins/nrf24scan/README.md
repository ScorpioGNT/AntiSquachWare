#  Scanner NRF24 scanner with logging and resend ability for Flipper Zero

An [NRF24](https://www.sparkfun.com/datasheets/Components/SMD/nRF24L01Pluss_Preliminary_Product_Specification_v1_0.pdf) driver for the [Flipper Zero](https://flipperzero.one/) device. The NRF24 is a popular line of 2.4GHz radio transceivers from Nordic Semiconductors. This library is not currently complete, but functional.

Settings file (default addr.txt) format:<br>
1: <Rate (0/1/2)><br>
2: <Channel (0..125)><br>
3: <address P0 (5 bytes in hex)><br>
4: [address P1 (5 bytes in hex)]<br>
5: [LSB address P2, MSB like P1]<br>
6: [LSB address P3, MSB like P1]<br>
7: [LSB address P4, MSB like P1]<br>
8: [LSB address P5, MSB like P1]<br>
<br>
<img src="https://raw.githubusercontent.com/vad7/nrf24scan/master/Screenshot-1.png">
<br>
<img src="https://raw.githubusercontent.com/vad7/nrf24scan/master/Screenshot-2.png">

## PinOut from from NoComp/Frog
<img src="https://media.discordapp.net/attachments/937479784726949900/994495234618687509/unknown.png?width=567&height=634">

# NRF24 pinout by UberGuidoZ
2/A7 on FZ goes to MOSI/6 on nrf24l01<br>
3/A6 on FZ goes to MISO/7 on nrf24l01<br>
4/A4 on FZ goes to CSN/4 on nrf24l01<br>
5/B3 on FZ goes to SCK/5 on nrf24l01<br>
6/B2 on FZ goes to CE/3 on nrf24l01<br>
8/GND on FZ goes to GND/1 on nrf24l01<br>
9/3V3 on FZ goes to VCC/2 on nrf24l01<br>
IRQ/8 is left disconnected on nrf24l01
![NRF_Pins](https://user-images.githubusercontent.com/57457139/178093717-39effd5c-ebe2-4253-b13c-70517d7902f9.png)
If the nRF module is acting a bit flakey, try adding a capacitor to the vcc/gnd lines! I've not tried the Plus model so it may have a bigger need for a cap. Otherwise, I haven't had any major issues. Anything from a 3.3 uF to 10 uF should do. (Watch your positive/negative placement! Negative to ground.) I learned if you wanna get fancy, include a 0.1 uF cap in parallel. The 3.3 uF to 10 uF will respond to slow freq changes while the 0.1 uF will respond to the high freq switching spikes that the larger one cannot. That said, a single 10 uF will likely suffice for the Mousejack attack. ¯\\\_(ツ)_/¯
![NRF_Capacitor](https://user-images.githubusercontent.com/57457139/178169959-d030f9a6-d2ac-46af-af8b-470ff092c8a7.jpg)

