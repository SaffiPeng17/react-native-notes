# Git

版本控制系統，遠端空間是使用GitHub，UI操作版本可以參考 [Source Tree](https://www.sourcetreeapp.com/)。以下紀錄一些比較常用到的command。<br>
Record some common git commands here. (Use GitHub)

## Create repository

可以直接在網頁上操作，或是使用下方command。<br>
You could create a new repository on the GitHub website. If you would like to use command, you could reference the command below.

```
echo "# newrepository" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/myGit/newrepository.git
git push -u origin master
```

* `git init`

    在現在的folder內建立一個XXX.git檔案

* `git remote add origin https://github.com/myGit/newrepository.git`

    增加遠端的repository

## Common git flow

1. Clone遠端repository (Clone remote repository)
2. 增加/修改檔案 (Add/Modified any file)
2. 將修改的檔案commit (Commit the modified files)
3. Push已經commit的檔案到遠端repository (Push to remote repository)

**＊記得 *每一個* 有修改到的檔案在commit之前，都需要先做add＊**

## Clone repository

```
git clone (remote repository url) (folder name)
```

* (remote repository url): 遠端repository的clone路徑，如：https://github.com/user/XXX.git
* (folder name): 本地資料夾名稱

Example:

```
git clone https://github.com/mygit/firstrepository.git firstRepository
```

## Add commit files

```
git add (file)
```

* (file): 要commit的檔案，要包含副檔名 (Any file, include extension name)

Example:

```
git add README.md
```

若你確定所有修改過的檔案都要加入，可以使用另外一個command一次加入所有修改過的檔案，

```
git add .
```

## Commit Status

```
git status -s
```

查看檔案修改狀態，哪些檔案是add、哪些檔案是modified、哪些檔案被加入此次的commit、...。<br>
這裡只會列出有被修改過的檔案，未做任何修改的檔案不會顯示。

![File status](/images/git_status.png)

* 白字 : 有進行修改的檔案
* 紅字 : 檔案狀態標記，且 **尚未加入** 此次的commit清單內。(M = Modify, ?? = Add)
* 綠字 : 檔案狀態標記，且 **已被加入** 此次的commit清單內。(M = Modify, A = Add)

## Commit

```
git commit
```

執行command之後會跳出 vi編輯器，可以在編輯器上編輯任何commit message。<br>
vi編輯器上會一併顯示這次要commit的資訊，如哪個檔案是add、哪些檔案是modified、...。

vi編輯器的操作方式：(以下鍵盤操作)

| 鍵盤按鍵 | 用途 |
|---------|-----|
| **i** | 開啟編輯模式，開啟之後就可以輸入任意文字進行文字編輯 |
| **Esc** | 離開編輯模式，離開之後就可以輸入指令 |
| **:wq!** | 儲存修改並離開 vi編輯器 |
| **:q!** | 不儲存修改並離開 vi編輯器 |

若是不需要太多commit message，也確切知道哪些檔案會被commit，可以使用快速commit command。

```
git commit -m "(commit message)"
```

* (commit message): 修改紀錄

Example:

```
git commit -m "Add new Logo, modify login flow, ..."
```

## Push

```
git push -u origin master
```

將已經commit的檔案丟到遠端 repository。<br>
Push the committed files to remote repository.
