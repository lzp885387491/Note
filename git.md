### 如何拉取项目

pc端项目地址： git@github.com:bo-ddd/union-b.git

移动端项目地址：git@github.com:bo-ddd/union-h5-vue.git

1. git init  初始化项目

2. git remote add origin 地址  关联线上代码仓库；

3. git pull  拉取线上代码

4. git checkout -b master origin/master  在本地新创建一个master分支，并和线上分支（origin/master）进行关联

### 切换分支

git fetch

git checkout -b develop origin/develop

#### 查看修改

 git branch -vv

#### 查看所有分支

 git branch -aa

git status 查看更改了那些文件

### 提交流程

1.  git add .     添加所有的修改文件；
2.  git commit -m "添加了一个index.html文件"      备注信息
3.  git pull
4.  git push