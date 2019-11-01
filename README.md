# react-native-ios-wifi

Experimental implementation of automatically connecting to protected WiFi from a react native app. This version supports pod install and is compatible with react-native 0.60 and above


## Getting started

`$ npm install react-native-ios-wifi --save`

### Mostly automatic installation

`$ react-native link react-native-ios-wifi`
`$ cd ios`
`$ pod install`

### Manual installation


1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-ios-wifi` and add `IosWifi.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libIosWifi.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)<


## Usage
```javascript

import WifiManager from 'react-native-wifi';

// Call this method to automatically connect to WiFi with password
try{
    await WifiManager.connectToProtectedSSID(ssid, password, isWep);
}catch (error) {
    console.log("Unable to connect" + error.message);
}

// Call this method to automatically connect to WiFi without password
try{
    await WifiManager.connectToSSID(ssid);
}catch (error) {
    console.log("Unable to connect" + error.message);
}

// Call this method to automatically disconnect from a given WiFi
try{
    await WifiManager.disconnectFromSSID(ssid);
}catch (error) {
    console.log("Unable to disconnect" + error.message);
}

// Call this method to fetch current WiFi details
try{
    const wifiDetails = await WifiManager.getCurrentWifiSSID(ssid);
}catch (error) {
    console.log("Unable to fetch WiFi details" + error.message);
}
```
