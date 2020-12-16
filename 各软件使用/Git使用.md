

#### 设置用户名和邮箱

打开Git Bash

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

#### 创建仓库

进入想要管理的目录下，打开Git Bash，执行

```
git init
```

这时候目标文件夹下会多一个.git的目录。

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214203505003.png" alt="image-20201214203505003" style="zoom: 67%;" />

#### 向仓库中添加文件

1. 使用`git add`命令，告诉git我们把文件添加到仓库缓存区了

   ```
   git add hello.txt
   ```

   ```
   git add .	#提交文件夹下所有文件
   ```

   没有提示说明操作成功

2. 使用`git commit`命令，告诉git我们要把缓存区的所有文件正式提交到仓库

   ```
   git commit -m "添加了hello.txt"
   ```

   <img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214204001717.png" alt="image-20201214204001717" style="zoom:67%;" />

   `1 file changed`：1个文件被改动（我们新添加的hello.txt文件）；`1 insertions`：插入了1行内容（hello.txt有一行内容）。

#### 查看版本修改情况

```
git log
```

显示前两次对文件的修改情况：修改人、修改时间。当前版本号：commit id，这个id用来做版本回退

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214204710107.png" alt="image-20201214204710107" style="zoom:67%;" />

#### 回退版本

回退到上一个版本，~后面的数字是几，就回退几个版本

```
git reset --hard HEAD~1
```

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214205103518.png" alt="image-20201214205103518" style="zoom:67%;" />

使用commit id回退版本，回退到上一个版本

发现刚才回退过的版本又回来了，同样的，对应的文件中的内容也相应改变

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214205338277.png" alt="image-20201214205338277" style="zoom:67%;" />



#### 查看历史命令

```
git reflog
```

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214205547040.png" alt="image-20201214205547040" style="zoom:67%;" />

退出这个命令行后，再进入这个文件夹下同样可以



### Git与GitHub关联

#### 本地文件推送到github

本地文件和远程项目同名，都为PythonCode，远程库的名字是origin

```
git remote add origin git@github.com:SuperYIP/PythonCode.git
或
git remote add origin https://github.com/SuperYIP/matlab.git
```

把本地库的所有内容推送到远程库上

```
git push -u origin master
```

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214213554914.png" alt="image-20201214213554914" style="zoom:67%;" />

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214213621962.png" alt="image-20201214213621962" style="zoom:67%;" />

第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

```
git add 文件名
```

```
git commit -m "备注内容"
```

```
git push origin master
```

#### Git查看远程地址

```
git remote -v
```

<img src="C:\Users\伊海迪\AppData\Roaming\Typora\typora-user-images\image-20201214213723841.png" alt="image-20201214213723841" style="zoom:67%;" />

#### Git删除远程文件

```
git rm hello.txt
git commit -m "删除测试文件"
git push
```

#### Git仓库重命名

GitHub中重命名仓库后，需要在git中做相应修改

```
git remote set-url origin git@github.com:SuperYIP/新仓库名.git
git pull  #这个不知道是不是必须运行
```

#### Git提交文件夹下所有变化

```
git add -A
```

