# brownfield-experiments

A collection of Expo brownfield apps

## Android

- [AntennaPod](https://github.com/gabrieldonadel/AntennaPod): Integrated project using monorepo approach
- [BlankAndroid](https://github.com/gabrieldonadel/BlankAndroid): Integrated project using monorepo approach
- [NewPipe](https://github.com/briones-agent/NewPipe): Isolated approach using AAR (SDK 56 canary) — Kotlin/Java media client, first user of `expo-brownfield build:android --fused` ([PR #45878](https://github.com/expo/expo/pull/45878)) which bundles every autolinked Expo module + heavy transitives into a single AAR ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/02-newpipe/newpipe-expo.mp4))
- [Signal-Android](https://github.com/briones-agent/Signal-Android): Isolated approach using AAR (SDK 56) — Kotlin messenger built with the fused mode from [PR #47921](https://github.com/expo/expo/pull/47921); exercises real host-conflict handling: Glide 4.15 vs expo-image's Glide 5, Signal's Compose stack vs `@expo/ui`'s compose alphas (autolinking exclude + Metro stub), release-variant pinning for `react-android`/`hermes-android` in a debug host, and Gradle dependency-verification metadata ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/03-signal-android/recording.mp4))
- [organicmaps](https://github.com/briones-agent/organicmaps): Isolated approach using AAR (SDK 57 canary) — C++/Java offline maps app built with the fused mode from [PR #47921](https://github.com/expo/expo/pull/47921); exercises a Java host (`BrownfieldLifecycleDispatcher.INSTANCE`), a minSdk 21 → 24 bump for React Native 0.86, and manifest-merger overrides to keep the AAR's legacy storage permissions out of a host with a build-time permission allowlist ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/06-organicmaps/recording.mp4))
- [thunderbird-android](https://github.com/briones-agent/thunderbird-android): Isolated approach using AAR (SDK 57 canary) — Kotlin/Java email client (Thunderbird for Android / K-9 Mail) and the first app consuming the fused AAR **from a remote Maven repository** ([briones-agent/packages](https://github.com/briones-agent/packages), a static `maven/` layout served over `raw.githubusercontent.com`): no `expo-app/` in the fork at all, just a repo URL + `implementation("dev.expo.brownfield:expobrownfield-fused-release:1.0.1")` + an `ExpoActivity`, wired into the message-list overflow menu of both white-label apps ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/07-thunderbird-android/recording.mp4))

## iOS

### UIKit

- [wikipedia-ios](https://github.com/gabrieldonadel/wikipedia-ios): Isolated approach using XCFramework
- [simplenote-react-native](https://github.com/gabrieldonadel/simplenote-react-native): Integrated project using monorepo approach
- [NetNewsWire](https://github.com/gabrieldonadel/NetNewsWire): Integrated project using monorepo approach
- [BlankIOS](https://github.com/gabrieldonadel/BlankIOS): Integrated project using monorepo approach
- [ish](https://github.com/briones-agent/ish): Isolated approach using local Swift Package — Objective-C host with a C/asm core ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/05-ish/recording.mp4))
- [KeePassium](https://github.com/briones-agent/KeePassium): Isolated approach using local Swift Package — UIKit password manager with **bidirectional shared state** (`useSharedState` ↔ `BrownfieldState`) + native↔RN messaging ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/61-keepassium/recording.mp4))
- [OsmAnd-iOS](https://github.com/briones-agent/OsmAnd-iOS): Isolated approach using local Swift Package (SDK 57 canary) — ObjC++ map app with bidirectional shared map state ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/84-osmand-ios/recording.mp4))
- [firefox-ios](https://github.com/briones-agent/firefox-ios): Isolated approach using local Swift Package (SDK 56 canary) — UIKit browser with a Bookmarks Inspector RN screen wired through Firefox's custom `Fennec` build configurations + Swift 6 strict concurrency ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/08-firefox-ios/recording.mp4))
- [Signal-iOS](https://github.com/briones-agent/Signal-iOS): Isolated approach using local Swift Package (SDK 56 canary) — UIKit messenger demonstrating the **Navigation API** (`popToNative()` from JS + `setNativeBackEnabled`) with a Safety Center RN screen + `expo-image` avatars via **`hostProvidedFrameworks`** ([SDWebImage shared with the host's CocoaPods runtime](https://github.com/expo/expo/pull/46355)) ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/10-signal-ios/recording.mp4))
- [Nextcloud-iOS](https://github.com/briones-agent/Nextcloud-iOS): Isolated approach using local Swift Package (SDK 56 canary) — UIKit cloud-files client with a Files Quick Look RN screen (storage quota bar + shared-file indicators), Navigation API + DCO-signed commits ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/51-nextcloud-ios/recording.mp4))
- [pocket-casts-ios](https://github.com/briones-agent/pocket-casts-ios): Isolated approach using local Swift Package (SDK 56 canary) — UIKit podcast app demonstrating the **`ExpoAppDelegateSubscriberManager` lifecycle pipeline** (host AppDelegate forwards every `UIApplicationDelegate` event into an `ExpoAppDelegateSubscriber` that records to `BrownfieldState`; live event feed rendered in the RN Lifecycle Trace screen) ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/60-pocket-casts-ios/recording.mp4))
- [OnionBrowser](https://github.com/briones-agent/OnionBrowser): Isolated approach using a **shared, prebuilt _remote_ Swift Package** (SDK 57.0.0) built once and reused across apps — UIKit Tor browser; RN screen presented on a dedicated `UIWindow` overlay (`.alert + 1`) from a floating "Expo" entry button ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/48-onionbrowser/recording.mp4))
- [mastodon-ios](https://github.com/briones-agent/mastodon-ios): Isolated approach using a **shared, prebuilt _remote_ Swift Package** (SDK 57.0.0) built once and reused across apps — UIKit Mastodon client (SPM-based, `MastodonSDK` local package); RN screen presented on a dedicated `UIWindow` overlay from a floating "Expo" entry button ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/53-mastodon-ios/recording.mp4))
- [openhab-ios](https://github.com/briones-agent/openhab-ios): Isolated approach using the shared, prebuilt remote Swift Package (SDK 57.0.0, [PR #48065 packaging fixes](https://github.com/expo/expo/pull/48065)) — UIKit smart-home controller (SPM-based, Firebase); RN screen presented on a dedicated `UIWindow` overlay from a floating "Expo" entry button ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/89-openhab/recording.mp4))
- [mammoth](https://github.com/briones-agent/mammoth): Isolated approach using a **shared, prebuilt _remote_ Swift Package** (SDK 57.0.0, built with the [expo-brownfield CLI fixes from PR #48065](https://github.com/expo/expo/pull/48065)) built once and reused across apps — UIKit Mastodon client (SPM-based, uses Arkana-obfuscated secrets); RN screen presented on a dedicated `UIWindow` overlay from a floating "Expo" entry button, bootstrapped from the `AppDelegate` ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/91-mammoth/mammoth.mp4))

### SwiftUI

- [IceCubesApp](https://github.com/gabrieldonadel/IceCubesApp): Integrated project using monorepo approach
- [yattee](https://github.com/briones-agent/yattee): Isolated approach using local Swift Package — SwiftUI YouTube player ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/38-yattee/recording.mp4))
- [wallabag-ios](https://github.com/briones-agent/ios-app): Isolated approach using local Swift Package (SDK 56 canary with the **`expo-image` SPM-deps fix**) — SwiftUI read-it-later app with a bidirectional reading-list inspector ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/90-wallabag-ios/recording.mp4))
- [element-x-ios](https://github.com/briones-agent/element-x-ios): Isolated approach using local Swift Package (SDK 56 canary) — SwiftUI Matrix client built on Element X's `AppCoordinator` / WindowGroup architecture, with a React Native **Safety Dashboard** presented on a dedicated `UIWindow` overlay (`.alert + 1`) so it floats over the SwiftUI scene without fighting the host's view-swap flow; bidirectional shared state (encrypted-sessions, verified-devices, recent-rooms feed), `BrownfieldMessaging` (`OPEN_ROOM` / `VERIFY_KEYS`), Navigation API (`popToNative()`), and `expo-image` avatars ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/75-element-x-ios/recording.mp4))
- [damus](https://github.com/briones-agent/damus): Isolated approach using a **shared, prebuilt _remote_ Swift Package** (SDK 57.0.0) built once and reused across apps — SwiftUI Nostr client (`@main App` + `WindowGroup`); RN screen presented on a dedicated `UIWindow` overlay from a floating "Expo" entry button ([recording](https://raw.githubusercontent.com/expo/expo-brownfield-examples/media/56-damus/recording.mp4))

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
