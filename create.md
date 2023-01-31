## 创建自己的博客

### 1. 新建仓库

![image-20230131111128076](C:\Users\gxzq\AppData\Roaming\Typora\typora-user-images\image-20230131111128076.png)

### 2. 准备本地git环境

1. 下载安装git

2. 配置用户名和邮箱

   git config --global user.name "你的用户名"
   git config --global user.email "你的邮箱"

3. 生成ssh key

   ssh-keygen -t rsa -C "你的邮箱"

   在"用户/.ssh"文件夹中找到id_rsa并复制其内容

### 4. 连接github

1. 在settings中找到ssh key并新建![image-20230131111529532](C:\Users\gxzq\AppData\Roaming\Typora\typora-user-images\image-20230131111529532.png)

   ![image-20230131111720755](C:\Users\gxzq\AppData\Roaming\Typora\typora-user-images\image-20230131111720755.png)

2. 测试能否连接成功

   ssh -T git@github.com

   ![image-20230131111924273](C:\Users\gxzq\AppData\Roaming\Typora\typora-user-images\image-20230131111924273.png)

   连接成功

3. 复制仓库的ssh地址

4. 运行git remote add origin ssh地址

5. 运行git pull origin master

6. 运行git push -u origin master 



## 连接问题

1. ssh: connect to host github.com port 22: Connection refused

   + 可能是SSH的私钥过期了，需要重新生成再配置到github

   + 可能是使用vpn全局代理导致的

   解决方法：关闭梯子，在用户/.ssh目录下创建config文件并填写：

   ```
   Host github.com
   User 3332343771@qq.com
   Hostname ssh.github.com
   PreferredAuthentications publickey
   IdentityFile ~/.ssh/id_rsa
   Port 443
   ```

   