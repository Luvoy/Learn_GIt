# Git学习笔记与问题复习

*作者：Luvoy，鸣谢：廖雪峰*

## 复习问题
### **开始**

1.  <span id="question_1"></span>简述Git诞生过程？谁因为什么用什么发明的？[查看答案](#answer_1) 

2.  <span id="question_2"></span>集中式和分布式版本控制系统有什么区别呢？ [查看答案](#answer_2)

3.  <span id="question_3"></span>安装完成git后需要设置什么？global参数有什么作用？[查看答案](#answer_3)
   
### **创建版本库**

4.  <span id="question_4"></span>什么是版本库？如何初始化版本库？如何添加文件？[查看答案](#answer_4)
5.  <span id="question_5"></span>
6.  <span id="question_6"></span>
7.  <span id="question_7"></span>
8.  <span id="question_8"></span>
9.  <span id="question_9"></span>
10. <span id="question_10"></span>
11. <span id="question_11"></span>
12. <span id="question_12"></span>
13. <span id="question_13"></span>


## 答案
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
        因为git有两个区域，工作区和暂存区，git add把工作区的修改提交到暂存区
        [返回问题](#question_4)
5.  