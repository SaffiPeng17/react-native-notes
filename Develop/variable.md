# 變數 Variables

命名變數有幾個原則。

## const, let, var

#### const

命名變數為常數，類似Ｃ語言的`#define`用法，較多會被放在`class`外面做定義。

```
import React, { Component } from 'react';
import { Text } from 'react-native';

const titleWidth = 250;
const titleHeight = 40;

export default class App extends Component {
    ...
}
```

#### let, var

皆是用來命名可變變數，用`var`命名的變數可以在整個function內使用，但是用`let`命名的變數只有在當下的block內才能使用。

ref.: [ES6 的 var 和 let](http://www.jstips.co/zh_tw/javascript/keyword-var-vs-let/)

```
onTestFunc() {
    ...
    for(var y = 0; y < 5; y++) {
        ...
    }
    for(let z = 0; z < 5; z++) {
        ...
    }
    console.log('y = '+y+', z = '+z);   //Ｘ: y = 5, z = 找不到變數
}
```

## Global variable

#### 狀態全域變數，牽涉UI畫面

根據React的特性，當狀態(包含在內的變數)有任何改變時，就會去重畫(`render()`) UI，因此修改任何狀態內的變數都會觸發`render()`行為來更新UI。所以當這個全域變數與UI有關，如UI的title文字、UI的說明文字...等等，會需要在更新變數之後立即在UI上更新顯示內容的狀況，就會將這個全域變數定義在`this.state`內。


```
import React, { Component } from 'react';
import { Text } from 'react-native';

export default class App extends Component {

  constructor(props) {
    super(props);

    this.state = {
      formulaText: '',
      inputNumber: '',
    };
  }

  onEqualPressed() {
    let formula = this.state.formulaText;   //取得State內的變數
    let iNumber = this.state.inputNumber;

    ...

    //更新State內的變數內容，也會觸發render()
    this.setState({formulaText: formula, inputNumber: iNumber});
  }
}
```

#### 一般全域變數，不牽涉UI畫面

這是比較一般性的全域變數用法，可以在專案內任意地方直接讀取/修改變數。

```
import React, { Component } from 'react';
import { Text } from 'react-native';

export default class App extends Component {

    constructor(props) {
        super(props);

        this.cardinalNumber = 0;    //global variable define
        this.operator = '';
    }

    onPressed(input) {
        ...
        this.cardinalNumber = (this.cardinalNumber == 0) ? Number(iNumber) : this.calculator(Number(iNumber));
        ...
    }
}
```
