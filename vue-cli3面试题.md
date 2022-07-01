### vue3-cli面试题总结2

``` js
1、git 线上出现bug后出现bug如何操作？
基于master分支创建一个热分支，修复完bug之后提交测试，测试完成后，将热分支代码合并到master分支上，项目上线后将master分支合并到dev开发分支中去

# 知识点：线上分支的代码出现重大bug缺陷，需要紧急处理，但是因为dev分支的代码已经进行开发，我们并不能直接在dev分支进行开发，所以我们需要做如下处理
	1、新建一个hot（热修复分支）命名规范：Hot_br20220630
    2、该分支需要从master分支上来取，不能zaidev分支上取，因为dev分支已经在做下一个版本的功能
    // 步骤一盒步骤2的实现为git checkout -b Hot_br20220630 origin/Hot_br20220630
    3、之后我们在Hot_br20220630分支上进行修复bug，修复完交给测试朋友进行测试
    4、测试完毕后需要进行代码合并
    5、将分支切换到master分支，并将Hot_br20220630分支的代码合并到master分支上来
    // 实现流程：git checkout master 切换至master分支
    git merge Hot_br20220630 将Hot_br20220630分支的代码合并到master分支
    6、项目打包  npm run build;
	7、布置服务器（把你master分支的代码放在服务器上）
    8、切换到dev分支，将master代码合并到dev分支
    
    
# 实现步骤
	1、打开GitHub或者gitlab
    2、点击切换分支按钮，输入创建分支提示：create branch :Hot_br20220630 from 'master'
    3、将线上分支同步到本地 git fetch 刷新获取到线上Hot_br20220630分支
    4、新建一个本地的分支并关联：git checkout -b Hot_br20220630 origin/Hot_br20220630
// -b  是branch的缩写 意思是分支
// origin ：虽然叫起源，源头 但是在这里指的是远程，线上（GitHub、gitlab) ;   git checkout 是切换分支； origin/Dev_br20220720 索要关联的分支 


# 知识点：任何分支都是从master分支上分下来的
	1、举例：下一个版本如果是720上线
    2、创建一个dev分支，该分支名为 ： Dev_br20220720
    3、功能开发完毕后提交测试
    4、测试完毕后合到master分支上取
```

![image-20220630104158513](C:\Users\李展鹏\AppData\Roaming\Typora\typora-user-images\image-20220630104158513.png)

git中如果遇到提示可以自动帮你修复冲突的话  输入：  :wq 就可以返回原界面

### 公司中的分支划分？

1、分为 开发分支（dev）和线上分支（master）公司规模较小时的分支划分

// 开发人员开发完代码，直接吧dev分支的代码让测试同学进行测试，测试完成后直接合并到master，然后部署上线

2、开发分支（pre）测试分支（dev）线上分支（master） 非常正规的分支划分

// 开发人员在pre分支进行开发，开发完以后把代码合到dev分支，dev分支测试完毕后，将dev代码统一合并到master分支

3、在公司中你们分支的种类

​	答：1、dev  master

​			2、sit  or  pre   dev   master

4、你们公司中有sit分支吗？（特别重要）or    你们公司中用的是sit还是pre  or   你们的测试环境是sit还是dev？

答：答复1：我们公司没有sit，但是之前的公司有

​	答复2：我们公司规模比较小，只有dev 和master 没有sit

// 这两种答复都对，目的不是看你的公司有没有sit  ，而是看你知不知道sit这个东西

5、在push代码时，如何推送到非关联的分支？

答：git push origin/<分支名>

//为什么会考这道题，是因为有一些公司的开发不知道如何关联分支，他们只能用这种方法去推送，所以这道题他们觉得很重要

知识点：开发中的分支说法？

​	开发分支  sit  、pre

​	测试分支   dev

​	线上分支  master  、prd

// 注：pre代表前  dev是开发  prd  生产，productopn