Just read the file.
git add filename
git commit -m "message"
git status
git log (--pretty=oneline)
git reflog
git reset filename          // 将该文件从暂存区取出 取消 add
git reset --hard <seq(HEAD)>  // 用 seq = HEAD 时，表示最新的版本，若无 seq，则回到上一次 commit 时的状态
git checkout -- filename    // 丢弃工作区的修改，让该文件回到最近一次 git commit 或 git add 时的状态