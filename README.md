# react-native-ios-wifi

## Getting started

`$ npm install react-native-ios-wifi --save`

### Mostly automatic installation

`$ react-native link react-native-ios-wifi`

### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-ios-wifi` and add `IosWifi.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libIosWifi.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)<

#### Android

1. Open up `android/app/src/main/java/[...]/MainApplication.java`
  - Add `import com.reactlibrary.IosWifiPackage;` to the imports at the top of the file
  - Add `new IosWifiPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-ios-wifi'
  	project(':react-native-ios-wifi').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-ios-wifi/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-ios-wifi')
  	```


## Usage
```javascript

import WifiManager from 'react-native-wifi';

WifiManager.connectToProtectedSSID(ssid, password, isWep)
.then(() => {
console.log('Connected successfully!')
}, () => {
console.log('Connection failed!')
})

```
