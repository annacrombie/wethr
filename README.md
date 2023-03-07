# wethr

Simple command line weather.

##  Features

- caches weather data (for 1 hour by default).
  + you could even check the weather conditions off-line after caching them
- caches the results of jq execution
- most of the display logic is handled by [plot](https://github.com/annacrombie/plot)
- POSIX shell (probably, need to do more testing)
- supports multiple weather backends
  + display average data accross all backends

## Installation

### Requirements

- [plot](https://github.com/annacrombie/plot)
- [jq](https://github.com/stedolan/jq)
- `curl` (or `wget`)

### Environment

You must also obtain an api key for the backend you want to use

- [darksky](https://darksky.net/dev/register)
- [openweathermap](https://home.openweathermap.org/users/sign_up)
- [weatherbit](https://www.weatherbit.io/account/create)

In addition, you need to know your current location in coordinates.

- look it up
- a small cli [latlon](https://github.com/annacrombie/latlon)

## Usage

```
wethr 0.4.2
USAGE:
	wethr [-a|-b<backend>] [-f] [-d<data>[-d<data>[...]]]

OPTIONS
	-a - average all cached data
	-c - cache only, don't display anything
	-b darksky|openweathermap|weatherbit - select backend to use
	-d <DATA> - add data to the output
	-f - force redownloading of cached data
	-p <OPTS> - pass along OPTS to plot(1)

DATA:
clouds, c
dew_point, dp
feels_like, f
humidity, h
ozone, o
precip_amnt, pa
precip_prob, pp
pressure, pr
temp, t
uv, u
visibility, v
wind_dir, wd
wind_gust, wg
wind_speed, ws

ENVIRONMENT
	COORDS - lattitude,longitude
		 coordinates to fetch the weather for
```
