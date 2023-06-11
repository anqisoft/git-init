# git-init [en](README.md 'en') [繁體](README.zh_tw.md '繁體')

## 描述：

本文档提供关于在 Windows 中使用 git-init 以及与 git-mentoring 的对应关系的信息。

# 给 git-mentoring 的电子邮件：

## 主题：

在 Windows 中使用 git bash 和 git-init 创建的是 master 分支，而新仓库的默认分支是 main。

## 内容：

嗨，

我最近在我的 Windows 10 电脑上下载并安装了最新版本的 Git。然而，当我使用 git-init 命令时，默认创建了 master 分支。在 GitHub 网站上创建新仓库时，默认分支设置为 main。这导致了一个差异，我需要使用"git push origin master:main"来提交更改，而不能直接使用"git push origin main"（无效）或"git push origin master"（会在仓库中创建一个额外的分支）。

因此，我建议当我们使用 git-init 命令时，应该将 main 分支作为默认分支创建，以与仓库保持一致。

最好的问候，

AnQi

2023 年 6 月 10 日

## 附件：git-init.pdf

#git-mentoring 的回复：
嗨 AnQi，

您可以配置 Git 在运行 git init 命令时创建的默认分支。这个配置可以在 Git 安装过程中设置（安装程序提供了一个选项），或者您也可以在安装后使用"git config --global init.defaultBranch <branch-name>"命令进行配置（请参阅文档：git-scm.com/docs/git-config#Documentation/git-config.txt-initdefaultBranch）。通过设置默认分支名称，Git 将在每次创建仓库时都使用该值作为默认分支的名称。

关于自动创建与远程仓库相同默认分支的仓库，Git 在 git init 过程中无法知道您指的是哪个远程仓库。因此，我认为无法自动创建具有相同默认分支的仓库。您需要在运行 git init 之前手动为 init.defaultBranch 配置变量赋值。

希望这些信息有所帮助。如果您有任何其他问题或需要进一步的解释，请随时联系我们。

谢谢！

问候，

[隐藏姓名]（他/他）

# 回复 git-mentoring：

嗨[隐藏姓名]，

我想对您的帮助表示感谢。我现在找到了另一种创建本地项目并提交更改的替代方法，以"python-help"项目为例。以下是我遵循的步骤：

1. 我访问了https://github.com/new页面，并在github.com上创建了一个新仓库。我提供了一个名称（例如"python-help"），编写了一个描述，选择了"添加README文件"选项，选择了一个.gitignore模板，选择了一个许可证，并单击了"创建仓库"按钮。
2. 在我的本地计算机上，我右键单击父目录并选择"Git Bash Here"。
3. 在 Git Bash 窗口中，我使用以下命令克隆了仓库：

```bash
git clone git+ssh://g...@github.com/anqisoft/python-help
```

4. 如果需要，我使用"mv"命令更改了目录名。例如：

```bash
mv python-help help
```

5. 接下来，我使用"cd"命令进入新的目录。例如：

```bash
cd help
```

6. 为了将我的名字和电子邮件添加到.git/config 文件中，我执行了以下命令：

```bash
  echo >> .git/config
  echo [user] >> .git/config
  echo \ \ name = anqisoft >> .git/config
  echo \ \ email = anqi...@gmail.com >> .git/config
```

7. 在使用开发工具完成项目后，我使用以下命令添加文件并推送更改：

```bash
git add .
git commit -m "initial commit"
git push origin main
```

如果您有任何进一步的建议或问题，请告诉我。

最好的问候，

AnQi（他/他）

2023 年 6 月 11 日
