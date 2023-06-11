# git-init [en](README.en.md 'en') [简体](README.zh_cn.md '简体')

## 描述：

本文檔提供關於在 Windows 中使用 git-init 以及與 git-mentoring 的對應關係的信息。

# 給 git-mentoring 的電子郵件：

## 主題：

在 Windows 中使用 git bash 和 git-init 創建的是 master 分支，而新倉庫的默認分支是 main。

## 內容：

嗨，

我最近在我的 Windows 10 電腦上下載並安裝了最新版本的 Git。然而，當我使用 git-init 命令時，默認創建了 master 分支。在 GitHub 網站上創建新倉庫時，默認分支設置為 main。這導致了一個差異，我需要使用"git push origin master:main"來提交更改，而不能直接使用"git push origin main"（無效）或"git push origin master"（會在倉庫中創建一個額外的分支）。

因此，我建議當我們使用 git-init 命令時，應該將 main 分支作為默認分支創建，以與倉庫保持一致。

最好的問候，

AnQi

2023 年 6 月 10 日

## 附件：git-init.pdf

#git-mentoring 的回复：
嗨 AnQi，

您可以配置 Git 在運行 git init 命令時創建的默認分支。這個配置可以在 Git 安裝過程中設置（安裝程序提供了一個選項），或者您也可以在安裝後使用"git config --global init.defaultBranch <branch-name>"命令進行配置（請參閱文檔：git-scm.com/docs/git-config#Documentation/git-config.txt-initdefaultBranch）。通過設置默認分支名稱，Git 將在每次創建倉庫時都使用該值作為默認分支的名稱。

關於自動創建與遠程倉庫相同默認分支的倉庫，Git 在 git init 過程中無法知道您指的是哪個遠程倉庫。因此，我認為無法自動創建具有相同默認分支的倉庫。您需要在運行 git init 之前手動為 init.defaultBranch 配置變量賦值。

希望這些信息有所幫助。如果您有任何其他問題或需要進一步的解釋，請隨時聯繫我們。

謝謝！

問候，

[隱藏姓名]（他/他）

# 回复 git-mentoring：

嗨[隱藏姓名]，

我想對您的幫助表示感謝。我現在找到了另一種創建本地項目並提交更改的替代方法，以"python-help"項目為例。以下是我遵循的步驟：

1. 我訪問了https://github.com/new頁面，並在github.com上創建了一個新倉庫。我提供了一個名稱（例如"python-help"），編寫了一個描述，選擇了"添加README文件"選項，選擇了一個.gitignore模板，選擇了一個許可證，並單擊了"創建倉庫"按鈕。
2. 在我的本地計算機上，我右鍵單擊父目錄並選擇"Git Bash Here"。
3. 在 Git Bash 窗口中，我使用以下命令克隆了倉庫：

```bash
git clone git+ssh://g...@github.com/anqisoft/python-help
```

4. 如果需要，我使用"mv"命令更改了目錄名。例如：

```bash
mv python-help help
```

5. 接下來，我使用"cd"命令進入新的目錄。例如：

```bash
cd help
```

6. 為了將我的名字和電子郵件添加到.git/config 文件中，我執行了以下命令：

```bash
  echo >> .git/config
  echo [user] >> .git/config
  echo \ \ name = anqisoft >> .git/config
  echo \ \ email = anqi...@gmail.com >> .git/config
```

7. 在使用開發工具完成項目後，我使用以下命令添加文件並推送更改：

```bash
git add .
git commit -m "initial commit"
git push origin main
```

如果您有任何進一步的建議或問題，請告訴我。

最好的問候，

AnQi（他/他）

2023 年 6 月 11 日
