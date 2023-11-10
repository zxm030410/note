

# git 上传仓库

```
git config –global

cd ~/.ssh 检查是否生成密钥  ls 如果有两个密钥，则密钥已经生成，id_rsa.pub就是公钥  也可以打开我的电脑C:\Users\Y\ .ssh 里面找到

没有生成，那么通过$ ssh-keygen -t rsa -C "email" 


git init //把这个目录变成Git可以管理的仓库

git add README.md //文件添加到仓库

git add . //不但可以跟单一文件，还可以跟通配符，更可以跟目录。一个点就把当前目录下所有未追踪的文件全部add了 

git commit -m "first commit" //把文件提交到仓库

git remote add origin git@github.com:wangjiax9/practice.git //关联远程仓库

git push -u origin master //把本地库的所有内容推送到远程库上
```

![image-20231110101501221](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20231110101501221.png)





![image-20231110101518172](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20231110101518172.png)





![image-20231110101528778](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20231110101528778.png)



与GitHub仓库关联：

![image-20231110101538949](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20231110101538949.png)



![image-20231110101558485](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20231110101558485.png)

