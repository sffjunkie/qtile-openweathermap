# OpenWeatherMap weather widget for QTile v0.1

This is a widget for QTile which can display current weather information
from OpenWeatherMap

## Information

The widget can display the following information

- An icon to represent the current weather state.
- Current temperature
- Feels like temperature
- Minimum temperature
- Maximum temperature
- Air pressure
- Relative humidity
- The textual description of the weather

For example using the default format string looks something like this
![example](./example.png)

## API Key

An [API key from OpenWeatherMap](https://openweathermap.org/api) is required and should be passed as the `api_key` parameter to the initializer

## Location

The location to display infomation for is set by the `latitude` and `longitude` parameters to the initializer.

## Temperature Units

Temperature units can be specified with the `units` parameter. Valid values are

- `metric` = °C (celsius, the default)
- `imperial` = °F (farenheight)
- `standard` = °K (kelvin)

## Format string

The `format` parameter determines what information is displayed.

To change the format use the following elements surrounded by `{` and `}`

| Element           | Description                   |
| ----------------- | ----------------------------- |
| `icon`            | Current weather icon          |
| `temp`            | Current temperature           |
| `temp_units`      | Temperature units             |
| `temp_min`        | Minimum temperature           |
| `temp_max`        | Maximum temperature           |
| `temp_feels_like` | Temperature it fells like     |
| `condition`       | Weather condition as a string |
| `pressure`        | Barometric pressure           |
| `humidity`        | Relative humidity             |

The default format string is `"{temp:.1f}{temp_units} {icon}"`

## Icons

The icons for the weather states can come from either of the following fonts which you will need to have installed

- [Weather Icons](https://erikflowers.github.io/weather-icons/) (the default)
- [Material Design Icons](https://materialdesignicons.com/)

## Installation

- Copy `owm.py` to your QTile config directory.
- From whichever file you construct your bars in, import the module

  ```python
  import owm
  ```

- Add it to your bar

  ```python
  ww = owm.OpenWeatherMap(
      api_key="...",
      latitude=51.0,
      longitude=-50.1,
      icon_font="Material Design Icons",
  )
  top_bar.append(ww)
  ```

## Version History

| No.   | Description |
| ----- | ----------- |
| 0.1   | Initial Version |
