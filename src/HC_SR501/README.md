# ZhangGaoxing's HC-SR501 Demo
This is a Windows 10 IoT Core project on the Raspberry Pi 2/3, coded by C#. HC-SR501 is used to detect motion based on the infrared heat in the surrounding area. 

## Sensor Image
![](https://raw.githubusercontent.com/ZhangGaoxing/windows-iot-demo/master/src/HC_SR501/02_Image/sensor.jpg)

## Connect
* VCC - 5V
* GND - GND
* OUT - GPIO 18 - Pin 12

## Reference
In Chinese : http://wenku.baidu.com/view/26ef5a9c49649b6648d747b2.html

In English : https://github.com/ZhangGaoxing/windows-iot-demo/tree/master/src/HC_SR501/01_Datasheet

## What Contains
In HCSR501.cs file
### One constructor
You need to pass OUT pin value to create a HC-SR501 object.
### Three methods
Initialize(), Read() and Dispose(). Initialize() is used to initializing the sensor. Read() returns a bool type data. Dispose() is a cleanup method.

## How to Use
* First, you need to create a HCSR501 object. After that you should call Initialize() to initialize.
```C#
HCSR501 sensor = new HCSR501(18);
sensor.Initialize();
```
* Second, Read().
```C#
bool data = sensor.Read();
```
* If you want to close the sensor, call Dispose().
```C#
sensor.Dispose();
```
