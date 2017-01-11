# MMM-mqtt_command
[MagicMirror²](https://github.com/MichMich/MagicMirror) Module that sends MM commands from a MQTT message



## Installation
1. Navigate into your MagicMirror's `modules` folder and execute `git clone https://github.com/plangdon/MMM-mqtt_command.git`. A new folder will appear, likely called `MMM-mqtt_command`.  Navigate into it.
2. Execute `npm install` to install the node dependencies.

## Using the module

To use this module, add it to the modules array in the `config/config.js` file:
````javascript
modules: [
	{
		module: 'MMM-mqtt_command',
		position: 'top_right',	// This can be any of the regions. Best results in left or right regions.
		header: 'Alexa Commands', // This is optional
		config: {
			// See 'Configuration options' for more information.
		}
	}
]
````

## Configuration options

The following options can be configured:

| Option  | Description  |
|---|---|
| `mqttServer`  | Connection string for the server to connect to (`mqtt://localhost`)  |
| `loadingText`  | Text to display while waiting for data to load  |
| `topic`  | MQTT Topic to subscribe to on the server (`alexa/mmm/display`)  |
| `showTitle`  | Boolean to show/hide a title (default: `false`)  |
| `title`  | Title to show if `showTitle` is `true`  |
| `interval`  | Refresh interval, not including MQTT subscription deliveries. (default: `300000`)  |
| `postText`  | Text to append after the data received from MQTT (default: `''`)  |

## Known Limitations
- Currently only supports unencrypted/unauthenticated MQTT connections.  

## Dependencies
- [mqtt](https://www.npmjs.com/package/mqtt) (installed via `npm install`)
