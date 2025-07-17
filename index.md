# Smart Mirror
This summer at BlueStamp I will be working on the smart mirror project, the main objective of this project is to create a mirror that displays information such as time, weather, and news headlines, using Raspberry Pi and MagicMirror.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Tamana N. | Mt. Eden High School | Software Engineering | Incoming Senior

![Headstone Image]([(https://mail.google.com/mail/u/0?ui=2&ik=fdfb431f52&attid=0.1&permmsgid=msg-a:r-7252976553293422791&th=19819d06cd9bbe61&view=fimg&fur=ip&permmsgid=msg-a:r-7252976553293422791&sz=s0-l75-ft&attbid=ANGjdJ_zVTRPqXZJxJyuMQUpfNQEnhuFaQdT8j9w5qT4VGtOOWF1nrF70cPGu6L0aA9Zuz_w8bmrW1-_pfR-yg1RF_3l2iaWcUQnKFoXRxGuDIF_nnotnydmEYaHMJc&disp=emb&realattid=ii_19819d0639fac788cdf1&zw)])
  
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone
<iframe width="560" height="315" src="[[https://www.youtube.com/embed/CaCazFBhYKs](https://www.youtube.com/watch?v=K6AuFzGZmk8&list=PLe-u_DjFx7eui8dmPGji-0-slT8KydYv_&index=86&pp=iAQB)](https://www.youtube.com/watch?v=orQV2renUGQ&list=PLe-u_DjFx7eui8dmPGji-0-slT8KydYv_&index=1&pp=iAQB)" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For my first milestone, I successfully set up the Raspberry Pi and installed MagicMirror². This included flashing the Raspberry Pi OS onto an SD card, connecting it to the internet, cloning the MagicMirror repository from GitHub, and configuring the initial settings. These steps established the core of my project, turning the Raspberry Pi into the central hub for running the software and displaying modules like time, weather, and news. What surprised me most was how straightforward the installation process was, with the clear documentation. The biggest challenge I faced was getting the Raspberry Pi configured properly, troubleshooting network issues, and ensuring that the correct version of Node.js was installed. I also ran into a minor issue with running commands from the wrong directory, but I quickly resolved it. Moving forward, I need to focus on customizing the modules, setting up the mirror display with a one-way mirror, and possibly adding extra features like motion sensors or voice control. Once these tasks are completed, I’ll be closer to having a fully functional MagicMirror ready for daily use. 

# Starter Project
<iframe width="560" height="315" src="[https://www.youtube.com/embed/CaCazFBhYKs](https://www.youtube.com/watch?v=K6AuFzGZmk8&list=PLe-u_DjFx7eui8dmPGji-0-slT8KydYv_&index=86&pp=iAQB)" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

- I finished my starter project which was the retro arcade console as my first stepping stone into learning about engineering. It consists of a USB socket, Dot matrix, digital tube, capacitance, keys, buzzer, power swtich, and a battery box. This all comes together to create a fun console where you can play 5 retro arcade games like snakes, blocks, fire fighting, racing car, and slots. I have soldered all components neccesray to get the console to function properly, I just need to attach the battery box and in order to do that I need to solder the battery box wires to the VCC and GND. Throighout this process, I have come across a few challenges, one being that I forgot to solder the USB socket, the holes are very small so instead of using the USB, I am goinhg to focus on making it battery powered. I realised this after completely screwing on the clear casing so I had to take it all apart.  

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

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
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberyy Pi Kit |Runs MagicMirror software and connects to monitor| $89.99 | <a href="[https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwju68ar28SOAxUf1uMHHc2RJyQYACICCAEQERoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VvkIrwwBnfDD_-3GCg9tDrg4H1k5wM31CARxVsGTUOi0QmNgZ6PCRxoCQDsQAvD_BwE&ohost=www.google.com&cid=CAESVuD2rc2vyXSPg9no_GGk3cCrhwZS6nLgpP1-6NYirdP1wMhtxNyK6KI8dvpd4tzxXu2Ty-gurUXskA9Kg5K9RaEoeORhr2KHR5dKuWsHMTOd6SvxY7F1&category=acrcp_v1_40&sig=AOD64_1wGXx4BDIKvLUO2armpU5wc4zueQ&ctype=5&q=&nis=4&ved=2ahUKEwiJ3L6r28SOAxWZm2oFHSJiLYAQww8oAnoECAkQDg&adurl=)"> Link </a> |
| Micro SD Card | Storage for Raspberry Pi OS and MagicMirror | $8 | <a href="[https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwjL8tSD28SOAxWfB7MAHdD2CB4YACICCAEQDxoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VlDOiAhApgjrCffJWbFn6uHJoRvRqmwEXXVhQCSojxgC4ZXX6UgFZRoCbbMQAvD_BwE&ohost=www.google.com&cid=CAESVuD2XR_6q9lTlacvAg6KRUJpsBPU-0Wi-k-rucQURW7mVqxkjd-2EZORULwmOC_RvCxKys8AkfBW4wesZg3ogPi1_uWNrv9NJf72V9eQfl8MnnECZGut&category=acrcp_v1_45&sig=AOD64_1iAC5X_rwE1Oh52GJeciOjINCerQ&ctype=5&q=&nis=4&ved=2ahUKEwjL_82D28SOAxV-mWoFHYdgKjkQ9aACKAB6BAgJEBI&adurl=)> Link </a> |
| Two-Way Acrylic Mirror | Creates the smart mirror effect | $36.33 | <a href="[https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwi31rDB28SOAxUZi8IIHdOIO0QYACICCAEQGBoCamY&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VkO-6SH8YO4GAaaXfcRUykZT1pwsUJXADHGMf2WyZxv0xYKseyJXVxoCFZwQAvD_BwE&ohost=www.google.com&cid=CAESVuD2e_DxcyBFXLuCmgV0SXL5RgrdPOh3Jz0jp4aukLwt9nDxztwBC43W-0Mh6GBmgtc0uM_4uqastt54ixbBjyluWaUKEQ89-6LFbSjmjII7HrBdx0CX&category=acrcp_v1_40&sig=AOD64_3ABrKIkaz32bXjZki5zSdGkmZlUw&ctype=5&q=&nis=4&ved=2ahUKEwitqKnB28SOAxUInWoFHSE0B5cQ9aACKAB6BAgIECU&adurl=)"> Link </a> |
| HDMI Cable | Connects Raspberry Pi to monitor | $8.99 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwj8wa213MSOAxXGILMAHaAkIyEYACICCAEQBxoCeW0&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0VuaHWtM3C6Gx3URuqXL9D7gJwuqTXTVRO4TJh7c-c-96bVl2JgXq2hoCZR4QAvD_BwE&ohost=www.google.com&cid=CAESVuD2TPKes6Iv0pNFuVIdEees6k2CBksm4EiLF6_tb3IxQmm296aib_N35CU3j6G_cyWimTnCtPSn7SpfjkSEaxMA2WhCKmfYVUaiwrCjTwKp--jfXLQW&category=acrcp_v1_41&sig=AOD64_2UYQvimm0lpUHW62XwV7W3J6gKrA&ctype=5&q=&nis=4&ved=2ahUKEwie66a13MSOAxXbnSYFHQnJHKEQ9aACKAB6BAgFEB4&adurl="> Link </a> |
| Portable Monitor | Display behind the mirror | $69.99 | <a href="https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChsSEwiFqO3x3MSOAxWDg8IIHeObFBkYACICCAEQBxoCamY&co=1&ase=2&gclid=CjwKCAjwvuLDBhAOEiwAPtF0Vtp9HM6j-xkeSNOiQG43Q6KfH6wgXPoJ4HqkLdvh3mqkTQiwJOYTrBoC3HwQAvD_BwE&ohost=www.google.com&cid=CAESVuD2EbyRzsNWjnFkmkMaveQSSyDZae7wCTJARHlYV4IEA776K9iaJ5cQ7fWsnX2OR-De4WQuK_acficIMrXArZQj-bSzMRUFoEju117YFU6vtvy29qxW&category=acrcp_v1_40&sig=AOD64_09S6r0ph6_9l3v0xx85A5CfyDbZg&ctype=5&q=&nis=4&ved=2ahUKEwitsebx3MSOAxVdlmoFHbZSCUwQ9aACKAB6BAgFEBI&adurl="> Link </a> |
| Wood Planks | Frame for mirror and monitor | $15.55 | <a href="https://www.amazon.com/Unfinished-Planks-Painting-Burning-Rectangle/dp/B07C4KX1LG?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&psc=1&smid=A1919NYIH5072G&gQT=1"> Link </a> |
