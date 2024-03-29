# Reporting

### Mission Plan

Before executing a cleanup mission every team is expected to send a mission plan in the following format


```
{
  "usv_id": "<id of the robot provided after registration>"
  "location": [{
	  "timestamp": "<ISO8601 formatted string precise till milliseconds>",
	  "location": {
	    "lat": "<WGS84 latitude precise up to 7 decimal places>",
	    "lng": "<WGS84 longitude precise up to 7 decimal places>",
	    "alt": "<altitude above MSL in meter precise upto 1 decimal place>",
	  }
    }, ...
  ],
  "battery": [
  
  ]
```

`POST`ed to `http://utm.enaxi.in/v1/mission_plan`

### Live Tracking

Teams may use a combination of SIM7600G-H + STM32
Sample code and hardware setup available at
1. [Blog: STM32 + SIM7600G-H](https://www.micropeta.com/video65)
1. [AT MQTT Commands](https://www.micropeta.com/SIM7500_SIM7600_SIM7800%20Series_MQTT_AT%20Command%20Manual_V1.00.pdf)
2. [STM32 Programming and bootloader](https://mischianti.org/stm32-programming-stm32f1-via-usb-with-stm32duino-boot-loader-2/)
3. [Designing a PCB based on STM32](https://www.pcbway.com/blog/PCB_Design_Tutorial/Tutorial__How_to_Design_Your_Own_Custom_STM32_Microcontroller_Board.html)
4. [SIM7600G-H module documentation](https://www.waveshare.com/wiki/SIM7600G-H_4G_Module)

During Testing and Live environments vehicles will be expected to submit flight logs in the following format

```
{
  "usv_id": "<id of the robot provided after registration>"
  "timestamp": "<ISO8601 formatted string precise till milliseconds>",
  "location": {
    "lat": "<WGS84 latitude precise up to 7 decimal places>",
    "lng": "<WGS84 longitude precise up to 7 decimal places>",
    "alt": "<altitude above MSL in meter precise upto 1 decimal place>",
  }
}
```

Such a tracking report must be `POST`ed  to `https://utm.enaxi.in/v1/tracking/` at a minimum frequency of 1 report per second. The API specification is available [here](https://utm.enaxi.in/docs/).

### Mission Logs

```
{
  "usv_id": "<id of the robot provided after registration>"
  "location": [{
	  "timestamp": "<ISO8601 formatted string precise till milliseconds>",
	  "location": {
	    "lat": "<WGS84 latitude precise up to 7 decimal places>",
	    "lng": "<WGS84 longitude precise up to 7 decimal places>",
	    "alt": "<altitude above MSL in meter precise upto 1 decimal place>",
	  }
    }, ...
  ],
  "battery": [
  
  ]
```

Mission Logs report must be `POST`ed  to `https://utm.enaxi.in/v1/mission_log/` directly after each mission is completed. The API specification is available [here](https://utm.enaxi.in/docs/).


### Video Streaming

SIM7600G-H + Raspberry Pi

