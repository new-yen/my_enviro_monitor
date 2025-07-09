# my-enviro-monitor
My desktop Pimoroni Enviro Monitor to track temperature, light, humidty and pressure. As a bonus it warns me when I am too loud again.

There is also a folder with some the icons I am using.

Some notes:
There seem to be some issues with the st7735 library (https://github.com/pimoroni/st7735-python)

The original code was:

#Create ST7735 LCD display class
st7735 = st7735.ST7735(
    port=0,
    cs=1,
    dc="GPIO9",
    backlight="GPIO12",
    rotation=270,
    spi_speed_hz=10000000
)

The new working code for the display:
#Create ST7735 LCD display class
st7735 = st7735.ST7735(
    port=0,
    cs=1,
    dc=**9**,
    backlight=**12**,
    rotation=270,
    spi_speed_hz=10000000
)

dc and backlight just need the pins as integer numbers, I don't know enough why this is the case, I could not make it out from the GH issues but this seems to fix it. 
Here is the pull request: https://github.com/pimoroni/st7735-python/issues/36
Cheers
