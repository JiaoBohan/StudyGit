Just read the file.

git config
git add filename
git commit -m "message"
git status
git log (--graph)(--pretty=oneline)     // graph 显示分支图     pretty=online 将每个信息显示在一行中
git reflog
git reset filename          // 将该文件从暂存区取出 取消 add
git reset --hard <seq(HEAD)>  // 用 seq = HEAD 时，表示最新的版本，若无 seq，则回到上一次 commit 时的状态
git checkout -- filename    // 丢弃工作区的修改，让该文件回到最近一次 git commit 或 git add 时的状态 可以恢复被删除的已经提交到版本库中的文件(在提交删除前)
git rm filename         //  删除该文件，之后提交即可将其从版本库中删除  从来没有被添加到版本库就被删除的文件，是无法恢复的
git remote add <origin> git@server-name:path/repo-name.git    // 关联远程库     origin 为给远程库指定的名字
git remote -v           // 查看远程库的信息
git remote rm <name>    // 删除远程库（解除本地库与远程库的绑定）
git push <-u> <origin> master    // 向远程库推送最新修改    第一次提交需加 -u
git clone https://github.com/project/repo.git   // 使用 HTTPS 协议克隆 每次推送均需输入口令
git clone git@github.com:project/repo.git   // 使用 SSH 协议克隆
git checkout -b <dev>   // 创建并切换到分支 dev     git switch -c <dev>
git branch <dev>    // 创建分支 dev
git checkout <dev>  // 切换到已有分支 dev       git switch <dev>
git branch          // 查看当前分支
git branch -d <dev> // 删除 dev 分支
git merge (--no-ff -m "<message>") <dev>     // 合并 dev 分支到当前分支
// --no-ff 强制禁用 Fast forward 模式，这样在 merge 时会生成一个新的 commit，这样从分支历史上就可以看出分支信息。
<<<<<<< Updated upstream
git stash
git stash list
git stash pop
git stash apply
git stass drop
=======
git stash       // 储藏当前工作区（已 add 但未 commit）
git stash list  // 显示所储存的工作区
git stash pop   // 恢复工作区并将 stash 内容删除
git stash apply // 恢复工作区
git stass drop  //删除 stash 中的内容
git cherry-pick <seq>
>>>>>>> Stashed changes
