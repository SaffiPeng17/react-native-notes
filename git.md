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

| Steps | Command | Description |
|-------|---------|-------------|
| 1 | clone | 將遠端的repository下載至local，只在第一次建立專案時使用 |
| 2 | pull | 將local的專案與遠端repository最新版本做同步 |
| 3 | | 用其他IDE編輯program |
| 4 | add | 將有修改到的檔案加入stage |
| 5 | commit | 將已stage的檔案進行commit |
| 6 | push | 將已commit的檔案同步到遠端repository |

* **add的操作一般稱為stage，目的是標記要進行commit的檔案；之後進行commit時，只會commit有被stage的檔案。**

## Clone repository

```
git clone (remote repository url) (folder name)
```

* **(remote repository url)**

    遠端repository的clone路徑，如：https://github.com/user/XXX.git

* **(folder name)**

    本地資料夾名稱

Example:

```
git clone https://github.com/mygit/firstrepository.git firstRepository
```

## Pull

```
git pull
```

將遠端repository的最新版本同步回local。

## Add (Stage)

```
git add (file)
```

* **(file)**

    要commit的檔案，包含檔名＋副檔名

Example:

```
git add README.md
```

若要一次加入所有修改過的檔案，可以使用，

```
git add .
```

## Commit

```
git commit
```

執行command之後會跳出 vi編輯器，上面會顯示這次要commit的資訊，如哪些檔案做了什麼修改等等，可以直接在commit資訊下方加入任意commit message。

vi編輯器的操作方式：(以下鍵盤操作)

| 鍵盤按鍵 | 用途 |
|---------|-----|
| **i** | 開啟編輯模式，開啟之後就可以輸入任意文字進行文字編輯 |
| **Esc** | 離開編輯模式，離開之後就可以輸入指令 |
| **:wq!** | 儲存修改並離開 vi編輯器 |
| **:q!** | 不儲存修改並離開 vi編輯器 |

<br>
若是不想用 vi編輯器 來編輯commit message，可以使用另外一個command，

```
git commit -m "(commit message)"
```

* **(commit message)**

    修改紀錄

Example:

```
git commit -m "Add new Logo, modify login flow, ..."
```

## Push

```
git push origin master
```

將已經commit的檔案同步到遠端repository。

<br>
——其他command——

## Status

主要用來查詢檔案修改的狀態。

```
git status -s
```

這個command可以查詢檔案狀態，執行command之後會顯示所有修改過的檔案，並且標記檔案修改狀態，如哪些是add、哪些是modified、...。

![File status](/images/git/git_status.png)

* **白字**

    有被修改過的檔案

* **紅字**

    **未** 被stage的檔案狀態。(M = Modify, ?? = Add)

* **綠字**

    **已** 被stage的檔案狀態。(M = Modify, A = Add)

* 若是檔案在stage後又被修改，這時會同時顯示紅/綠兩種檔案狀態。

## Checkout

主要目的是將現在的專案切換到指定版本，要特別注意的是 **執行這個command後，任何沒有進行commit的檔案修改都將被捨棄**。
當然執行這個command時，git system若偵測到有任何未commit的檔案修改，會跳出警示訊息，這時再進行確認也可以。

```
git checkout -- (file)
```

* **(file)**

    要進行checkout的檔案，包含檔名＋副檔名。

Example:

```
git checkout -- README.md
```

## Stash

主要可以把目前所有的檔案修改都放到暫存。如果遇到工作到一半被打斷，而且需要去修改其他issue時，就可以使用stash把修改到一半的部分暫存起來，等目前的issue處理好後，再從stash把之前做到一半的工作搬回來繼續完成。

```
git stash
```

這個command是將目前所有的檔案修改丟到stash。

雖然git system會自動給予stash一個node ID，但當你有好幾個被打斷的工作(好幾個stash)時，你可能需要加入一些資訊來辨別不同的stash，這時可以使用，

```
git stash save "(stash message)"
```

* **(stash message)**

    自己辨識用的stash訊息

當你想把指定的stash搬回專案時就要使用，

```
git stash apply
```

當stash被搬回專案之後，該stash就可以使用下方的command進行刪除，

```
git stash drop
```

當你只有一個stash時，可以直接使用上方的command；但若是你的stash不只一個，就可以使用下方command來指定你想刪除的stash，

```
git stash drop (node id)
```

* **(node id)**

    git system為stash建立的node ID

若是想查詢stash的nodeID可以使用，

```
git stash list
```
