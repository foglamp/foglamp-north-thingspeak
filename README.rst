=========================================
Fledge "ThingSpeak" C++ North Plugin
=========================================

This is a Fledge north plugin for talking to the MathWorks ThingSpeak
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
To build Fledge "ThingSpeak" C++ filter plugin:

.. code-block:: console

  $ mkdir build
  $ cd build
  $ cmake ..

- By default the Fledge develop package header files and libraries
  are expected to be located in /usr/include/fledge and /usr/lib/fledge
- If **FLEDGE_ROOT** env var is set and no -D options are set,
  the header files and libraries paths are pulled from the ones under the
  FLEDGE_ROOT directory.
  Please note that you must first run 'make' in the FLEDGE_ROOT directory.

You may also pass one or more of the following options to cmake to override 
this default behaviour:

- **FLEDGE_SRC** sets the path of a Fledge source tree
- **FLEDGE_INCLUDE** sets the path to Fledge header files
- **FLEDGE_LIB sets** the path to Fledge libraries
- **FLEDGE_INSTALL** sets the installation path of Random plugin

NOTE:
 - The **FLEDGE_INCLUDE** option should point to a location where all the Fledge 
   header files have been installed in a single directory.
 - The **FLEDGE_LIB** option should point to a location where all the Fledge
   libraries have been installed in a single directory.
 - 'make install' target is defined only when **FLEDGE_INSTALL** is set

Examples:

- no options

  $ cmake ..

- no options and FLEDGE_ROOT set

  $ export FLEDGE_ROOT=/some_fledge_setup

  $ cmake ..

- set FLEDGE_SRC

  $ cmake -DFLEDGE_SRC=/home/source/develop/Fledge  ..

- set FLEDGE_INCLUDE

  $ cmake -DFLEDGE_INCLUDE=/dev-package/include ..
- set FLEDGE_LIB

  $ cmake -DFLEDGE_LIB=/home/dev/package/lib ..
- set FLEDGE_INSTALL

  $ cmake -DFLEDGE_INSTALL=/home/source/develop/Fledge ..

  $ cmake -DFLEDGE_INSTALL=/usr/local/fledge ..
