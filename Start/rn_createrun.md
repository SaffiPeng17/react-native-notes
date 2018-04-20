# 建立＆執行專案 Create & Run

環境準備完成之後，就可以開始建立React-Native專案。

## Create React-Native Project

```
react-native init (project name)
```

* (project name): 自定義專案名稱

Example:

```
react-native init FirstRNProject
```

執行 建立專案command 之後，會自動建立iOS＆Android各自的專案，並且補上執行專案需要用到的檔案，其中部分的JS Files還包含了簡單的iOS＆Android共用App UI，所以需要等待一些建立時間。
<br>
最後，在建立完成之後會出現建立的專案路徑。

```
This will walk you through creating a new React Native project in /(file path)/(project name)
```

(file path) 會是你執行 建立專案command 當下所在的路徑。若是想要指定專案路徑，有兩個方法，

1. 在 建立專案command 上指定專案路徑

	```
	react-native init /User/MyLoad/Document/Project/FirstRNProject
	```

2. 先把當前路徑切換到想要放置專案的路徑，再執行 建立專案command

	```
	cd /User/MyLoad/Document/Project
	react-native init FirstRNProject
	```

## Run React-Native Project (iOS)

建立專案完成之後，會跳出 執行專案command 的說明可供參考。<br>

![Run iOSAndroid](/images/run_iosandroid_pj.png)

<br>
**＊方法 1. 使用command來執行專案**

```
cd FirstRNProject
react-native run-ios
```
<br>
在執行command之後，若未正常執行專案，而是跳出如下方圖片的錯誤，<br>

![Run iOS Error](/images/run_ios_error.png)

就依照以下步驟來解決，

1. 開啟 **Xcode**
2. 進入 **Preferences**
3. 開啟 **Locations** Tab
4. 設定 **Command Line Tools** <br>
    選項基本上只有一個，版本就是你現在的 Xcode 版本，不必非要選擇哪種版本。<br>

    ![Setup Cmd Line](/images/setup_xcode_cmdline.png)

ref.: [Error Running React Native App From Terminal (iOS)](https://stackoverflow.com/questions/39778607/error-running-react-native-app-from-terminal-ios)

**＊方法 2. 用Xcode開啟iOS專案，並任擇一模擬器執行專案。**

<br>
以上為使用模擬器執行專案的方法，若是想在真實手機上執行專案，就只能用Xcode。<br>

1. 開啟 **Xcode**
2. 在專案設定內的 **Signing** 加入你的 **Apple ID**
3. 使用傳輸線連接你的Mac電腦與手機
4. 選擇連接的手機並執行專案

ref.: [［REACT 隨筆］專案 APP IPHONE 實機測試](https://4xsc.com/react-app-on-iphone/)

<br><br>
### References

* [［REACT 隨筆］REACT NATIVE – 建立專案 HELLO WORLD](https://4xsc.com/react-native-hello-world/)
