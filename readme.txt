本地仓库：
 1.安装git 

    检测是否安装git：git --version

    debian系列安装命令：sudo apt-get install git 

    windows系列：一键安装msysgit

2.创建用户

    git config --global user.name "name"

    git config --global user.email "email@xx.xxx"

3.创建并初始化一个空仓库

    mkdir warehouse_name   //新建文件夹作为仓库

    cd warehouse_name      //进入文件夹

    git init               //初始化为仓库，自动生成.git

4.提交文件到仓库

    git add file1 file2 ...  //将文件放入缓冲区

    git commit -m "提示信息"  //将缓冲区的文件全部提交到仓库，-m后加提示信

息

    git status               //查看缓冲区状态

    git diff                 //查看更改的内容

5.版本回退

    git log 或 git log --pretty=oneline  //查看历史版本

    git reset --hard HEAD^       //相对于当前版本的回退，其中HEAD表示当前>版本,HEAD^表示上一版本，HEAD^^表示上上版本，以此类推

    git reset --hard commit_id    //指定commit_id的版本回退，commit_id为文件hash值，可只写几位

    git reflog                   //显示历史输入命令

6.小结

    刚初始化产生.git文件夹实质是版本库

    add就是把工作区的文件添加到版本库中的缓存区（stage），commit就是将缓存

区（stage）中的文件放进master区中并清空缓存区（stage） 

7.撤销操作和删除操作

    git checkout -- filename    //若缓存区有文件，则撤销到缓存区文件，若没

有，则回到当前版本库HEAD相同状态，若已经提交版本库，则参考版本回退

    git reset HEAD filename     //把缓存区的修改撤销掉，重新放回工作区

    git rm & git commit         //删除版本库里的文件并更新