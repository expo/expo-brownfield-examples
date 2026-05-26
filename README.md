# brownfield-experiments

A collection of Expo brownfield apps

## Android

- [AntennaPod](https://github.com/gabrieldonadel/AntennaPod): Integrated project using monorepo approach
- [BlankAndroid](https://github.com/gabrieldonadel/BlankAndroid): Integrated project using monorepo approach

## iOS

### UIKit

- [wikipedia-ios](https://github.com/gabrieldonadel/wikipedia-ios): Isolated approach using XCFramework
- [simplenote-react-native](https://github.com/gabrieldonadel/simplenote-react-native): Integrated project using monorepo approach
- [NetNewsWire](https://github.com/gabrieldonadel/NetNewsWire): Integrated project using monorepo approach
- [BlankIOS](https://github.com/gabrieldonadel/BlankIOS): Integrated project using monorepo approach
- [ish](https://github.com/briones-agent/ish): Isolated approach using local Swift Package — Objective-C host with a C/asm core ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/05-ish/recording.mp4))
- [yattee](https://github.com/briones-agent/yattee): Isolated approach using local Swift Package — SwiftUI YouTube player ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/38-yattee/recording.mp4))
- [KeePassium](https://github.com/briones-agent/KeePassium): Isolated approach using local Swift Package — UIKit password manager with **bidirectional shared state** (`useSharedState` ↔ `BrownfieldState`) + native↔RN messaging ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/61-keepassium/recording.mp4))
- [OsmAnd-iOS](https://github.com/briones-agent/OsmAnd-iOS): Isolated approach using local Swift Package (SDK 57 canary) — ObjC++ map app with bidirectional shared map state ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/84-osmand-ios/recording.mp4))

### SwiftUI

- [IceCubesApp](https://github.com/gabrieldonadel/IceCubesApp): Integrated project using monorepo approach
- [wallabag-ios](https://github.com/briones-agent/ios-app): Isolated approach using local Swift Package (SDK 56 canary with the **`expo-image` SPM-deps fix**) — SwiftUI read-it-later app with a bidirectional reading-list inspector ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/90-wallabag-ios/recording.mp4))

## Integration steps

Check commits inside each repo for detailed steps, full instructions can be found in the [expo-brownfield documentation](https://docs.expo.dev/brownfield/overview/).

### Integrated

#### Monorepo

1. **Set up a yarn monorepo**: Create a `package.json` file in the root directory, then add the following to it:

   ```json
   {
     "private": true,
     "workspaces": ["exp"]
   }
   ```

2. **Create the Expo app**: Run `npx create-expo-app exp` to set up a new Expo app.

3. **Install dependencies**: Add expo to you Podfile and run `pod install`

4. **Add React Native view**: Create a new Swift file in the `NetNewsWire-iOS` target, for example `ReactNativeView.swift`, and implement a basic React Native view.

### Isolated

1. **Create the Expo app**: Run `npx create-expo-app exp` to set up a new Expo app.

2. **Install expo-brownfield**: Add expo-brownfield to your project `npx expo install expo-brownfield` and generate a XCFramework.

3. **Add React Native view**: Integrate the Expo app XCFramework into the existing iOS app.
