# homebridge-MotionSensor

Creates a Motion Sensor Accessory for iOS Home app/Homekit via Homebridge.
For now, the state of the sensor is only checked when homebridge requests the current value.


### Installation

1. Install homebridge using: ```npm install -g homebridge```
2. Install this plugin using: ```npm install -g homebridge-http-temperature```
3. Update your configuration file. See sample-config.json in this repository for a sample.

### Configuration

See the sample-config.file to see an example of working accessory. Following, all available options are explained:

The mandatory options are:
 * ```url``` Endpoint to call when the state is requested.
 * ```name``` Accessory name.

The other available options are:
 * ```manufacter``` Manufacter name to be displayed.
 * ```model``` Model name to be displayed.
 * ```serial``` Serial number to be displayed.
 * ```http_method``` Http metod that will be used to call the ```url``` when the state is requested. Default is 'GET' (check request module to get the available options).
 * ```json_response``` This option defines the field that must be parsed to get the state in the endpoint response body. If not defined (or if the value is an empty string which is the default) the response is assumed to be a boolean value directly.

### Endpoint expectations
The enpoint can return 2 types of body responses:
 * JSON. The reponse body is a JSON and the fied with the current status is defined using the ```json_response``` option.
 * Boolean value. The response body is directyle the current status. Accepted values are: 0, false, 1, true.
