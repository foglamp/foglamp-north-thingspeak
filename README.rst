=========================================
FogLAMP "ThingSpeak" C++ North Plugin
=========================================

This is a FogLAMP north plugin for talking to the MathWorks ThingSpeak
web API. This allows buffered reading to be sent to the ThingSpeak API
and further analysed in MATLAB. https://thingspeak.com

Configuration
-------------

The following configuration options exist for the plugin

url
  The URL of the ThingSpeak API, this should normally be left as the default https://api.thingspeak.com/channels

source
  The source of data to send, either redings or statistics

channelId
  The ChannelID has setup in the ThingSpeak interface

write_api_key
  The write_api_key as obtained from the ThingSPeak interface

fields
  A defintion of the fields to be send. This is a JSON document with an
  array called elements, each item in the array is a JSON object with
  the properties asset and reading. Asset is the asset name and reading
  is the datapoitn within the asset. The default for this element is an
  example of how to send data fromthe siusoid plugin.

Build
-----
To build FogLAMP "ThingSpeak" C++ filter plugin:

.. code-block:: console

  $ mkdir build
  $ cd build
  $ cmake ..

- By default the FogLAMP develop package header files and libraries
  are expected to be located in /usr/include/foglamp and /usr/lib/foglamp
- If **FOGLAMP_ROOT** env var is set and no -D options are set,
  the header files and libraries paths are pulled from the ones under the
  FOGLAMP_ROOT directory.
  Please note that you must first run 'make' in the FOGLAMP_ROOT directory.

You may also pass one or more of the following options to cmake to override 
this default behaviour:

- **FOGLAMP_SRC** sets the path of a FogLAMP source tree
- **FOGLAMP_INCLUDE** sets the path to FogLAMP header files
- **FOGLAMP_LIB sets** the path to FogLAMP libraries
- **FOGLAMP_INSTALL** sets the installation path of Random plugin

NOTE:
 - The **FOGLAMP_INCLUDE** option should point to a location where all the FogLAMP 
   header files have been installed in a single directory.
 - The **FOGLAMP_LIB** option should point to a location where all the FogLAMP
   libraries have been installed in a single directory.
 - 'make install' target is defined only when **FOGLAMP_INSTALL** is set

Examples:

- no options

  $ cmake ..

- no options and FOGLAMP_ROOT set

  $ export FOGLAMP_ROOT=/some_foglamp_setup

  $ cmake ..

- set FOGLAMP_SRC

  $ cmake -DFOGLAMP_SRC=/home/source/develop/FogLAMP  ..

- set FOGLAMP_INCLUDE

  $ cmake -DFOGLAMP_INCLUDE=/dev-package/include ..
- set FOGLAMP_LIB

  $ cmake -DFOGLAMP_LIB=/home/dev/package/lib ..
- set FOGLAMP_INSTALL

  $ cmake -DFOGLAMP_INSTALL=/home/source/develop/FogLAMP ..

  $ cmake -DFOGLAMP_INSTALL=/usr/local/foglamp ..
