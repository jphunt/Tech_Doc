###
react-native-vector-icons

```
npm install --save react-native-vector-icons
react-native link
```

issues: Error: While resolving module `react-native-vector-icons/MaterialIcons`, the Haste package `react-native-vector-icons` was found.
```
# add following script to package.json or delete file directly
"scripts": {
    "postinstall": "rm ./node_modules/react-native/local-cli/core/__fixtures__/files/package.json”
}
```

using icons as Image
```
var settingsIcon;
var settingsOutlineIcon;
var peopleIcon;
var iosNavigateOutline;
var iosNavigate;
export default class App {
  constructor() {
    Icon.getImageSource('ios-settings', 30).then((source) => { settingsIcon = source});
    Icon.getImageSource('ios-settings-outline', 30).then((source) => { settingsOutlineIcon = source});
    Icon.getImageSource('ios-people', 30).then((source) => { peopleIcon = source});
    Icon.getImageSource('ios-navigate-outline', 30).then((source) => { iosNavigateOutline = source});
    Icon.getImageSource('ios-navigate', 30).then((source) => { iosNavigate = source});
}

  // Initialise redux, hydrator and persistent stores (left out)
 // startApp is only ever called once redux store has been restored, which always takes longer than
 // the promises above - but the safest way is to implement the Icon.getImageSources as chained 
 // promises or something like that, then kick off 'startApp' after everything is resolved (but this works as a  // quick test

 startApp(root) {
    switch (root) {
        Navigation.startTabBasedApp({
          navigatorStyle: {
            navBarBackgroundColor: '#FFFFFF',
            drawUnderNavBar: true,
            navBarTransparent: true,
            navBarButtonColor: '#F5002A'
          },
          tabs: [
            {
              label: 'Friends',
              screen: 'friends',
              icon: peopleIcon,            
              title: 'Friends',
              navigatorStyle: {

              },
            },
            {
              label: 'Settings',
              screen: 'settings',
              icon: settingsOutlineIcon,
              selectedIcon: settingsIcon,
              title: 'Settings',
              navigatorStyle: {
              },
            }
          ],
          tabsStyle: { // optional, add this if you want to style the tab bar beyond the defaults
            drawUnderTabBar: true,
            tabBarBackgroundColor: '#FFFFFF',
            tabBarSelectedButtonColor: '#F5002A'
          },
          animationType: 'slide-down'
        });
      }
      return;    
      default:
        console.error('Unknown app root');
    }
}
```