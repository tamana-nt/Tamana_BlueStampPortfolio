# Smart Mirror
This summer at BlueStamp I will be working on the smart mirror project, the main objective of this project is to create a mirror that displays information such as time, weather, and news headlines, using Raspberry Pi and MagicMirror.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Tamana N. | Mt. Eden High School | Software Engineering | Incoming Senior

<img src = "unnamed.png" style = "width:30%; height:30%;">

# Final Milestone




# Second Milestone



# First Milestone
<iframe width="560" height="315" src="https://www.youtube.com/embed/orQV2renUGQ?si=WIugzJQIWiaW_cI9" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For my first milestone, I successfully set up the Raspberry Pi and installed MagicMirror². This included flashing the Raspberry Pi OS onto an SD card, connecting it to the internet, cloning the MagicMirror repository from GitHub, and configuring the initial settings. These steps established the core of my project, turning the Raspberry Pi into the central hub for running the software and displaying modules like time, weather, and news. What surprised me most was how straightforward the installation process was, with the clear documentation. The biggest challenge I faced was getting the Raspberry Pi configured properly, troubleshooting network issues, and ensuring that the correct version of Node.js was installed. I also ran into a minor issue with running commands from the wrong directory, but I quickly resolved it. Moving forward, I need to focus on customizing the modules, setting up the mirror display with a one-way mirror, and possibly adding extra features like motion sensors or voice control. Once these tasks are completed, I’ll be closer to having a fully functional MagicMirror ready for daily use.

<img src = "https://github.com/tamana-nt/Tamana_BlueStampPortfolio/blob/gh-pages/Screenshot%202025-07-17%20142038.png" style = "width:30%; height:30%;">

# Starter Project
<iframe width="560" height="315" src="https://www.youtube.com/embed/K6AuFzGZmk8?si=hGj0GuObNYL4hWkC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I finished my starter project which was the retro arcade console as my first stepping stone into learning about engineering. It consists of a USB socket, Dot matrix, digital tube, capacitance, keys, buzzer, power swtich, and a battery box. This all comes together to create a fun console where you can play 5 retro arcade games like snakes, blocks, fire fighting, racing car, and slots. I have soldered all components neccesray to get the console to function properly, I just need to attach the battery box and in order to do that I need to solder the battery box wires to the VCC and GND. Throighout this process, I have come across a few challenges, one being that I forgot to solder the USB socket, the holes are very small so instead of using the USB, I am goinhg to focus on making it battery powered. I realised this after completely screwing on the clear casing so I had to take it all apart.  

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's my config file where all the code for my magic mirror is. 

```c++
let config = {
	address: "localhost",	// Address to listen on, can be:
							// - "localhost", "127.0.0.1", "::1" to listen on loopback interface
							// - another specific IPv4/6 to listen on a specific interface
							// - "0.0.0.0", "::" to listen on any interface
							// Default, when address config is left out or empty, is "localhost"
	port: 8080,
	basePath: "/",	// The URL path where MagicMirror² is hosted. If you are using a Reverse proxy
									// you must set the sub path here. basePath must end with a /
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1"],	// Set [] to allow all IP addresses
									// or add a specific IPv4 of 192.168.1.5 :
									// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.1.5"],
									// or IPv4 range of 192.168.3.0 --> 192.168.3.15 use CIDR format :
									// ["127.0.0.1", "::ffff:127.0.0.1", "::1", "::ffff:192.168.3.0/28"],

	useHttps: false,			// Support HTTPS or not, default "false" will use HTTP
	httpsPrivateKey: "",	// HTTPS private key path, only require when useHttps is true
	httpsCertificate: "",	// HTTPS Certificate path, only require when useHttps is true

	language: "en",
	locale: "en-US",   // this variable is provided as a consistent location
			   // it is currently only used by 3rd party modules. no MagicMirror code uses this value
			   // as we have no usage, we  have no constraints on what this field holds
			   // see https://en.wikipedia.org/wiki/Locale_(computer_software) for the possibilities

	logLevel: ["INFO", "LOG", "WARN", "ERROR"], // Add "DEBUG" for even more logging
	timeFormat: 24,
	units: "metric",

	modules: [
		{
			module: "alert",
		},
		{
			module: "updatenotification",
			position: "top_bar"
		},
		{
			module: "clock",
			position: "top_left"
		},
		{
			module: "calendar",
			header: "US Holidays",
			position: "top_left",
			config: {
				calendars: [
					{
						fetchInterval: 7 * 24 * 60 * 60 * 1000,
						symbol: "calendar-check",
						url: "https://ics.calendarlabs.com/76/mm3137/US_Holidays.ics"
					}
				]
			}
		},
	{
  module: "weather",
  position: "top_right",
  config: {
    weatherProvider: "openmeteo",
    type: "current",
    lat: 37.6688,    // Latitude for Hayward, CA
    lon: -122.0808   // Longitude for Hayward, CA
  }
},
{
  module: "weather",
  position: "top_right",
  header: "Weather Forecast",
  config: {
    weatherProvider: "openmeteo",
    type: "forecast",
    lat: 37.6688,    // Latitude for Hayward, CA
    lon: -122.0808   // Longitude for Hayward, CA
  }
},

		{
			module: "newsfeed",
			position: "bottom_bar",
			config: {
				feeds: [
					{
						title: "New York Times",
						url: "https://rss.nytimes.com/services/xml/rss/nyt/HomePage.xml"
					}
				],
				showSourceTitle: true,
				showPublishDate: true,
				broadcastNewsFeeds: true,
				broadcastNewsUpdates: true
			}
		},
{
  module: 'MMM-MyPrayerTimes',
  position: 'top_left',
  header: 'My Prayer Times',
  config: {
	mptLat: 37.6688,            // Hayward latitude
	mptLon: -122.0808,          // Hayward longitude
	mptMethod: 2,               // Islamic Society of North America (ISNA) - common in US
	mptOffset: "0,0,0,0,0,0,0,0,0", // No offset adjustments
	showSunrise: true,          // Show Sunrise time
	showSunset: true,
		// Default display 24hour clock -> false is 12hour (AM/PM) clock
	  }
},
]
};
/*************** DO NOT EDIT THE LINE BELOW ***************/
if (typeof module !== "undefined") { module.exports = config; }

```

