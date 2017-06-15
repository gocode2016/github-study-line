##  my Project
+   init(初始化)
+   repository(仓库)
+   track(开始或者停止跟踪)：`git add `命令来实现对指定文件的跟踪
+   stage(暂存)
+   commit(提交)
+   push(推送)
+   pull(拉取)
##  使用 Git 时文件的生命周期
![git live](https://github.com/Tinywan/github-study/blob/master/image/Figure2-1.png)
##  工作目录
+   作目录下的每一个文件都不外乎这两种状态：
    +   已跟踪 :已跟踪的文件是指那些被纳入了版本控制的文件，在上一次快照中有它们的记录，在工作一段时间后，它们的状态可能处于未修改，已修改或已放入暂存区  
    +   未跟踪 :工作目录中除已跟踪文件以外的所有其它文件都属于未跟踪文件，它们既不存在于上次快照的记录中，也没有放入暂存区。  
##  检查当前文件状态
+   `Untracked files`
    +   未跟踪的文件意味着 Git 在之前的快照（提交）中没有这些文件；Git 不会自动将之纳入跟踪范围，除非你明明白白地告诉它“我需要跟踪该文件”，
+   `Changes to be committed`
    +   这行下面的，就说明是已暂存状态
+   `Changes not staged for commit`
    +   这行下面，说明已跟踪文件的内容发生了变化，但还没有放到暂存区（staged）
    +   要暂存这次更新，需要运行` git add` 命令
    +   ` git add` 命令是个多功能命令
        1.  可以用它开始跟踪新文件
        2.  把已跟踪的文件放到暂存区
        3.  合并时把有冲突的文件标记为已解决状态等
        4.  个命令理解为“添加内容到下一次提交中”而不是“将一个文件添加到项目中”要更加合适
    
##  Git查看、删除、重命名远程分支和tag
+   [Git查看、删除、重命名远程分支和tag](http://zengrong.net/post/1746.htm)
+   查看远程分支
    ```bash 
    $ git branch -a
      master
      remote
      tungway
      v1.52
    * zrong
      remotes/origin/master
      remotes/origin/tungway
      remotes/origin/v1.52
      remotes/origin/zrong
    ```
+   删除远程分支和tag
    +   删除远程分支：`git push origin --delete <branchName>`
    +   删除tag：`git push origin --delete tag <tagname>`
    +   重命名本地分支：`git branch -m devel develop`
+   推送本地分支：`git push origin develop`    
    
##  标签管理
    