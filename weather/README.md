# Weather

This directory contains datasets related to weather information during COVID-19 period, focusing primarily on the United States.

## Source index

For more descriptions, click on the link to each source.

| Source | Description | Tags | Location | Frequency | Source Type | First Updated | Last Updated |
|-|-|-|-|-|-|-|-|
| [GHCN](ghcn/) | Daily summary of temperature, precipitation, wind, and general climate data worldwide. | `Basic`, `Compr.` | Worldwide | Daily | Official | 01/01/1849 | - |
| [ClimaCell](climacell/) | API for minute-by-minute advanced weather information (paid addon for longer historical data)| `Basic`, `Extended`, `Hazard`, `API` |  Worldwide | Every minute | Aggregate | 4 weeks back | - |
| [Aeris Weather](aeris/) | API for hourly advanced weather information complete with geographical weather mapping (paid addon for longer historical data) | `Basic`, `Extended`, `Hazard`, `Water` | Worldwide | Hourly | Aggregate | 1 month back | - | - |
| [Weather Source](weathersource/) | API for long-range hyperlocal weather and climatology datas | `Basic`, `Extended`, `API` | Worldwide | Hourly | Aggregate | 2000 | - |
| [NCEI](ncei/) | API for comprehensive official weather information from the NOAA | `Basic`, `Extended`, `Compr.`, `API` | Worldwide | Vary | Official | 01/01/1849 | - |

## Field description
- Compr-ness*: Comprehensiveness
- `Official`: data officially reported by authorities
- `Aggregate`: data curated from various sources, which may not have been officially reported by authorities

## Tag description
- `Basic`: Basic weather information, namely `Temperature`, `Precipitation`, `Humidity` and `Wind`.
- `Extended`: Extended weather information, namely `Pressure`, `Cloud`, `Air`.
- `Compr.`: covers a detailed and wide-range, low-level information
- `Trends`: trends (% change) data
- `Index`: contains indexing/ranking mechanism

## Additional paid sources
- [The Weather Company](https://www.ibm.com/products/weather-company-data-packages)
- [AccuWeather](https://enterprisesolutions.accuweather.com/current-historical-weather/historical-weather)
- [OpenWeather](https://openweathermap.org/history)
- [World Weather Online](https://www.worldweatheronline.com/developer/) [Demo](https://towardsdatascience.com/obtain-historical-weather-forecast-data-in-csv-format-using-python-5a6c090fc828)
- [Visual Crossing](https://www.worldweatheronline.com/developer/)
- [Mateomatics](https://www.meteomatics.com/en/eshop)