# Bill of Materials 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberyy Pi Kit |Runs MagicMirror software and connects to monitor| $89.99 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwiCzuTbzsSOAxXg5uMHHQxLIFcYACICCAEQBRoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VnGgodLDb5CXa4rerdb9lgNTOQB5B_-mhyK2ygFr7NPToaNucYd0TxoCseEQAvD_BwE&ei=R015aLT7Ofqi0PEPiOXZ2Qw&ohost=www.google.com&cid=CAESVuD2qTRJwshzlz-u6dSwUwWJqhMdDPXiZ3apdwxN8ac55qjLIpwEn8jgqS11FiImNjIQRMbSVgCyUqhEKksCvR7gZcyoyY5jlXBvjfYTSgXRqlpFdvae&category=acrcp_v1_40&sig=AOD64_1PWZF9C66drB4R0gHsPpvWTHMe5w&ctype=5&q=&nis=4&sqi=2&ved=2ahUKEwj0utzbzsSOAxV6ETQIHYhyNssQ9aACKAB6BAgIEBM&adurl="> Link </a> |
| Micro SD Card | Storage for Raspberry Pi OS and MagicMirror | $8 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwjL8tSD28SOAxWfB7MAHdD2CB4YACICCAEQDxoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VlDOiAhApgjrCffJWbFn6uHJoRvRqmwEXXVhQCSojxgC4ZXX6UgFZRoCbbMQAvD_BwE&ohost=www.google.com&cid=CAESVuD2XR_6q9lTlacvAg6KRUJpsBPU-0Wi-k-rucQURW7mVqxkjd-2EZORULwmOC_RvCxKys8AkfBW4wesZg3ogPi1_uWNrv9NJf72V9eQfl8MnnECZGut&category=acrcp_v1_45&sig=AOD64_1iAC5X_rwE1Oh52GJeciOjINCerQ&ctype=5&q=&nis=4&ved=2ahUKEwjL_82D28SOAxV-mWoFHYdgKjkQ9aACKAB6BAgJEBI&adurl="> Link </a> |
| Two-Way Acrylic Mirror | Creates the smart mirror effect | $36.33 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwi31rDB28SOAxUZi8IIHdOIO0QYACICCAEQGBoCamY&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VkO-6SH8YO4GAaaXfcRUykZT1pwsUJXADHGMf2WyZxv0xYKseyJXVxoCFZwQAvD_BwE&ohost=www.google.com&cid=CAESVuD2e_DxcyBFXLuCmgV0SXL5RgrdPOh3Jz0jp4aukLwt9nDxztwBC43W-0Mh6GBmgtc0uM_4uqastt54ixbBjyluWaUKEQ89-6LFbSjmjII7HrBdx0CX&category=acrcp_v1_40&sig=AOD64_3ABrKIkaz32bXjZki5zSdGkmZlUw&ctype=5&q=&nis=4&ved=2ahUKEwitqKnB28SOAxUInWoFHSE0B5cQ9aACKAB6BAgIECU&adurl="> Link </a> |
| HDMI Cable | Connects Raspberry Pi to monitor | $8.99 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwj8wa213MSOAxXGILMAHaAkIyEYACICCAEQBxoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VuaHWtM3C6Gx3URuqXL9D7gJwuqTXTVRO4TJh7c-c-96bVl2JgXq2hoCZR4QAvD_BwE&ohost=www.google.com&cid=CAESVuD2TPKes6Iv0pNFuVIdEees6k2CBksm4EiLF6_tb3IxQmm296aib_N35CU3j6G_cyWimTnCtPSn7SpfjkSEaxMA2WhCKmfYVUaiwrCjTwKp--jfXLQW&category=acrcp_v1_41&sig=AOD64_2UYQvimm0lpUHW62XwV7W3J6gKrA&ctype=5&q=&nis=4&ved=2ahUKEwie66a13MSOAxXbnSYFHQnJHKEQ9aACKAB6BAgFEB4&adurl="> Link </a> |
| Portable Monitor | Display behind the mirror | $69.99 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwiFqO3x3MSOAxWDg8IIHeObFBkYACICCAEQBxoCamY&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0Vtp9HM6j-xkeSNOiQG43Q6KfH6wgXPoJ4HqkLdvh3mqkTQiwJOYTrBoC3HwQAvD_BwE&ohost=www.google.com&cid=CAESVuD2EbyRzsNWjnFkmkMaveQSSyDZae7wCTJARHlYV4IEA776K9iaJ5cQ7fWsnX2OR-De4WQuK_acficIMrXArZQj-bSzMRUFoEju117YFU6vtvy29qxW&category=acrcp_v1_40&sig=AOD64_09S6r0ph6_9l3v0xx85A5CfyDbZg&ctype=5&q=&nis=4&ved=2ahUKEwitsebx3MSOAxVdlmoFHbZSCUwQ9aACKAB6BAgFEBI&adurl="> Link </a> |
| Wood Planks | Frame for mirror and monitor | $15.55 | <a href="https://www.amazon.com/Unfinished-Planks-Painting-Burning-Rectangle/dp/B07C4KX1LG?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&psc=1&smid=A1919NYIH5072G&gQT=1"> Link </a> |
