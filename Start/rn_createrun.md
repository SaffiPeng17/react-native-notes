# 建立＆執行專案 Create & Run


<br>
## Create React-Native Project

```
react-native init (project name)
```

* (project name): 自定義專案名稱

Example:

```
react-native init FirstRNProject
```

執行建立專案 command 之後，會自動建立 iOS ＆ Android 各自的專案，並且補上執行專案需要用到的檔案，其中部分的 JS Files 還包含了簡單的 iOS ＆ Android 共用 App UI，所以需要等待一些建立時間。

最後，在建立完成之後會出現建立的專案路徑。

```
This will walk you through creating a new React Native project in /(file path)/(project name)
```

(file path) 會是你執行 建立專案command 當下所在的路徑。若是想要指定專案路徑，有兩個方法操作，

1. 在 建立專案command 上指定專案路徑

```
react-native init /(specify file path)/(project name)
```

Example:

```
react-native init /User/MyLoad/Document/Project/FirstRNProject
```

2. 先切換到想要建立專案的路徑，再執行 建立專案command

```
//將當前路徑切換到 (specify file path)
cd (specify file path)
react-native init (project name)
```

Example:

```
cd /User/MyLoad/Document/Project
react-native init FirstRNProject
```

<br>
## Run React-Native Project (iOS)

建立專案完成之後，會跳出執行專案的 command 說明可供參考。

![Run iOSAndroid](/images/run_iosandroid_pj.png)

**＊方法 1.**

使用 command 來執行專案。

```
//將當前路徑切換到 (project name)
cd (project name)
react-native run-ios
```

Example:

```
cd FirstRNProject
react-native run-ios
```

若是在執行 command 之後跳出了以下的錯誤，

![Run iOS Error](/images/run_ios_error.png)

解決辦法，

1. 開啟 Xcode
2. 進入 Preferences
3. 開啟 Locations Tab
4. 設定 Command Line Tools

    選項基本上都只有一個，版本就是你現在的 Xcode 版本，不必非要哪種版本才可以。

    ![Setup Cmd Line](/images/setup_xcode_cmdline.png)

ref.: [Error Running React Native App From Terminal (iOS)](https://stackoverflow.com/questions/39778607/error-running-react-native-app-from-terminal-ios)

**＊方法 2.**

直接在 Xcode 開啟 iOS 專案，並任擇一模擬器執行專案。

<br>
以上為使用模擬器執行專案的方法，若是想在真實手機上執行專案，就只能用 Xcode。

1. 開啟 Xcode
2. 在專案設定內的 Signing 加入你的 Apple ID
3. 使用傳輸線連接你的 Mac 電腦與手機

ref.: [［REACT 隨筆］專案 APP IPHONE 實機測試](https://4xsc.com/react-app-on-iphone/)

<br><br>
### References

* [［REACT 隨筆］REACT NATIVE – 建立專案 HELLO WORLD](https://4xsc.com/react-native-hello-world/)
