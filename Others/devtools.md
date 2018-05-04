# 開發工具 Develop Tools

* 開發IDE : [Atom](https://atom.io/)
* 版本控制 : [Git](https://git-scm.com/)
* Git空間 : [GitHub](https://github.com/), [Bitbucket](https://bitbucket.org/)
* 開發紀錄 : [GitBook](https://www.gitbook.com/)

## Atom

**附加功能套件** : 推薦

* [react-snippets](https://atom.io/packages/react-snippets)
* [language-javascript-jsx](https://atom.io/packages/language-javascript-jsx)
* [Highlight Selected](https://atom.io/packages/highlight-selected)

**安裝步驟**

1. 點開Atom menu bar上的 **Packages**
2. 選擇 **Settings View** ➔ **Open**
3. 選擇 **Install** tab
4. 在搜尋列上輸入套件名稱進行搜尋
5. 在結果中選擇要安裝的套件按下 **Install**

## GitBook

在修改了任何內容後，想要立即查看顯示結果的話可以使用command，

```
cd (gitbook folder)
gitbook serve
```

* **(gitbook folder)**

    你的GitBook資料夾，預設路徑會是 `/Users/(username)/GitBook/Library/(gitbook username)/(gitbook folder)`

執行command後，gitbook會將你的GitBook轉換成網頁版本放至`../myGitbook/_book/`，並將網頁版部署在 [http://localhost:4000](http://localhost:4000)，只要使用瀏覽器打開這個網址就可以看到顯示結果。<br/>
所有的GitBook在執行`gitbook serve`之後，都會部署到同樣的網址上，所以網址上顯示的只會是 **最後一次部署** 的GitBook內容。
