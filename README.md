# FunSports-web
----------
## 1. 项目背景
本系统主要定向为运动软件：主要包括跑步，骑行等运动方式的记录，并对运动记录进行存储和分析，根据个人的信息状况，获得个人的运动结果，让用户对自己的运动记录产生反馈，以此制定和改变训练任务。分为两个部分：包括App记录数据和网页管理浏览数据。
本项目包含的是个人数据管理的网页前端。
## 2. 定义
	下面是在项目中的常用缩写语与术语的定义与解释。
1.xx运动软件系统：由两部分组成（包括基于Android的App和基于web的数据管理系统）的本系统。<br /> 
2．	训练任务：用户通过手机App建立的训练计划。<br /> 
    例如：<br /> 
    ①用户建立为期一个月的训练任务，通过对每天的运动进行记录，获得训练任务的进度，以此来指导训练任务的改变和完成。<br /> 
    ②用户建立固定里程的训练任务，通过对每次的运动进行记录，获得训练任务的进度，来指导训练任务的改变和完成。<br /> 
3．运动：用户的一次有效(大于30s且大于1公里)运动。<br /> 
4．运动记录：用户的一次运动的完整记录，可包括：运动时间，运动路线轨迹，运动起点和终点，运动平均速度等信息。<br /> 
## 3. 软件环境
操作系统：Ubuntu 14.04<br /> 
数据库系统：MySQL 5.5<br /> 
Web：Webstorm(HTML+CSS+JAVASCRIPT)<br /> 
Server：PHP<br /> 
## 4.  数据需求
4.1	数据描述:本系统的数据由Baidu地图提供.<br /> 
4.2	数据库设计
实体-联系模型：<br /> 
用户（用户ID，邮箱，姓名，密码，头像，地址，体重，身高，生日，性别，运动记录数）<br /> 
管理员（管理员ID，密码）<br /> 
运动记录（运动记录编号，开始时间，结束时间，持续时间，运动距离，运动方式，运动路线编号）<br /> 
单用户运动记录（用户ID，运动记录编号）<br /> 
运动线路（运动线路编号，开始点经度，开始点纬度，结束点经度，结束点纬度，线路点个数）<br /> 
运动线路点（运动线路编号，点编号，经度，纬度）<br /> 
训练任务（训练任务编号，任务类型名，目标类型，目标值，开始时间，规定结束时间）<br /> 
单用户训练任务（用户ID，训练任务编号）<br /> 
训练任务进度（训练任务编号，记录时间，当前完成目标值，结束类型，结束时间）<br /> 
## 5. 安装
    git clone https://github.com/heismelody/admin-frontend.git
安装Apache后，配置Apache完毕，将文件复制入

    /var/www/html/
安装Mysql后，配置Mysql完毕，修改下列文件中的用户登录信息，执行sql创建新用户后即可使用。
    
    /php/mysqlcon.php
## 6. 项目文件结构
    /vendors        项目使用库文件
    /site           项目主页
    /production     后台管理网页
        /css            css文件
        /images         图片资源
        /js             js文件
        /php            php文件，实际后台处理文件，响应前端数据
            /mysqlcon.php         MySqlConn类，用来表示数据库连接，使用Singleton模式
            /mysqlquery.php       封装了所有使用的sql查询的方法
        /sql            创建数据库使用的sql语句和测试数据
        /index.html     登录后个人主页
        /login.html     登录界面
        /register.html  注册界面
        /file.html      用户训练任务日历
        /map.html       用户运动路线显示于地图
        /tables.html    用户个人信息表
        /table_record.html  用户运动记录表
        /settings.html  用户个人信息设置




