# Git指令参考手册

## 1. 基础入门 (Getting Started)

用于初始化新项目或获取已有项目。

- **初始化本地仓库**：`git init` 
  - *解释：在当前目录下创建一个新的 Git 仓库控制文件（.git 文件夹）。*
- **克隆现有仓库**：`git clone <url>` 
  - *解释：从远程服务器（如 GitHub）完整下载一个项目到本地。*



## 2. 准备提交 (Prepare to Commit)

在正式保存更改前，需要先将文件放入“暂存区”。

- **添加指定文件的更改**：`git add <file>` 
- **添加所有更改（包括未跟踪文件）**：`git add .`（注：原文为 `git add`） 
- **交互式选择部分代码暂存**：`git add -p` 
- **查看当前状态**：`git status` 
  - *解释：查看哪些文件被修改了、哪些已经放入暂存区。*
- **取消暂存某个文件**：`git reset <file>` 
- **取消暂存所有文件**：`git reset` 
- **文件重命名或移动**：`git mv <old> <new>` 
- **删除文件**：`git rm <file>` 
- **从 Git 中移除文件（但保留本地文件）**：`git rm --cached <file>`（注：原文为 `git rmcached`） 



## 3. 提交更改 (Make Commits)

将暂存区的更改永久保存到历史记录中。

- **创建提交并打开编辑器填写说明**：`git commit` 
- **直接在命令行填写提交说明**：`git commit -m 'message'` 
- **跳过暂存区，直接提交所有已跟踪文件的修改**：`git commit -am 'message'` 
- **修改上一次提交**：`git commit --amend`（注：原文为 `git commit-amend`） 
  - *解释：如果你发现刚提交的消息写错了，或者漏掉了一个文件，可以用这个命令修复。*



## 4. 分支操作 (Move Between Branches)

分支用于在不影响主代码的情况下开发新功能。

- **切换分支**：`git switch <name>` 或 `git checkout <name>` 
- **创建并切换到新分支**：`git switch -c <name>` 或 `git checkout -b <name>` 
- **列出所有分支**：`git branch` 
- **按最后提交时间排序查看分支**：`git branch --sort=-committerdate`（注：原文为 `git branch sort-committerdate`） 
- **删除分支**：`git branch -d <name>` 
- **强制删除未合并的分支**：`git branch -D <name>` 



## 5. 合并与集成 (Combine Diverged Branches)

将不同分支的劳动成果合并在一起。

- **普通合并 (Merge)**：`git merge <branch>` 
  - *解释：将指定分支合并到当前分支。*
- **变基合并 (Rebase)**：`git rebase <branch>` 
  - *解释：将当前分支的更改“移”到目标分支的最前端，使提交历史呈线性。*
- **变基压缩提交**：`git rebase -i HEAD~n`（注：原文为 `git rebase -1 HEAD-6`） 
  - *解释：可以将过去的多个提交合并为一个，让历史更整洁。*
- **拣选提交**：`git cherry-pick <commit>` 
  - *解释：只把特定的某次提交应用到当前分支，而不是合并整个分支。*



## 6. 远程同步 (Push & Pull)

与云端（如 GitHub）进行数据交换。

- **推送分支到远程**：`git push origin <branch>` 
- **推送新分支并建立跟踪关系**：`git push -u origin <name>` 
- **拉取并合并远程更改**：`git pull` 
- **拉取远程更改但不自动合并**：`git fetch origin <branch>` 
- **强制推送（带保护）**：`git push --force-with-lease`（注：原文为 `git push-force-with-lease`） 



## 7. 撤销与修复 (Discard & Undo)

当事情搞砸时，这些是你的救命稻草。

- **放弃对单个文件的未暂存修改**：`git restore <file>` 
- **放弃所有未提交的修改（慎用！）**：`git reset --hard`（注：原文为 `git reset-hard`） 
- **“存”起当前工作进度**：`git stash` 
  - *解释：暂时隐藏当前的修改，让工作区变干净，方便去处理紧急 bug。*
- **回退到上一个提交（保留本地修改）**：`git reset HEAD~1`（注：原文为 `git reset HEADA`） 
- **查看操作日志以找回丢失的提交**：`git reflog` 



## 8. 查看历史与对比 (Code Archaeology & Diff)

- **查看提交日志**：`git log` 
- **图形化显示历史**：`git log --graph --oneline`（注：原文为 `git log-graph`） 
- **查看某文件的修改历史**：`git log <file>` 
- **查看谁修改了文件的每一行**：`git blame <file>` 
- **查看已暂存的差异**：`git diff --staged` 



## 9. 配置 (Configuration)

- **设置用户名**：`git config user.name 'Your Name'` 
- **设置全局配置**：`git config --global` 
- **添加快捷命令别名**：`git config alias.st status` 
  - *解释：之后你可以只输入 `git st` 来代替 `git status`。*



## 10.重要文件 

- `.gitignore`: 告诉 Git 哪些文件不需要版本控制（如日志、缓存、编译产物）。
- `.git/config`: 存放该项目的本地配置信息。
- `~/.gitconfig`: 存放你电脑上所有 Git 项目的全局配置信息。