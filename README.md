1. npx create-expo-app@latest StickerSmash && cd StickerSmash

- 템플릿을 사용하여 StickerSmash라는 새 프로젝트 디렉터리를 생성합니다.

2. npm run reset-project

- 보일러플레이트 코드를 제거해 보겠습니다.

3. npx expo start

- 개발 서버가 시작되고 터미널 창 내부에 QR 코드가 표시됩니다.
- 기기에서 앱을 열려면 QR 코드를 스캔하세요. Android에서는 Expo Go > QR 코드 스캔 옵션을 사용하세요. iOS에서는 기본 카메라 앱을 사용하세요.
- 웹 앱을 실행하려면 w터미널에서 버튼을 누르세요. 기본 웹 브라우저에서 웹 앱이 열립니다.

4. 간단한 스타일링

```
import { Text, View,  StyleSheet } from 'react-native';

export default function Index() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Home screen</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    color: '#fff',
  },
});

```

5. 페이지 추가

```
import { Text, View, StyleSheet } from "react-native";

export default function AboutScreen() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>About screen</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#25292e",
    justifyContent: "center",
    alignItems: "center",
  },
  text: {
    color: "#fff",
  },
});

```

6. 경로 제목 업데이트

```
import { Stack } from 'expo-router';

export default function RootLayout() {
  return (
    <Stack>
      <Stack.Screen name="index" options={{ title: 'Home' }} />
      <Stack.Screen name="about" options={{ title: 'About' }} />
    </Stack>
  );
}

```

7. 화면 간 이동

```
import { Text, View, StyleSheet } from 'react-native';
 import { Link } from 'expo-router';

export default function Index() {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Home screen</Text>
      <Link href="/about" style={styles.button}>
        Go to About screen
      </Link>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    alignItems: 'center',
    justifyContent: 'center',
  },
  text: {
    color: '#fff',
  },
  button: {
    fontSize: 20,
    textDecorationLine: 'underline',
    color: '#fff',
  },
});

```

8. not-found 경로 추가

```
import { View, StyleSheet } from 'react-native';
import { Link, Stack } from 'expo-router';

export default function NotFoundScreen() {
  return (
    <>
      <Stack.Screen options={{ title: 'Oops! Not Found' }} />
      <View style={styles.container}>
        <Link href="/" style={styles.button}>
          Go back to Home screen!
        </Link>
      </View>
    </>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#25292e',
    justifyContent: 'center',
    alignItems: 'center',
  },

  button: {
    fontSize: 20,
    textDecorationLine: 'underline',
    color: '#fff',
  },
});

```

9. 탭 네비게이션 추가

```
import { Tabs } from "expo-router";

import Ionicons from "@expo/vector-icons/Ionicons";

export default function TabLayout() {
  return (
    <Tabs
      screenOptions={{
        tabBarActiveTintColor: "#ffd33d",
        headerStyle: {
          backgroundColor: "#25292e",
        },
        headerShadowVisible: false,
        headerTintColor: "#fff",
        tabBarStyle: {
          backgroundColor: "#25292e",
        },
      }}
    >
      <Tabs.Screen
        name="index"
        options={{
          title: "Home",
          tabBarIcon: ({ color, focused }) => (
            <Ionicons
              name={focused ? "home-sharp" : "home-outline"}
              color={color}
              size={24}
            />
          ),
        }}
      />
      <Tabs.Screen
        name="about"
        options={{
          title: "About",
          tabBarIcon: ({ color, focused }) => (
            <Ionicons
              name={
                focused ? "information-circle" : "information-circle-outline"
              }
              color={color}
              size={24}
            />
          ),
        }}
      />
    </Tabs>
  );
}

```

10. 이미지 사용

```
npx expo install expo-image
```

11. 이미지 선택기

```
npx expo install expo-image-picker
```

12. 모달 열기

```
<Pressable style={styles.button}  onPress={onPress}>
```

13. 제스처 추가

```
import { GestureHandlerRootView } from "react-native-gesture-handler";
```

14. 카메라 권한 요청

```
usePermissions()hook from을 사용하면 expo-media-library권한 permissionResponse과 requestPermission()메서드를 사용하여 접근 권한을 요청할 수 있습니다.
```
