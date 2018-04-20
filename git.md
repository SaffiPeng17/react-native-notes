# Git

版本控制系統，遠端空間是使用 GitHub，UI 操作版本可以參考 [Source Tree](https://www.sourcetreeapp.com/)。以下紀錄一些比較常用到的 command。<br>
Record some common git commands here. (Use GitHub)

<br>

## Create repository

可以直接在網頁上操作，或是使用下方 command。<br>
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

    在現在的 folder 建立一個 XXX.git 檔案

* `git remote add origin https://github.com/myGit/newrepository.git`

    增加遠端的 repository

<br>

## Common git flow

1. 增加/修改檔案或程式 (Add/Modified any file or code)
2. 修改檔案或程式進行 commit (Commit the modified)
3. Push 到遠端 repository (Push to remote repository)

**＊記得*每一個*有修改到的檔案在 commit 之前，都需要先做 add＊**

<br>

## Add file in

```
git add (file)
```

* (file): 任意檔案，要包含副檔名 (Any file, include extension name)

Example:

```
git add README.md
```

<br>

## Commit Status

```
git status -s
```

查看檔案修改狀態，哪些檔案是 add、哪些檔案是 modified、哪些檔案被加入此次的 commit。<br>
這邊只會顯示有進行修改的檔案，未做任何修改的檔案不會顯示。

![File status](/images/git_status.png)

* 白字 : 有進行修改的檔案
* 紅字 : 檔案狀態標記，且 **尚未加入** 此次的 commit 清單內。(M = Modify, ?? = Add)
* 綠字 : 檔案狀態標記，且 **已被加入** 此次的 commit 清單內。(M = Modify, A = Add)

<br>

## Commit

```
git commit
```

執行 command 之後會跳出 vi編輯器，可以在編輯器上編輯任何 commit message。<br>
vi編輯器上會一併顯示這次要 commit 的資訊，如哪個檔案是 add、哪些檔案是 modified。

vi 編輯器的操作方式：(以下鍵盤操作)

**i** : 開啟編輯模式。開啟之後就可以輸入任意文字進行文字編輯。
**Esc** : 離開編輯模式。離開之後就可以輸入指令。
**:wq!** : 儲存修改並離開 vi編輯器。
**:q!** : 不儲存修改並離開 vi編輯器。

若是沒有這麼多 commit message 需要輸入，也確切知道哪些檔案會被 commit，可以使用快速 commit command，

```
git commit -m "(Commit message)"
```

* (Commit message): 修改紀錄，如這次增加/修改了什麼 (Commit record, e.g., Add/Removed/Modified something)

Example:

```
git commit -m "Add new Logo, modify login flow, ..."
```

<br>

## Push

```
git push -u origin master
```

將已經 commit 的檔案/程式丟到遠端 repository。<br>
Push the committed file/program to remote repository.
