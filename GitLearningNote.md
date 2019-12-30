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
10. <span id="question_10"></span>[查看答案](#answer_10)
11. <span id="question_11"></span>[查看答案](#answer_11)
12. <span id="question_12"></span>[查看答案](#answer_12)
13. <span id="question_13"></span>[查看答案](#answer_13)


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