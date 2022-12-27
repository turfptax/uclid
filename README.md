<br />
<div align="center">
    <img src="images/uclid.jpg" alt="Logo" width="100%">
    <h1 align="center">Micropython CLI Datagram</h1>
  <h3 align="center">Simple Datagram Communication.</h3>
  <h2 align="center">Snags IP Addresses automatically if possible</h2>
  <p align="center"> Get Feedback Over UDP</p>
</div>


## About uclid

uclid was designed to communicate with a micropython board and another computer over UDP packets. uclid cannot replicate the stdout entirely but does provide enough feedback via the frint() function. 

Redirecting STDOUT on all devices is very difficult even with DMA so a recursive frint() function works enough to get some feedback form the micropython device. To make frint() work better you can call it in your other functions running so that it can be easily redirected over UDP.

uclid functions:
* Wireless Client Connect & Wireless Access Point Create
* Send & Receive functions with some automatic IP address resolve


## Getting Started

```python
#boot.py

import uclid

uclid.wificonnect('SSID','PASSWORD')

data = uclid.receive()
uclid.send('Totally got your message!')

```
### Installation

Simply put: copy uclid.py onto the micropython board.

1. Copy uclid.py onto your micropython board
2. connect to network
4. send or receive data


<!-- USAGE EXAMPLES -->
## Usage

```python
import ugit

uclid.wificonnect('ssid','password') # connects to wifi
uclid.wap('ssid','password') # Creates Wireless Access Point
uclid.receive() # receives data on port 3145 and grabs sender's ip address
uclid.send(data) # sends data to client ip Address
uclid.set_client_ip('IP.ADDRESS.1.1') # sets client iop address
uclid.set_port(port) # sets the sending and receiving port
uclid.set_timeout(time_in_seconds) # sets how long receive() will wait before quiting
uclid.start() # starts REPL or CLI like loop to receive commands and send output back
uclid.frint() # tries to capture stdout of commands

```
