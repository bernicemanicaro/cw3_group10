cw3_group10

#!/usr/bin/python

import os
from time import sleep
import RPi.GPIO as GPIO

GPIO.setmode(GPIO.BCM)

# setup our input pin
# we use an internal pull up resistor to hold the pin at 3v3, otherwise the inputs value could chat$
GPIO.setup(11, GPIO.IN, pull_up_down=GPIO.PUD_UP)
GPIO.setup(17,GPIO.OUT)
GPIO.setup(27,GPIO.OUT)
GPIO.setup(22,GPIO.OUT)
GPIO.setup(10,GPIO.OUT)
GPIO.setup(9,GPIO.OUT)
BS1=False

 
while (1):
    if GPIO.input(11) == 0:
        print"11 was Pressed"
        if BS1==False:
                GPIO.output(17,True)
                GPIO.output(27,True)
                GPIO.output(22,True)
                GPIO.output(10,True)
                GPIO.output(9,True)
                BS1=True
                sleep(2)

        else:
                GPIO.output(17,False)
                GPIO.output(27,False)
                GPIO.output(22,False)
                GPIO.output(10,False)
                GPIO.output(9,False)
                BS1=False
                sleep(0.1)
