# Git学习

## 配置

~~~
$git config --global user.name "ligiggy"
$git config --global user.email "ligiggy1234@gmail.com"
~~~



## 基础操作

* 查询git状态

  ```
  git status
  ```

* 查询对应文件修改

  ```
  git diff readme.txt
  ```

* 放置到暂存区

  ~~~
  git add readme.txt
  ~~~

* 提交到版本库

  ~~~
  git commit -m "add readme.txt"
  ~~~

* 查询历史记录

  ~~~
  git log
  ~~~

  注意：按Q退出查询历史记录状态

* 查询每一次命令

  ~~~
  git reflog
  ~~~

* 回退

  ~~~
  git reser --hard HEAD^
  ~~~

  注意：HEAD^表示回到前一个版本，HEAD^^表示回到前两个版本，HEAD~100表示回到版本100

  其他回退方法

  ~~~
  git reset --hard 1094a
  ~~~

  1094a表示对应版本id

* 读取当前文本内容

  ~~~
  cat readme.txt
  ~~~

* 撤销修改

  ~~~
  git checkout -- readme.txt
  ~~~

* 删除文件管理器中文件

  ~~~
  rm readme.txt
  ~~~

* 删除版本库中文件

  ~~~
  git rm readme.txt
  ~~~



## 远程库操作

* 添加远程库

  ~~~
  git remote add origin https://github.com/ligiggy/learngit.git
  ~~~

* push到远程库

  ~~~
  git push -u origin master
  ~~~

* 远程与本地库不匹配需要merge

  ~~~
  git pull --rebase origin master
  ~~~



## 分支操作

* 创建分支

  ~~~
  git checkout -b branch1
  ~~~

  等同于如下操作

  ~~~
  git branch branch1
  git checkout branch1
  ~~~

* 查看当前分支

  ~~~
  git branch
  ~~~

* 切换当前“分支”

  ~~~
  git checkout master
  ~~~

* 合并分支

  ~~~
  git merge branch1
  ~~~

* 删除分支

  ~~~
  git branch -d branch1
  ~~~

* 查看分支合并情况

  ~~~
  git log --graph --pretty=oneline --abbrev-commit
  ~~~

  注意：merge分支存在冲突，需要解决冲突后重新add，commit。