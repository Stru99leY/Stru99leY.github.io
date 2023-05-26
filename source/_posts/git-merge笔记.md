---
title: git_merge笔记
date: 2023-04-06 20:51:40
category:
   - 随笔
tags:
   - git
---
## gitub问题:master和main分支合并

问题:github创建仓库后默认分支是main，而本地创建的是master

1. 先给本地master改名

   ```git
   git branch -M main
   //-M对分支重命名
   ```

2. 查看所有分支

    ```git
    git branch -a
    * main   
    remotes/origin/main   
    remotes/origin/master  
    ```

3. 删除远程分支master

   ```git
      $ git push origin --delete master 
    To https://github.com/
         - [deleted]         master  
   ```

4. 确认删除情况

   ```git
   $git branch -a
   * main
   remotes/origin/main
   ```

5. 切换当前分支main，也就要保留下来的分支

    ```git
    $ git checkout main 
    Already on 'main' 
    ```

6. 合并分支

    ```git
    $ git merge remotes/origin/main 
    fatal: refusing to merge unrelated histories 
    ```

    说明:拒绝合并，需要忽略这个限制，添加"--allow--unrelated-histories"
7. 提交修改

   ```git
   git push origin main
   ```
