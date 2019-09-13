# wethr

![wethr](screenshot.png)

Simple command line weather, built with performance and simplicity in mind.
Powered by [Darksky](https://darksky.net/dev), `wethr` will only re-download
weather after its old data has "expired" (1 hour by default).  It supports the
`hourly` forecasts.

# Installation

### Requirements

- [jq](https://github.com/stedolan/jq)
- [plot](https://github.com/annacrombie/plot)
- [curl](https://curl.haxx.se/)

### Environment

You must also obtain a Darksky api key [here](https://darksky.net/dev/register).
In addition, you need to know your current location in coordinates,
[latlon](https://github.com/annacrombie/latlon) might be something you are
interested in.  Or just use a map.

# Usage

```
usage: wethr [-h|[-d <data> [-d <data>[...]]] [-p <plot args>]

data:
a - apparentTemperature
b - windBearing
c - cloudCover*100
d - dewPoint
g - windGust
h - humidity*100
i - precipIntensity
o - ozone
p - precipProbability*100
P - pressure
t - temperature
u - uvIndex
v - visibility
w - windSpeed

environment
COORDS - lattitude,longitude
  coordinates to fetch the weather for
DARKSKY_API_KEY - xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
  your api key

ex.
wethr -dt -da
```
