1、用.sh结尾的文件
2、#！代表文件使用哪种语言编译
####shell文件

    系统级别
    /etc/profile
    /etc/bashrc

    用户级别
    ~/.bash_profile
    ~/.bashrc
    ~/.bash_logout
    ~/.bash_history
3、login shell   
    
    eq:
    - su -    会使用到以下文件
        - /etc/profile
        - /etc/bashrc
        - ~/.bash_profile
        - ~/.bashrc
4、nologin shell 

     eq:
    - su -    会使用到以下文件
        - /etc/bashrc
        - ~/.bashrc
5、退出时使用：
    
    ~/.bash_logout
    ~/.bash_history
##
####设置每天运行

定时任务
    
    永久执行
    crontab -e
    * * * * *(分 时 日 月 周)

    一次性执行
    at 时间
    at> 执行的事件
    at>Ctrl+D
    
#循环
###if

    if() ;then

    elif[]

    elif[]

    esle

    fi
###for

    For 条件

    do
    语句1
    done

```sh
#!/bin/bash

For((i=1;i<=100;i++))
do
    j=$(($i+$j))
done

echo $j  #输出5050
```

###while
```sh
while 条件
do 
    执行语句
done < /etc/hosts
```

### Case选择语句

```sh
case $1 in

    条件1)
        执行语句
    ;;
    条件2)
        执行语句
    ;;
esac
```
### select选择语句
```sh
PS3 = "选择你所需要的"
select i in "apache" "mysql" "php"

do
    case $1 in 

        apache)
            echo "apache 安装"
        ;;
        mysql)
            echo "mysql安装"
        ;;
        php)
            echo "php安装"
        ;;
    esac

done

```
###逻辑运算符

    !  反义
    -f 判断文件是否存在  if[ -f filename ]
    -d 判断目录是否存在  if[ -f filename ]
    -eq 等于   用于整型比较
    -ne 不等于 
    -lt 小于
    -gt 大于
    -le 小于等于
    -ge 大于等于
    -a   and
    -o   or
    -z 空字符串

###数组

    1.定义 
    A = (1 2 3 4 5 6 7)
    2.查看
    $(A[@]) 全部
    $(A[下标]) 查看一个
    $(#A[@])  数组个数
    $(A[@]/被替换者/替换者)
    unset A[下标]

###sed 

    sed -i 's/被修改者/修改内容/g' 修改文件
    不加i是预修改 加i是插入修改