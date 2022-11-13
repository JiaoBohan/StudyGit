Just read the file.

git config
git add filename
git commit -m "message"
git status
git log (--pretty=oneline)
git reflog
git reset filename          // 将该文件从暂存区取出 取消 add
git reset --hard <seq(HEAD)>  // 用 seq = HEAD 时，表示最新的版本，若无 seq，则回到上一次 commit 时的状态
git checkout -- filename    // 丢弃工作区的修改，让该文件回到最近一次 git commit 或 git add 时的状态 可以恢复被删除的已经提交到版本库中的文件(在提交删除前)
git rm filename         //  删除该文件，之后提交即可将其从版本库中删除  从来没有被添加到版本库就被删除的文件，是无法恢复的