# git

版本控制的工具，這邊主要是使用 GitHub。以下紀錄一些比較常用到的 command。

Record some common git commands here. (Use GitHub)

## Create repository

可以直接在網頁上操作，或是使用下方 command。

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

指定要操作的是 github 上的哪個 repository

## Common git flow

1. 增加/修改檔案或程式 (Add/Modified any file or code)
2. 修改檔案或程式進行 commit (Commit the modified)
3. Push 到遠端 repository (Push to remote repository)

## Add file in

`git add (file)`

* (file): 任意檔案，要包含副檔名 (Any file, include extension name)

Example:

`git add README.md`

## Commit

`git commit -m "(Commit message)"`

* (Commit message): 修改紀錄，如這次增加/修改了什麼 (Commit record, e.g., Add/Removed/Modified something)

Example:

`git commit -m "Add new Logo, modify login flow, ..."`

## Push

```
git remote add origin https://github.com/myGit/newrepository.git
git push -u origin master
```

先指定遠端的 repository 位址，之後再進行 push。

Specified the remote repository you would like to operate and then push the committed.