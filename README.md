# Waveshare 5.65 inch (F) - waveshare5in65f

A GFX enabled device driver for the Waveshare 5.65 inch (F) color e-paper display

This library allows GFX to bind to a Waveshare 5.65 inch (F) display so that you can use it as a draw target.

Documentation for GFX is here: https://www.codeproject.com/Articles/5302085/GFX-Forever-The-Complete-Guide-to-GFX-for-IoT

To use GFX, you need GNU C++14 enabled. You also need to include the requisite library. Your platformio.ini should look something like this:

```
[env:node32s]
platform = espressif32
board = node32s
framework = arduino
lib_deps = 
	codewitch-honey-crisis/htcw_waveshare5in65f@^1.1.4
lib_ldf_mode = deep
build_unflags=-std=gnu++11
build_flags=-std=gnu++14
            -DBOARD_HAS_PSRAM
            -mfix-esp32-psram-cache-issue
```

Note that PSRAM is enabled. This expects an ESP32 WROVER or modification to use your platform's PSRAM (probably)

The frame buffer takes a significant amount of space - at least 132kB, or generally more if you're dithering.