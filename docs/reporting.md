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
https://www.micropeta.com/video65

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

