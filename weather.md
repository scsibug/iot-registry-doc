# Weather

Current weather data.

## NATS Subject

Messages are published on the subject `iot.weather`.

## CloudEvent Format

CloudEvent spec version `1.0` is used.

### Event Type

The `type` is `com.wellorder.iot.weather`

### Event Sources

#### OpenWeather

The OpenWeather service is denoted with a `source` of `https://openweathermap.org/`.

[Documentation for OpenWeather](https://openweathermap.org/api).

#### National Weather Service

The National Weather Service is denoted with a `source` of `https://www.weather.gov/`.

[Documentation for the National Weather Service API](https://www.weather.gov/documentation/services-web-api).

### Event Subject

The `subject` is the location of the weather data, and will be the US ZIP code.

## Example

```
{
    "specversion" : "1.0",
    "type" : "com.wellorder.iot.weather",
    "source" : "https://openweathermap.org/",
    "subject" : "10001",
    "id" : "79e699de-e6f2-4887-b41d-f88614ddfa4e",
    "time" : "2018-04-05T17:31:00Z",
    "datacontenttype" : "application/json",
    "data" : "<see payload example below>"
}
```

### Payload Example

Temperature is in kelvin, pressure in hPa, humidity in percentage, windspeed in meters/sec, visibility in meters, sunrise/sunset is in seconds since UNIX epoch, rain and snow volume in mm.

```
{
  "loc": {
    "lon": -97.19,
    "lat": 32.91,
    "zip": "10001"
  },
  "description": "scattered clouds"
  "temp": 280.23,
  "feels_like": 276.05,
  "dew_point": 272.88,
  "uvi": 0.54,
  "pressure": 1020,
  "humidity": 60,
  "clouds": 40,
  "windspeed": 3.1,
  "winddeg": 0,
  "visibility": 10000,
  "sunrise": 1608125908,
  "sunset": 1608161130,
  "rain": { "rain.1h": 0, "rain.3h": 0 },
  "snow": { "snow.1h": 0, "snow.3h": 0 }
}
```
