# 第三方套件 Third Party

網路上有許多免費開源的第三方套件，例如一些已經設計好的UI component，可以直接引用進專案就不用自己刻，這也是 *敏捷開發* 的基本概念。

[GitHub](https://github.com/) 上就有許多第三方套件可以應用，但是要注意授權狀態不要侵權。

## How to use

大部分的第三方套件作者在分享時都會一併附上使用說明，基本上大多是使用command來安裝(下載)，

```
npm install (third party name)
```

* **(third party name)** : 第三方套件名稱

<br>
安裝好第三方套件之後，使用方式是將第三方套件內想要使用的component `import` 進專案：

```
import (component name) from '(third party name)'
```

* **(component name)** : 要引用第三方套件內的哪個component進來

<br>
這邊有個漂亮的 Button套件 可以拿來練練手 : [apsl-react-native-button](https://github.com/APSL/react-native-button)
