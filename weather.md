# Weather

Current weather and forecast data.

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
