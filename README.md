# react-native-navigation-hotreload
Sample project demonstrating that react-native-navigation breaks hot reload.

## Steps taken to setup
1. `react-native init Test; cd Test`
2. `npm i --save react-native-navigation`
3. Setup iOS and Android projects according to react-native-navigation docs
4. Edited js files as seen.

## Hot reload repro steps:
1. Download and extract the attached sample project. Navigate your command prompt into the extracted folder.
2. Run `react-native run-ios` or `react-native run-android` to launch the app in the simulator/emulator.
3. Enable hot reloading (iOS: cmd+D -> Enable Hot Reloading; android: cmd+M -> Enable Hot Reloading)
4. Change to the second tab
5. Change some of the text on the second tab and save.

### Expected
Hot reload would update only the text that changed, leaving the rest of the UI untouched.

### Actual
While the loading bar says "Hot reloading...", it seems to do a full app reload as the entire UI flashes and you are returned to the first tab. Going back to the second tab shows the changes have been made, though.
