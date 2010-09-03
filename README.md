# Config.JSON

*JSON Config Driver*

- **Module Version:** 1.0.0
- **Module URL:** <http://github.com/Zeelot/kohana-config.json>
- **Compatible Kohana Version(s):** 3.0.x

## Description

A simple JSON driver for the Kohana 3.x config system. I was simply tired of writing PHP arrays so I 
thought this would be simple enough to implement. This also adds the little benefit of making your 
config files portable to other languages (as long as they implement something similar). Also note 
that JSON is a subset of YAML 1.2 so many of the frameworks using YAML config files will be able to 
use these JSON config files (as long as they implement YAML 1.2 or above).

## Requirements & Installation

1. Download or clone this repository to your Kohana modules directory
2. Enable the module in your `bootstrap.php` file
3. Attach the JSON reader to a directory of your choosing

<pre></code>/**
 * This attaches the json reader to a config.json directory
 * (ex: application/config.json/hello.json)
 */
Kohana::$config->attach(new Config_JSON('config.json'));
</code></pre>

## Example JSON File

`application/config.json/example.json`

	{
		"some_key": "some value",
		"another_key": {
			"foo": "bar",
			"bars": ["bar1", "bar2", "bar3"]
		}
	}

## Example Usage

	Kohana::config('example')->another_key[bars][1]; // "bar2"
