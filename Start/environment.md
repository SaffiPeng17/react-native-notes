# 環境建置 Environment

React-Native屬於NodeJS的一個套件，所以在建置開發環境時，要先安裝NodeJS。<br>
以下安裝套件都將以在Terminal上下command的方式進行。

React-Native is a kit belong to NodeJS. If you want to develop React-Native project, you have to install NodeJS first. Please use Terminal to install the tools below.

## Homebrew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

一個macOS使用的套件管理工具。NodeJS的安裝需要使用到這個套件管理工具。<br>
A tool for manage packages in mac OS.

[Homebrew](https://brew.sh/)

## NodeJS

```
brew install node
```

[NodeJS](https://nodejs.org/en/)


## Watchman

```
brew install watchman
```

可以即時查看修改內容的套件。<br>
Display UI immediately after modified.

[Watchman](https://facebook.github.io/watchman/)


## React-Native

```
npm install -g react-native-cli
```

在NodeJS上加入React-Native套件。<br>
Add React-Native kit into NodeJS.

[React-Native](https://facebook.github.io/react-native/)

<br><br>
### References

* [［REACT 隨筆］REACT NATIVE 環境建置 – 適用於 IOS 開發](https://4xsc.com/react-native-introduction-ios/)
* [Introducing Hot Reloading](http://facebook.github.io/react-native/blog/2016/03/24/introducing-hot-reloading.html)
