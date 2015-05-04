# com.rajsoft.cordova.gpslocation

This plugin provides information about the device's location, such as
latitude and longitude using Network Provider's location or Global Positioning System (GPS).
There is no guarantee that the plugin returns the
device's actual location.

## Cordova Version
    This plugin is tested on cordova version: 3.5.0

## Installation
    cordova plugin add https://github.com/rajsoft/GPSLocation-Cordova-Plugin.git

## Supported Platforms
    - Android

## Methods
    - navigator.gpslocation.getLocation

### Parameters
    - __gpsLocationHighAccuracy__: _(Boolean)_ Need high accuracy GPS location or not.
    - __callBackSuccess__: The callback that is passed the current position.
    - __callBackError__: _(Optional)_ The callback that executes if an error occurs.

### Example
    var highAccuracy = true; -- If true, get location from gps, otherwise from network provider
    var timeout = 60 * 1000; -- Timeout time for GPS listener
    var max_age = 120 * 1000;-- Max age for returning same location

    navigator.gpslocation.getLocation(highAccuracy, timeout, max_age, onSuccess, onError);
    
    // onSuccess Callback receives a Position object
    //
    var onSuccess = function(position) {
        alert("Latitude: "+ position.latitude + "\n" +
              "Longitude: "+ position.longitude + "\n" +
              "Altitude: "+ position.altitude + "\n" +
              "Accuracy: "+ position.accuracy + "\n" +
              "Heading: "+ position.heading + "\n" +
              "Velocity: "+ position.velocity + "\n" +
              "Timestamp: "+ position.timestamp
        );
    };

    // onError Callback receives a PositionError object
    //
    function onError(error) {
        alert('message: ' + error);
    }
