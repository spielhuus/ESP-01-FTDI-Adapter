# ESP-01-FTDI-Adapter

simple adapter to connect an ESP-01 with a FTDI cable.

[<img src="https://spielhuus.github.io/ESP-01-FTDI-Adapter/perfboard.png" alt="perfboard" width="393" height="250">](https://spielhuus.github.io/ESP-01-FTDI-Adapter/perfboard.png)
[<img src="https://spielhuus.github.io/ESP-01-FTDI-Adapter/product.jpg" alt="product" width="314" height="250">](https://spielhuus.github.io/ESP-01-FTDI-Adapter/product.jpg)

# Usage

## Boot the device
connect to the com port with 76800 baud rate and press the reset button.

## Test the setup
connect to the com port with 115200 baud rate and enter

```
AT
```

## Set the baud rate

AT+UART_DEF=<baudrate>, <databits>, <stopbits>, <parity>, <flow control>

```
AT+UART_DEF=9600,8,1,0,0
```

## List the available access points.

```
AT+CWLAP
```

## start a http server

you can connect to the server and see the request in the console.

```
AT+CWJAP=”<access_point_name>”,”<password>”
AT+CWMODE=1
AT+CIPSERVER=1,80
```

get ip address

```
AT+CIFSR
```

start the server

enable musltiple connections and start the server on port 80.

```
AT+CIPMUX=1
AT+CIPSERVER=1,80
```

#Reference

* [ESP User Manual](http://wiki.ai-thinker.com/_media/esp8266/esp8266_series_modules_user_manual_v1.1.pdf)
* [ESP8266 AT Commands](https://room-15.github.io/blog/2015/03/26/esp8266-at-command-reference/)
