PHP MP3 JSON Waveform Generator
===

### About

Generates JSON waveform images for a given MP3 file by converting it to WAV and processing amplitude points.

This code based on [php-waveform-png](http://github.com/afreiday/php-waveform-png/).

### Requirements

- PHP 5+
- LAME MP3 Encoder (Windows build available from http://www.rarewares.org/mp3-lame-bundle.php)

### Usage/Installation

- Copy to a location on your web server
- Ensure that the 'lame' command is accessible and executable from that directory (for Windows systems, place the downloaded .exe and .dll as linked above into that same directory, or modify the script)
- php php-waveform-json.php test.mp3 > test.json

### Other notes

The detail of the waveform can be adjusted by modifying the DETAIL constant at the top of the script. The lower the number, the less data points are skipped, thus resulting in higher detail waveform.

The most time-consuming factor of the script is the LAME encoder, which first converts the uploaded MP3 into a 16 bit, mono, 8 KHz MP3 and finally to a WAV audio file. Unfortunately this doesn't seem to be possible to perform this in one step with the LAME encoder. If this script is to be modified to generate waveforms on the fly for the same MP3 multiple times, I recommend either storing a copy of the final WAV file or modifying the script to keep a dataset of the amplitude points so that the waveform can be redrawn much more quickly.

### Example

See [demo](http://alexkirs.github.io/php-waveform-json/) page.
