# React Native GANG 🥶 
![image](https://github.com/ikhlasdansantai/react-native-jouney/assets/95151018/d0107b27-c240-4752-aee2-8f6a231c62ba)
Home overview

## Day 1 (Slicing Auth UI)
![image](https://github.com/ikhlasdansantai/react-native-jouney/assets/95151018/c21348b5-59de-490b-8e58-70a09c113398)
Yang dipelajari disini adalah
1. kalo mau buat linear gradient, gak bisa pake `bg-gradient-to-b from-red-300 to-red-600`, tapi pake lib nya `expo-linear-gradient` :v
2. ada beberapa styling yang gak ada di react native, contohnya, `dvh, ch, bg-gradient, transition, dll`
3. statusbar, ternyata bisa di hidden, gak harus pake `style="dark"` atau `style="light"`, buat ngakalin biar statusbar nya "ilang"
4. Bisa langsung pake `<Stack.Screen options={{}} />`, tanpa _layout, karena klo pake layout, harus di define dulu nama atau target nya apa, jadi langsung aja pake di componentnya



## Day 2 (Spash Screen)
https://github.com/ikhlasdansantai/react-native-jouney/assets/95151018/8bfd6eb6-84c2-4be1-8adb-c10ffa55eb34
1. buat animasi disini, kudu mesti pake lib nya `react-native-animated`
2. ada banyak pilihan untuk comp `Animated`, mulai dari `Animated.View, Animated.Text, Animated.Image, dll`, dan kita bisa kasih animasinya dengan prop `entering` & `exiting`
3. klo mau trigger animasinya, misal disini, karena bikin tabs, yang dimana animasinya ke trigger klo comp nya di render-ulang, kita bisa kasih `key prop`
4. kalo mau atur berapa lama durasi + delay, bisa langsung diconfig di inline-comp nya, `FadeIn.duration(600)` / `FadeOut.duration(600)`
5. ternyata bikin fitur swipe itu, tidak sesimple itu
6. ada banyak method untuk capture gesture, bisa diatur di method Fling() nya, bisa atur di param method `.direction(Directions.RIGHT | Directions.LEFT, dll)`
7. cara yang dipake sebelumnya yaitu
   ```tsx
   const handleForward = () => (tab === tabDatas.length - 1 ? handleSkip() : setTab(tab + 1));
   
   const swipeRight = Gesture.Fling()
    .direction(Directions.RIGHT)
    .onEnd((e) => {
      // handleForward()
    });
   ```
   Mengakibatkan force close, ketika di swipe, akhirnya solusi ini tersolve disini
   [Solusinya hehe]https://stackoverflow.com/questions/73893490/gesturedetector-gesture-handler-app-crash-when-calling-external-function
   ```tsx
   const swipeRight = Gesture.Fling()
    .direction(Directions.RIGHT)
    .onEnd(() => runOnJS(handleBackward)());
   ```
8. 
