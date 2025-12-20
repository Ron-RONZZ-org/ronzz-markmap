# React Native

## Learn once, write anywhere

- Multiplatform
  - Web
  - iOS
  - Android

- Instant update
  - Javascript delivery

- Dependencies
  - node.js

- Suggested IDE
  - VSCode
        - Expo tools
        - React Native tools
        - code expander
            - `dsznajder.es7-react-js-snippets`
              - [snippet](https://github.com/r5n-labs/vscode-react-javascript-snippets/blob/HEAD/docs/Snippets.md)
                - `rnfe`
    - Git

## Project mangement

- creation
  - `npx create-expo-app@latest`
- start development server
  - `npx expo start --dev-client`

## Project Structure

- `package.json`
  - Package and version control
  - App styling
    - Icon
    - Name
    - Splash screen
- `tsx`
  - `index.tsx`
    - Default page
  - `_layout.tsx`
    - `<Stack>`
    - `<Tabs>`
    - optional overwrite direct in page `tsx`s.
  - `not-found.tsx`
  - `tsconfig.json`
    - Control which `tsx,jsx`s are included
    - 404
  - `(group)`
    - A group of tabs
- `assets`
  - `images`
  - `fonts`
- `constants`
  - `Color.ts`
- `components`
  - `ui`
    - `IconSymbol`
    - `TabBarBackground`

## Threads

- UI thread
- JS thread
- Native module thread
- Render thread
  
## Components

- Dumb
  - UI concerned
  - Most reusable
- Smart

## Page structure

### import

```javascript
import GIVEN_NAME, { PARA_NAME, ... } from ADDRESS
```

- `GIVEN_NAME`: import default export
- `PARA_NAME`: import named values

```javascript
import { View, Text, StyleSheet, ImageBackground, Button, Alert } from 'react-native'
import React from 'react'
```

- react-native
  - View: app view
  - Text
  - StyleSheet
  - ImageBackground
  - Pressable: buttons

### App

```javascript
const app = () => {
  //
  return (
    <View style={styles.container}>
    <!-->
    </View>
  );
}
export default app
```

### Style

```typescript
import { StyleSheet } from 'react-native';
import { Dimensions } from 'react-native';
const { width, height } = Dimensions.get('window');
const styles = StyleSheet.create({
  container: {
      backgroundColor: 'rgba(0,0,0,0.5)',
      flexDirection: 'column',
      alignItems: 'center',
      justifyContent: 'center', // Added to center content vertically
      opacity: 1,
      alignSelf: 'center',
  },
  bgImage: {
    height: height,
    width: width,
    justifyContent:'center',
    // opacity: 0.5,
  },
  text: {
    color: 'white',
    fontSize: 42,
    fontWeight: 'bold',
    textAlign: 'center',
    backgroundColor: 'rgba(0,0,0,0.5)',
    }
  })
```
*\*:Be careful with opacity. React-native renders everything in background image as a composite layer to ensure touch propagation. Therfore, `opacity: 0.5` in `{style.bgImage}` would affect everything on the screen.*

For more styling options, see [styles_reactNative](styles_reactNative.md)

### Navigation

#### Link

```javascript
import {Link} from 'expo-router'
<Link href="explore">Explore</Link>
```

#### Button

```javascript
<Button onPress={onPressButton} 
              title="Press Me" color="green" />
```

```javascript
      <Link href="explore" style={styles.link} asChild>
      <Pressable style={styles.button}>
        <Text style={styles.buttonText}>Explore</Text>
      </Pressable>
      </Link>
```

```javascript
class App extends Component {
  state = {
    count: 0,
  };

  onPress = () => {
    this.setState({
      count: this.state.count + 1,
    });
  };

  render() {
    return (
      <View style={styles.container}>
        <TouchableOpacity style={styles.button} onPress={this.onPress}>
          <Text>Click me</Text>
        </TouchableOpacity>
        <View>
          <Text>You clicked {this.state.count} times</Text>
        </View>
      </View>
    );
  }
}
```

#### Stacks&Tabs

```javascript
import { Stack } from 'expo-router';
export default function StackLayout() {
  return (  <Stack>
    <Stack.Screen name="index" options={{ title: "Accueil" }} />
    <Stack.Screen name="details" options={{ title: "Détails" }} />
  </Stack>
);
}
```

```javascript
import { Tabs} from 'expo-router';
export default function TabLayout() {
  const colorScheme = useColorScheme();

  return (
    <Tabs
      screenOptions={{
        tabBarActiveTintColor: Colors[colorScheme ?? 'light'].tint,
        headerShown: false,
        tabBarButton: HapticTab,
        tabBarBackground: TabBarBackground,
        tabBarStyle: Platform.select({
          ios: {
            // Use a transparent background on iOS to show the blur effect
            position: 'absolute',
          },
          default: {},
        }),
      }}>
      <Tabs.Screen
        name="index"
        options={{
          title: 'Home',
          tabBarIcon: ({ color }) => <IconSymbol size={28} name="house.fill" color={color} />,
        }}
      />
      <Tabs.Screen
        name="explore"
        options={{
          title: 'Explore',
          tabBarIcon: ({ color }) => <IconSymbol size={28} name="paperplane.fill" color={color} />,
        }}
      />
    </Tabs>
  );
}
```

##### Icons

```javascript
<IconSymbol size={28} name="heart.fill" color={color}/>
```

###### react-native-vector-icons

| Material Icon Name | Description    |
|------------------|---------------|
| `home`          | Maison        |
| `explore`       | Explorer      |
| `shopping_cart` | Panier        |
| `favorite`      | Favoris       |
| `settings`      | Paramètres    |
| `person`        | Utilisateur   |
| `notifications` | Notifications |

###### Apple ecosystem

| SF Icon Name | Description (in Romantic French) |
|-----------|------------|
| `house.fill` | Maison |
| `magnifyingglass` | Loupe |
| `book.fill` | Livre |
| `star.fill` | Étoile |
| `heart.fill` | Cœur |
| `person.fill` | Utilisateur |
| `gearshape.fill` | Paramètres |
| `cart.fill` | Panier |
| `bell.fill` | Cloche |

***Manual mapping** required at `components/ui/IconSymbol.tsx` for cross-platform compatibility.*

##### Alternative Icons: \<Ant Design\>

```javascript
<AntDesign name="star" size={24} color="black" />
```
[Available Icon List](https://icons.expo.fyi/Index/AntDesign/staro)

##### Navigation bar tinting:

`constants/Colors.ts`

```javascript
const tintColorLight = '#0a7ea4';
const tintColorDark = '#fff';

export const Colors = {
  light: {
    text: '#11181C',
    background: '#fff',
    tint: tintColorLight,
    icon: '#687076',
    tabIconDefault: '#c68e17',
    tabIconSelected: tintColorLight,
  },
  dark: {
    text: '#ECEDEE',
    background: '#151718',
    tint: tintColorDark,
    icon: '#9BA1A6',
    tabIconDefault: '#9BA1A6',
    tabIconSelected: tintColorDark,
  },
};
```

#### Hooks

```javascript
import { useNavigation } from '@react-navigation/native';
const navigation = useNavigation();
navigation.navigate('worship');
```

### Animation and indicators

#### Status Bar (Phone)

```javascript
import { StatusBar } from 'expo-status-bar';
<StatusBar style="auto" />
```

#### Avtivity indicator

```javascript
<ActivityIndicator size="large" color="lightgreen"/> 
```

### Store and reuse

#### Dumb component/Props

```javascript
const Function = (props) => {
 return(
   ...code of creating any element
 )
}
```

Creating a custom element to be reused across app.

```javascript
function ImageFill(props) { 
    return ( 
        <View style={styles.contStyle}> 
            {[...Array(props.count)].map( 
        () => ( 
          <Image source={props.image} style = {{height: 100,width: 100,  
          flex:1, flexWrap:'wrap'}}/> 
        ) 
      )} 
        </View> 
    ); 
} 
```

```javascript
import ImageFill from './ImageFill'; 
  
// Exporting default component 
export default function App() { 
  return ( 
    <ScrollView style={styles.container}> 
      <ImageFill image = {require('./assets/gfglogo.png')}  
      count = {4}/> 
    </ScrollView> 
  ); 
} 
```

#### Asynchronous storage

```bash
npm install @react-native-async-storage/async-storage
```

```javascript
  const [data , setdata] = useState("");
  const add = async ()=>{
    try {
      await AsyncStorage.setItem('gfg', "GeeksforGeeks")
    }
    catch (e){
      console.error(e);
    }
  }

  const get = async () => {
    try {
      const value = await AsyncStorage.getItem('gfg')
      if(value !== null) {
          setdata(value);
      }
    }  catch (e){
      console.error(e);
    }
  }
    return (
    <View style={styles.container}>
        <Text style={styles.text}>{data}</Text>
        <View style={styles.button} >
          <Button
            title={"add"}
            onPress={add}
          />
        </View>
        <View style={styles.button} >
          <Button
            title={"get"}
            onPress={get}
          />
        </View>
</View>
  );
  ```

## App logic

- await

## Learning React.js

- Project series
  - Hello World!
  - Counter!