GifDecoder - AnimatedGIF Decoder Library
========================================
This library decodes Animated GIF frames from a Filesystem, and draws them to a display.  The Filesystem and Display specific functions have been abstracted out using callback functions contained in the sketch, so this library should be useful on many different platforms.  This library depends on the [AnimatedGIF Library](https://github.com/bitbank2/AnimatedGIF).

As of release 0.0.2 (November 2020), the GifDecoder Library has been rewritten and simplified to use the external [AnimatedGIF Library](https://github.com/bitbank2/AnimatedGIF) to do the decoding.  The AnimatedGIF Library is written to be very efficient, but doesn't have the easiest API to work with.  GifDecoder Library acts as a wrapper to provide an easier interface, familiar with anyone using the Pixelmatix AnimatedGIFs sketch or earlier versions of the GifDecoder Library.

Note one API change for previous users of the AnimatedGIFs sketch or earlier versions of the GifDecoder Library: A callback function that returns the current file size is required, use `setFileSizeCallback()`

The AnimatedGIF Library can't decode all GIF types.  Follow the updated example code that checks for errors when calling `startDecoding()` and `decodeFrame()` to find GIFs that aren't compatible.  In particular, GIFs using interleaved frames aren't supported.

A [SmartMatrix Library](http://docs.pixelmatix.com/SmartMatrix/index.html) example is included, reading from a SD card.  This works on both the Teensy and ESP32 platforms.

For ESP32/ESP8266 SPIFFS, try adapting the SmartMatrix example, using the FilenameFunctions code in this repository: https://github.com/prenticedavid/AnimatedGIFs_SD

For Adafruit's Arcada platform, see the examples in this repository: https://github.com/adafruit/Adafruit_Arcada_GifDecoder

For other platforms or other displays, start with the SmartMatrix example, remove the SmartMatrix-specific code, and modify FilenameFunctions as needed.

The included example is meant to give you an idea of how to add GIF playback to your own sketch.  For a project that adds GIF playback with other features, take a look at [Light Appliance](https://github.com/CraigLindley/LightAppliance), [Aurora](https://github.com/pixelmatix/aurora), and the [Adafruit Arcada examples](https://github.com/adafruit/Adafruit_Arcada_GifDecoder/tree/master/examples).

If you find any GIFs that won't play properly, please attach them to a new Issue post in the GitHub repo [here](https://github.com/pixelmatix/AnimatedGIFs/issues):

Many thanks to David Prentice and Adafruit for improvements on the original AnimatedGIFs sketch and turning the sketch into a library, the original author [Craig A. Lindley](http://www.craigandheather.net/celelightappliance.html), and Larry Bank who's [AnimatedGIF Library](https://github.com/bitbank2/AnimatedGIF) does the heavy lifting to decode the GIFs.  If you want to support Animated GIF decoding with Arduino sketches, Larry Bank [accepts donations and GitHub sponsorships](https://github.com/bitbank2/AnimatedGIF), please support his work!
