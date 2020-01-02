# **Git学习笔记**

*作者：Luvoy，鸣谢：廖雪峰*
# 写在前面

学习东西时如果追求效率，那么很容易学了就忘，必须时常复习。

```
子曰：温故而知新，可以为师矣。
```

然而复习时看是不行的，容易眼高手低，遂整理问题和答案，并且用跳跃查看以起到遮掩的目的。

# 复习问题
## **开始**

1.  <span id="question_1"></span>简述Git诞生过程？谁因为什么用什么发明的？[查看答案](#answer_1) 

2.  <span id="question_2"></span>集中式和分布式版本控制系统有什么区别呢？ [查看答案](#answer_2)

3.  <span id="question_3"></span>安装完成git后需要设置什么？global参数有什么作用？[查看答案](#answer_3)
   
## **创建版本库**

4.  <span id="question_4"></span>什么是版本库？如何初始化版本库？如何添加文件？[查看答案](#answer_4)
5.  <span id="question_5"></span>如何查看仓库的状态？如何查看文件具体修改了什么内容？[查看答案](#answer_5)
6.  <span id="question_6"></span>如何看到git的日志信息？如何只输出commit id和commit的信息？commit id是用什么计算出来的？[查看答案](#answer_6)

## **版本回退**
7.  <span id="question_7"></span>Git中用什么表示当前版本？上一个版本？往前n个版本？[查看答案](#answer_7)
8.  <span id="question_8"></span>如何把当前版本回退到上一个版本？--hard参数有什么意义？回退的原理是什么？[查看答案](#answer_8)
9.  <span id="question_9"></span>忘记commit id和版本如何回退？未commit但是有修改的其他文件会不会被回退？[查看答案](#answer_9)
10. <span id="question_10"></span>什么是工作区？什么是版本库？add和commit在这些区域上执行了什么操作？[查看答案](#answer_10)
11. <span id="question_11"></span>某文件经历了：修改1->add->修改2->commit，提交的是哪次修改？为什么？[查看答案](#answer_11)
12. <span id="question_12"></span>什么命令可以撤销上一次修改？（让这个文件回到最近一次git commit或git add时的状态？）[查看答案](#answer_12)
13. <span id="question_13"></span>如何删除文件？错删文件怎么办？[查看答案](#answer_13)

## **远程仓库**
14. <span id="question_14"></span>如何在github上创建远程仓库？[查看答案](#answer_14)
15. <span id="question_15"></span>[查看答案](#answer_15)
16. <span id="question_16"></span>[查看答案](#answer_16)
17. <span id="question_17"></span>[查看答案](#answer_17)
18. <span id="question_18"></span>[查看答案](#answer_18)
19. <span id="question_19"></span>[查看答案](#answer_19)
20. <span id="question_20"></span>[查看答案](#answer_20)
21. <span id="question_21"></span>[查看答案](#answer_21)
22. <span id="question_22"></span>[查看答案](#answer_22)
23. <span id="question_23"></span>[查看答案](#answer_23)

# 答案
1.  <span id="answer_1"></span>Git由linux系统之父**Linus**，在管理linux版本时，因为其他版本控制系统太难用或者收费，自己用**C语言两周**写出来的**分布式**版本控制系统。[返回问题](#question_1)
2.  <span id="answer_2"></span>集中式相当于图书馆，任何修改都必须上传到服务器上，版本库也存放在服务器上，必须联网。

    分布式相当于每个人电脑里都有完整的版本库，修改文件只需把修改发送给拥有相同版本库的其他人就可以了。不需要服务器存储，可以有服务器用来交换好传输。[返回问题](#question_2)
3.  <span id="answer_3"></span>
    ```git
    git config --global user.name "Tom"
    git config --global user.email "a@b.com"
    ```
    global参数是将这台计算机上所有Git仓库都用这个配置[返回问题](#question_3)
4.  <span id="answer_4"></span>版本库又叫版本仓库repository，可看作一个目录，目录下的文件被Git管理起来，追踪增删改查记录
   
    * 初始化版本库：
        - 在某一文件夹下输入命令
            ```git
            git init
            ```

    * 向版本库添加文件：
        - 将一个或多个文件放入此文件夹下并输入命令
            ```git
            git add 文件名
            ``` 
        - 将文件提交到仓库
            ```git
            git commit -m "wrote a file"
            ```
        git有两个区域，工作区和暂存区，git add把工作区的修改提交到暂存区，git commit把暂存区的修改保存到本地库，git push把本地库的记录，推送至远程库。[返回问题](#question_4)
5.  <span id="answer_5"></span>使用```git status```命令查看仓库状态，使用```git diff```命令查看文件变化[返回问题](#question_5)
6.  <span id="anwser_6:"></span>使用```git log```命令查看仓库日志，加上```--pretty=oneline```参数可以将每次修改按一行显示。其中第一列是commit id，由SHA1计算得出。[返回问题](#question_6)
7.  <span id="anwser_7"></span>用HEAD表示当前版本，HEAD^表示上一版本，HEAD^表示上上版本，往上100个版本是HEAD~100。[返回问题](#question_7)
8.  <span id="anwser_8"></span>用```git reset --hard 某版本```即可回退到某一版本。此时，回退只是把HEAD的指向修改[返回问题](#question_8)
9.  <span id="anwser_9"></span>用命令```git relog```可以看到历史命令。没有commit 的文件，用reset，也会恢复到之前的版本。[返回问题](#question_9)
10. <span id="anwser_10"></span>文件夹目录是工作区（working directory），而.git文件夹是Git版本库（Repository），版本库包括缓存区（stage）和第一个分支（master），指向master的指针是HEAD。add命令会把文件修改添加到暂存区，commit把暂存区全部提交到当前分支。提交后，工没有对工作区修改，那么工作区就是干净的[返回问题](#question_10)
11. <span id="anwser_11"></span>只会提交第一次修改，因为git必须先把文件添加到暂存区在提交。[返回问题](#question_11)
12. <span id="anwser_12"></span>```git checkout -- file```可以撤销修改，如果文件修改后没有add就撤销，则退回到和版本库一样的状态，如果已经add后修改再撤销，则退回到add时的状态。```git reset```可以将暂存区的修改回退到工作区[返回问题](#question_12)
13. <span id="anwser_13"></span>```git checkout -- file```已经删除了文件，可以```git rm file```确认在仓库中删除并且commit。如果是误删，可以用checkout --file回退，但是这个文件必须add过才行。[返回问题](#question_13)
14. <span id="anwser_14"></span>```ssh-keygen -t rsa -C "email"```创建ssh key，然后在github的个人主页，settings->ssh keys-> add ssh key。注意把公钥里所有的文本都粘贴上去。[返回问题](#question_14)