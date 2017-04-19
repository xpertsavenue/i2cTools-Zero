# i2cTools-Zero

This is small guide how to get the I2C-Tools on the Orange Pi Zero.


## Check    
First run this command to chekc the i2c busses:
```    
ls -l /dev/i2c-*
```  
 you should see the folowing output
```
crw------- 1 root root 89, 0 Apr 19 20:49 /dev/i2c-0
crw------- 1 root root 89, 1 Apr 19 20:49 /dev/i2c-1
```
The Orangepi Pi Zero has two I2C Busses. Bus 0 is connected to GPIO pin 3 and 5

## Install the tools
Run the following commands:
```
sudo apt-get update
sudo apt-get install i2c-tools  
sudo apt-get install python-smbus  
sudo apt-get install libi2c-dev     
```

##Check the bus
To detect all the devices that are connectet to the i2c pins in the GPIO header run this as sudo(!)
```
sudo i2cdetect -y 1
```
The output is somthing like the following:
```
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- 27 -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 3f
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
```
