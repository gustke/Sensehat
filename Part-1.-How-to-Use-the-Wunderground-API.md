In order to use the Wunderground API, you first need your own API key. Getting an API key is quick and free. 

* Go to http://www.wunderground.com/weather/api/?MR=1.
* Click “Sign Up for FREE!”.

![Wunderground](https://github.com/InitialState/wunderground-sensehat/wiki/img/wunderground_home.png)

* Create an account and click the link sent to you in a validation email to activate your account
* Sign in
* Go to Pricing and select the free Stratus Plan (default selection). You get 500 API calls per day for $0.  There is no credit card required to get the Developer level API.

![Wunderground](https://github.com/InitialState/wunderground-sensehat/wiki/img/wunderground_key.png)

* Click “Purchase Key”
* Fill out the form and submit it to get your API key

Your key will look something like this: 0def10027afaebb7. Save it.

You can make an API to Wunderground by typing in a URL into your browser in the following format:

    http://api.wunderground.com/api/YOUR_API_KEY/conditions/q/THE_DESIRED_STATE/THE_DESIRED_CITY.json

for example, to get the weather in San Francisco, CA:

* http://api.wunderground.com/api/0def10027afaebb7/conditions/q/CA/San_Francisco.json

or, to get the weather in London

* http://api.wunderground.com/api/0def10027afaebb7/conditions/q/UK/London.json

Let's look at what is returned:

```
{
  "response": {
  "version":"0.1",
  "termsofService":"http://www.wunderground.com/weather/api/d/terms.html",
  "features": {
  "conditions": 1
  }
	}
  ,	"current_observation": {
		"image": {
		"url":"http://icons.wxug.com/graphics/wu2/logo_130x80.png",
		"title":"Weather Underground",
		"link":"http://www.wunderground.com"
		},
		"display_location": {
		"full":"London, United Kingdom",
		"city":"London",
		"state":"",
		"state_name":"United Kingdom",
		"country":"UK",
		"country_iso3166":"GB",
		"zip":"00000",
		"magic":"1",
		"wmo":"03772",
		"latitude":"51.47999954",
		"longitude":"-0.44999999",
		"elevation":"24.00000000"
		},
		"observation_location": {
		"full":"London, ",
		"city":"London",
		"state":"",
		"country":"UK",
		"country_iso3166":"GB",
		"latitude":"51.47750092",
		"longitude":"-0.46138901",
		"elevation":"79 ft"
		},
		"estimated": {
		},
		"station_id":"EGLL",
		"observation_time":"Last Updated on October 23, 5:50 AM BST",
		"observation_time_rfc822":"Fri, 23 Oct 2015 05:50:00 +0100",
		"observation_epoch":"1445575800",
		"local_time_rfc822":"Fri, 23 Oct 2015 06:13:53 +0100",
		"local_epoch":"1445577233",
		"local_tz_short":"BST",
		"local_tz_long":"Europe/London",
		"local_tz_offset":"+0100",
		"weather":"Overcast",
		"temperature_string":"50 F (10 C)",
		"temp_f":50,
		"temp_c":10,
		"relative_humidity":"87%",
		"wind_string":"From the Variable at 4 MPH",
		"wind_dir":"Variable",
		"wind_degrees":0,
		"wind_mph":4,
		"wind_gust_mph":0,
		"wind_kph":6,
		"wind_gust_kph":0,
		"pressure_mb":"1022",
		"pressure_in":"30.18",
		"pressure_trend":"0",
		"dewpoint_string":"46 F (8 C)",
		"dewpoint_f":46,
		"dewpoint_c":8,
		"heat_index_string":"NA",
		"heat_index_f":"NA",
		"heat_index_c":"NA",
		"windchill_string":"NA",
		"windchill_f":"NA",
		"windchill_c":"NA",
		"feelslike_string":"50 F (10 C)",
		"feelslike_f":"50",
		"feelslike_c":"10",
		"visibility_mi":"6.2",
		"visibility_km":"10.0",
		"solarradiation":"--",
		"UV":"0","precip_1hr_string":"-9999.00 in (-9999.00 mm)",
		"precip_1hr_in":"-9999.00",
		"precip_1hr_metric":"--",
		"precip_today_string":"0.00 in (0.0 mm)",
		"precip_today_in":"0.00",
		"precip_today_metric":"0.0",
		"icon":"cloudy",
		"icon_url":"http://icons.wxug.com/i/c/k/nt_cloudy.gif",
		"forecast_url":"http://www.wunderground.com/global/stations/03772.html",
		"history_url":"http://www.wunderground.com/history/airport/EGLL/2015/10/23/DailyHistory.html",
		"ob_url":"http://www.wunderground.com/cgi-bin/findweather/getForecast?query=51.47750092,-0.46138901",
		"nowcast":""
	}
}
```

Look at all of that glorious weather data. We just need to make a script to parse it, then ship it to a web-based dashboard. First, let's setup the destination for our data -> Initial State.

[<< Part 1: Wunderground](Part-1.-Wunderground) - [Part 1: Initial State >>](Part-1.-Initial-State)