# ZhangGaoxing's DS3231 Demo
This is a Windows 10 IoT Core project on the Raspberry Pi 2/3, coded by C#. The DS3231 is a low-cost, extremely accurate I2C realtime clock (RTC) with an integrated temperature compensated crystal oscillator (TCXO) and crystal.

## Sensor Image
![](https://raw.githubusercontent.com/ZhangGaoxing/windows-iot-demo/master/src/DS3231/02_Image/sensor.jpg)

## Connect
* SDA - Pin3
* SCL - Pin5
* VCC - 5V
* GND - GND

## Reference
https://github.com/ZhangGaoxing/windows-iot-demo/tree/master/src/DS3231/01_Datasheet

## What Contains
In DS3231.cs file
```C#
/// <summary>
/// Initialize the sensor
/// </summary>
/// <returns></returns>
public async Task InitializeAsync();
/// <summary>
/// Read Time from DS3231
/// </summary>
/// <returns>DS3231 Time</returns>
public DateTime ReadTime();
/// <summary>
/// Set DS3231 Time
/// </summary>
/// <param name="time">Time</param>
public void SetTime(DateTime time);
/// <summary>
/// Read DS3231 Temperature
/// </summary>
/// <returns></returns>
public double ReadTemperature();
/// <summary>
/// Cleanup
/// </summary>
public void Dispose();
```

## How to Use
* First, you need to create a DS3231 object. After that you should call InitializeAsync() to initialize.
```C#
DS3231 sensor = new DS3231();
await sensor.InitializeAsync();
```
* Secondly
```C#
DateTime time = sensor.ReadTime();
double temp = sensor.ReadTemperature();
```
* If you want to close the sensor, call Dispose().
```C#
sensor.Dispose();
```

## Demo Result
![](https://raw.githubusercontent.com/ZhangGaoxing/windows-iot-demo/master/src/DS3231/02_Image/result.jpg)