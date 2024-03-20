 ERROR  Error: A navigator cannot contain multiple 'Screen' components with the same name (found duplicate screen named 'settings')

This error is located at:
    in NativeStackNavigator (created by App)
    in EnsureSingleNavigator
    in BaseNavigationContainer
    in ThemeProvider
    in NavigationContainerInner (created by App)
    in TimeTableProvider (created by App)
    in App (created by withDevTools(App))
    in withDevTools(App)
    in RCTView (created by View)
    in View (created by AppContainer)
    in RCTView (created by View)
    in View (created by AppContainer)
    in AppContainer
    in main(RootComponent), js engine: hermes



    import HomeView from './src/View/HomeView'
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import TimeTable from './src/View/TimeTableView'
import BikeView from './src/View/BikeView'
import WeatherView from './src/View/weather'
import TimeTableRoot from './src/View/TimeTableViewNavigateRoot'
import ASetting from './src/View/ASetting';
import { TouchableOpacity } from 'react-native';
import { AntDesign } from '@expo/vector-icons';
import TimeTableSetting from './src/View/TimeTableSetting';
import { TimeTableProvider } from './src/component/TimeTable/TimeTableContext'; 

import ALoginView from './src/View/ALoginView';

const Stack = createNativeStackNavigator();

function App() {
  return (
    <TimeTableProvider>
      <NavigationContainer>
        <Stack.Navigator initialRouteName='Home'>
          <Stack.Screen name="Home" component={HomeView} options={{ headerShown: false }}/>
          <Stack.Screen name="TimeTable" component={TimeTable} 
            options={({ navigation }) => ({ 
              title: '',
              headerRight: () => (
                <TouchableOpacity onPress={() => navigation.navigate('TimeTableSetting')}>
                  <AntDesign name="ellipsis1" size={24} color="black" />
                </TouchableOpacity>
              ),
            })} />
          <Stack.Screen name="Bike" component={BikeView}/>
          <Stack.Screen name="weather" component={WeatherView}/>
          <Stack.Screen name="settings" component={ASetting} />
          <Stack.Screen name="TimeTableSetting" component={TimeTableSetting} options={{ title: '' }} />
          <Stack.Screen name="settings" component={ASetting}/>
          <Stack.Screen name="login" component={ALoginView} options={{ headerShown: false }}/>
          <Stack.Screen name="TimeTableSetting" component={TimeTableSetting} />
        </Stack.Navigator>
      </NavigationContainer>
    </TimeTableProvider>
  );
}


export default App;


error: Your local changes to the following files would be overwritten by merge:
        frontend/App.js
        frontend/package-lock.json
        frontend/yarn.lock
Please commit your changes or stash them before you merge.
Aborting
Updating 63c5db1..af08013



git checkout -- frontend/App.js frontend/package-lock.json frontend/yarn.lock

    
 ERROR  Invariant Violation: "main" has not been registered. This can happen if:
* Metro (the local dev server) is run from the wrong folder. Check if Metro is running, stop it and restart it in the current project.
* A module failed to load due to an error and `AppRegistry.registerComponent` wasn't called., js engine: hermes


https://prod.liveshare.vsengsaas.visualstudio.com/join?C6FF17EF709DE9EDE1A380429A67733DFF69
