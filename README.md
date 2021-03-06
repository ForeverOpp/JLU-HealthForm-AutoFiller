# 吉林大学健康填报自动填表程序
  这是一个自动定时访问吉林大学健康填报网站并且进行确认及提交的程序。
   
## 声明：
  1. 本程序不应用于任何非吉林大学允许的行为，本程序不会对填报内容做任何修改，仅确认已填好的表格内容并发送。
  2. 使用者应对自己的填报内容进行负责，本程序仅辅助实现填报，对于使用本程序造成的一切后果本人不予负责。  
    
## 使用方法
  1. 在config.ini中的userlist中新建username = passwd字段，其中username为用户名，即去掉@mails.jlu.edu.cn后的邮箱名；
  passwd为密码。
  2. 右键管理员运行win-install.cmd即可开机启动，如果不想开机启动也可以直接运行程序。
  3. 如果需要自定义浏览器，请修改b = webdriver.Chrome()一行，改为Firefox等也可。
  4. 请在 [这里](http://npm.taobao.org/mirrors/chromedriver/) 下载对应浏览器版本的ChromeDriver，放到Python安装目录下（Python目录一般已经加入
  到Path变量中，这里是为了方便，如果需要放到其它目录请将对应目录加入Path变量）或放到安装目录下，自定义目录修改配置文件即可。
    
## 配置文件说明
time: 每天开始填报的时间
diff: 以上时间的浮动范围（分钟）
apikey: apikey
method: bark或者servserchan
title: 推送标题
content: 推送内容
timeout: 默认就行
chromedriver: 路径
  
## 已知问题
  1. 闰年、闰月的时候可能会出问题，就像今年各大软件出现的问题一样。
  2. ~~Windows服务无法启动，但是进程里面有进程，不知道怎么回事（建议注释掉源码内弹窗的代码试一下）。~~
  3. 在某些设备上，更改后的config.ini文件可能无法被识别（我在Windows Server上测试是如此）。
  4. 会因服务器连不上错过填报时间。
  
## 待办事项  
- [x] 自动填表（自动读取已经填好的内容并且保存待下次填写）  
- [x] Linux/macOS开机启动脚本  
- [x] 队列填报  
- [x] 根据上次填报时间确定今日是否填报  
- [x] 上次填报时间记录及通知  
- [x] ~~多线程填报~~