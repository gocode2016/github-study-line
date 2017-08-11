##  Github的工作原理
+  ![git live](https://github.com/Tinywan/github-study/blob/master/image/git-workflow-release.png)
+  如图所示，这是一张Github的工作原理图，每一种色彩的分别代表着不同的分支。从下往上看：
    +  **蓝色** 表示功能分支，负责开发某一功能的工作流。
    +  **橙色** 表示功能总汇分支，他里面是所有功能的汇总。
    +  **黄色** 表示测试分支，用于产品内测。
    +  **绿色** 表示发布分支，只用于发布产品，对外展示。
    +  **紫色** 表示bug修复分支，它是指已经发布的产品发现有bug时进行修复的分支。
##  使用 Git 时文件的生命周期
+  ![git live](https://github.com/Tinywan/github-study/blob/master/image/Figure2-1.png)
+   init(初始化)
+   repository(仓库)
+   track(开始或者停止跟踪)：`git add `命令来实现对指定文件的跟踪
+   stage(暂存)
+   commit(提交)
+   push(推送)
+   pull(拉取)
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
    +   重命名本地分支：`git branch -m devel develop`
+   推送本地分支：`git push origin develop`    
+   tag 管理
    +   把本地tag推送到远程
        +   推送单个tag到远程 
            +   命令格式为：`git push origin [tagname]`
            +   `git push origin v1.0` 将本地v1.0的tag推送到远端服务器
        +   推送所有tag到远程 
            +   命令格式为：`git push [origin] --tags`
            +   `git push --tags` 或者`git push origin --tags`
    +   删除远程tag：`git push origin --delete tag <tagname>` 
+    [合并远程分支](http://www.tuicool.com/articles/JzAv6z)          
##  三种合并方式及特点
+   ![git live](https://github.com/Tinywan/github-study/blob/master/image/merge_method.png)    
+   合并分支的三种方式，分别是 `Create a merge commit`，`Squash and merge` 和 `Rebase and merge`
+   方式一：`Create a merge commit.`
    +   ![git live](https://github.com/Tinywan/github-study/blob/master/image/Create_merge_commit.jpg)
    +   它是最完整的一种合并方式。这种方式合并时不仅保留了所有的提交版本，还保留了所有的修改轨迹
+   方式二：`Squash and merge.`,如图所示，这种方式是最不完整的合并方式，既不保留历史版本，也不保留修改轨迹。
    +   ![git live](https://github.com/Tinywan/github-study/blob/master/image/Squash_and_merge.jpg)
    +   这种方式是最不完整的合并方式，既不保留历史版本，也不保留修改轨迹。这种方式的好处是对于纯文字编辑者在修改错别字、病句等非关键性语句时，为简洁方便，推送时可以直接忽略版本和轨迹。
+   方式三：`Rebase and merge`.
    +   ![git live](https://github.com/Tinywan/github-study/blob/master/image/Rebase_and_merge.jpg)
    +   这种方式是前两者的中间值，它保留了提交版本，却不保留各版本的修改轨迹
+   至于到底选择哪种方式，这就要看你所做的事情对历史版本和修改轨迹的需求啦~    
+   fork的对象是仓库的全部内容，而 pull resquest的对象是各分支    
