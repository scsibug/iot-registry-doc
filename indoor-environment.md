# Indoor Environmental Monitoring

Indoor environmental quality monitoring, temperature, humidity, etc.

## NATS Subject

Messages are published on the subject `iot.indoorenv`.

## CloudEvent Format

CloudEvent spec version `1.0` is used.

### Event Type

The `type` is `com.wellorder.iot.indoorenv`

### Event Sources

Each event `source` is set to a URI representing the server/sensor combination that is performing the monitoring.

For example, if the host foo.example.com has a TMP36 sensor attached, the source may be `http://foo.example.com/iot/tmp36`.

### Event Subject

The `subject` is a human-readable name of the sensor's location ("office", "bedroom", etc.).

## Example

```
{
    "specversion" : "1.0",
    "type" : "com.wellorder.iot.indoorenv",
    "source" : "http://foo.example.com/iot/tmp36",
    "subject" : "office",
    "id" : "79e699de-e6f2-4887-b41d-f88614ddfa4e",
    "time" : "2018-04-05T17:31:00Z",
    "datacontenttype" : "application/json",
    "data" : "<see payload example below>"
}
```

### Payload Example

Temperature is in kelvin, pressure in hPa, humidity in percentage.

```
{
  "loc": "office"
  "dt": 1608163984,
  "temp": 280.23,
  "pressure": 1020,
  "humidity": 0.60,
  "sensorModel": "TMP36"
}
```

## InfluxDB Measurements

When sending to InfluxDB, the measurement is `indoorenv`.  The tag set should include `location` (mapped from `loc` in the event), and `sensor-model` (mapped from `sensorModel` in the event).

