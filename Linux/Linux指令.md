实用指令
==========
* [切换运行级别](#切换运行级别)  
* [帮助指令](#帮助指令)  
* [文件目录](#文件目录类)  
* [重定向(覆盖追加操作)](#重定向)  
* [时间日期](#时间日期命令)  
* [搜索查找](#搜索查找命令)  
* [压缩解压](#压缩和解压)  

切换运行级别
----------
`0:关机` `1:单用户` `2:多用户没有网络` `3:多用户有网络`
`4:系统未使用保留给用户` `5:图像界面` `6:系统重启` 常用3和5，忘记密码时切到1改密码<br>
    
    init 0~5
帮助指令(不如百度）
---------
    man ls                                 //获取帮助信息
    help cd                                //获取shell内置命令帮助信息
文件目录类
-----------
    pwd                                     //当前绝对路径
    ls -al                                  //列表方式显示所有文件和目录包括隐藏的
    cd ~  
    cd                                      //回到家目录
    cd ..                                   //回到上一级目录
    mkdir -p /home/animals/dog              //创建多级目录 
    rmdir /home/animals/dog                 //删除空目录
    rm -rf                                  //删除非空目录 -r递归 -f忽略警告
    rm                                      //删除文件
    tough hello.txt world.txt               //创建多个空文件
    cp hello.txt dest/                      //将文件拷贝到dest
    cp -r source/ dest/                     //将source整个目录所有文件拷贝到dest，同名文件回提示
    \cp -r source/ dest/                    //强制覆盖同名文件且不提示
    mv old.txt new.txt                      //重命名
    mv old.txt /root/                       //将当前目录中old文件移动到根目录中   
 查看文件
 -----------
    cat -n /etc/profile                     //只读方式查看文件内容 -n显示行号
    cat -n /etc/profile | more              //长配合一个管道 more分页浏览
    more                                    //space下翻 enter上翻 q离开 ctrl+f下滚 ctrl+b上滚
    less                                    //适合加载查看大日志，space pageDown pageUp上下翻 q离开
    head /etc/profile                       //查看前10行
    head -n 5 /etc/profile                  //查看前5行
    tail /etc/profile                       //查看后10行
    tail -n 5 /etc/profile                  //查看后5行
    tail -f data.txt                        //实时监控，如有变化立即显示
重定向(覆盖追加操作）
-----------------
    ls -l > new.txt                         //列表内容覆盖写入文件
    ls -l /home/ > /home/info.txt           //home目录列表写入文件中
    ls -l >> new.txt                        //只追加
    cat /etc/profile > new.txt              //覆盖
    echo "hello"                            //输出内容到控制台
    echo $PATH                              //输出环境变量
    history 10                              //显示最近使用过的10个命令
    ！5                                     //执行编号为5的指令
 时间日期命令
 -------------
    data                        //显示当前时间
    data "+%Y-%m-%d %H:%M:%S"   //年-月-日 时：分：秒
    data -s "2020-3-3 23:22:00" //设置系统当前时间
    cal                         //显示本月日历
    cal 2020                    //显示一年的
搜索查找命令
--------------
    find /home -name hello.txt              //搜home目录下（包括子目录）名为hello的文件，
    find /opt -user lwt                     //搜索用户为lwt的所有文件
    find / -size +20M                       //搜整个系统下大于20m的文件
    find / -size -20M                       //小于
    find / -name *.txt                      //搜所有后缀为txt文件
    updatedb                                //第一次使用locate命令前必须先更新数据库
    locate hello.txt                        //快速定位文件路径
    cat hello.txt |grep -n yes              //过滤查找，查找yes所在行显示行号，区分大小写
    cat hello.txt |grep -ni yes             //过滤查找，区分大小写
压缩和解压
-----------
    gzip hello.txt                          //压缩不保留原来文件，压缩成*.gz文件 
    gunzip hello.txt.gz                     //当前目录下解压
    zip -r package.zip /home/               //将home下所有文件压缩成package.zip
    unzip -d /opt/tmp package.zip           //解压到/opt/tmp目录下
    tar -zcvf dest.tar.gz source1.txt source2.txt  //压缩多个文件，打包结尾*.tar.gz文件
    tar -zcvf dest.tar.gz /home/            //压缩整个honme文件
    tar -zxvf dest.tar.gz                   //解压到当前目录
    tar -zxvf dest.tar.gz -C /opt/tmp       //-C指定到目录，tmp必须先存在
    
    
