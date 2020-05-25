# Git学习

## 配置

* 基础配置

  ~~~
  $git config --global user.name "ligiggy"
  $git config --global user.email "ligiggy1234@gmail.com"
  ~~~

* 创建本地库

  ~~~
  cd f:learngit
  ~~~

* 初始化本地库

  ~~~
  git init
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

* 删除远程库

  ~~~
  git remote rm origin
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



## 标签管理

* 创建一个新标签

  ~~~
  git tag V1.0
  ~~~

* 对历史提交建立标签

  ~~~
  git tag v0.9 f52c64
  ~~~

* 查看标签

  ~~~
  git tag
  ~~~

  注意：标签是按照字母顺序显示的，不是按照时间顺序显示的

* 显示标签信息

  ~~~
  git show V1.0
  ~~~

* 创建带说明的标签

  -a 指定标签名，-m指定说明文字

  ~~~
  git tag -a v1.0 -m "version 1.0 Release" 1094db
  ~~~

* 删除标签

  ~~~
  git tag -d v1.0
  ~~~

* 推送标签到远程

  ~~~
  git push origin v1.0
  ~~~

* 一次推送所有的标签

  ~~~
  git push origin --tags
  ~~~

* 远程删除标签

  ~~~
  git tag -d v1.0
  git push origin :refs/tags/v1.0
  ~~~

  注意：如果上传到远程报错，基本上是网络的问题。