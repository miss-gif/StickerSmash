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
