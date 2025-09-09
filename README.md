# brownfield-experiments

A collection of Expo brownfield apps

## Android

- [AntennaPod](https://github.com/gabrieldonadel/AntennaPod): Integrated project using monorepo approach

## iOS

### UIKit

- [simplenote-react-native](https://github.com/gabrieldonadel/simplenote-react-native): Integrated project using monorepo approach
- [NetNewsWire](https://github.com/gabrieldonadel/NetNewsWire): Integrated project using monorepo approach
- [BlankIOS](https://github.com/gabrieldonadel/BlankIOS): Integrated project using monorepo approach

### SwiftUI

- [IceCubesApp](https://github.com/gabrieldonadel/IceCubesApp): Integrated project using monorepo approach

## Integration steps

Check commits inside each repo for detailed steps

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
