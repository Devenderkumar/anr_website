
# Anr_website

### clone repo

	git clone https://github.com/anr990/anr_website

### [install hugo in local of machin](https://gohugo.io/getting-started/installing/)

### develop mode

	hugo server

### build mode


	hugo

##### Example: building for https://somedomain.com

	hugo --baseURL="https://somedomain.com"


### using Image with Caption
Use following code to get an image with caption:

		{{< figure src="[IMAGE_URL]" class="figureWithCaption" caption="[IMAGE_CAPTION]" >}}

[IMAGE_URL] - url to your image.
[IMAGE_CAPTION] - content of caption. Links are supported.

Example:

	{{< figure src="/uploads/nfl_990.png" class="figureWithCaption" caption="The beginning of the 2015 IRS Form 990 filing  for the [National Football League](https://www.nfl.com)." >}}