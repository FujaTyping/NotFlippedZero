# NotFlippedZero (Wifi penetration tool)
## Webserver component

This component provides an UI for user to interact with the tool itself.

HTML sites are stored in RAM and are defined as a constant char array in `pages/`. Currently only one page is provided and it's updated dynamically usign AJAX calls from JavaScript client.
Currently the Webserver is started by calling `webserver_run()` which registers all available endpoints and runs until ESP32 shuts down.

## JavaScript client
Endpoints are called using AJAX calls from JavaScript provided on `index.html` page. It also parser reponses from webserver from binary to human readble form.
It should do all additional computations that doesn't neccesarry have to happen on ESP32 to minimize its power consumption. 

## Utils
To make development of web client a bit easier, there is a script `utils/convert_html_to_header_file.sh` available that converts standard HTML file into header file and formats it to make it compilable.
