# StaubliSerial
Hacks to get serial port working on Staubli RX160 robot hand with controller v7.9

## Background

All VAL3 examples refer to `io` library and `sioLink` as means to connecto to one of available serial ports on the controller. However this seems to be ment for old v6.x controller. 

## Solution

What you really need to do is to create variable in program data XML file (`.dtx`) of type `sio`.

```
<Data name="portSerial2" access="public" xsi:type="array" type="sio" size="1">
  <Value key="0" link="Serial\0" />
</Data>
```

Then in your val code, to output something to serial you just assign strings to this variable:

```
portSerial = "Hello world"
```

**Note** Serial port parameters like baud rate and end of line character are defined in the controller, via Controll Pannel > IO > Serial.

  
