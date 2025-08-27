# 域名  
dns:将域名与ip地址转换（解析）
dns服务器将ip与域名绑定
本地HOSTS与dns关系：本地hosts文件可改重新定向ip:改ip为其他绑定域名；没有才连网络dns服务器；
暗改网站指向（钓鱼工具）
cdn:缓存节点（多服务器节点；相同网站）
（重要数据不在节点上）
dns服务器为全球公有
dns攻击：对dns服务器攻击让其转向网站错误；
针对其地区dns服务器
脚本语言：针对web
asp php aspx jsp javaweb pl py eqi
常见：php javaweb
以上为网站脚本框架，可用于破解
后门：攻击者留的二次入侵webshell；服务器：木马；
（通道）
玩法：通过后门操作控制你；
免杀：防止后门被检测；
web组成：网站源码：脚本类型，应用方向(干什么)
操作系统：win/linux
中间件：平台搭建：apache iis tomcat nginx
数据库：access MySQL Oracle sybase db2 postsql

# 查找多站点：
  1.搜索引擎：直接搜；
  2.批量爆破：layer.exe,域名前加东西去尝试；
  3.域名查询；直接去域名注册网站找注册了的；a记录，mx记录；

# dns解析修改

# burpsuite:
改联网的IP到电脑本机IP，端口；在proxy中监控
针对web模板的app

# web安全
## 第一题：
f12获取注释源代码
## 第二题：请用GET方式提交一个名为a,值为1的变量，“？”即为get方式
        execute为发送1.直接用hackerbar
        2.curl "网址" -d "b=2",在cmd中
## 第三题：X老师上课讲了Robots协议，小宁同学却上课打了瞌睡，赶紧来教教小宁Robots协议是什么吧。
        robots协议：网址/robots.txt
        文件语法：
        #注释
        *匹配任意字符
        /目录
        User-agent爬虫名字
        Disallow限制爬取的页面
        Disallow:/禁止爬取任何页面
        查看源代码遇到：Content unavailable. Resource was not cached，f12->网络->停用缓存->刷新
## 第四题：X老师忘记删除备份文件，他派小宁同学去把备份文件找出来,一起来帮小宁同学吧！  
        扫描路径：kali：dirsearch -u url -e php
        ctrlC暂停
## 第五题：X老师告诉小宁他在cookie里放了些东西，小宁疑惑地想：‘这是夹心饼干的意思吗？’
        应用->cookie
        转到网址后->网络->找到response
## 第六题：X老师今天上课讲了前端知识，然后给了大家一个不能按的按钮，小宁惊奇地发现这个按钮按不下去，到底怎么才能按下去呢？
        直接在元素中将disabled改enabled
## 第七题：小宁发现了一个网页，但却一直输不对密码。(Flag格式为 Cyberpeace{xxxxxxxxx} )
        编程中的\x 在编程语言（如Python、C++）中，
        \x是一个转义字符，用于表示十六进制数。例如，"\x41"表示ASCII码为41（十六进制）的字符，即字母A。
        用python转码
## 第八题：小宁听说php是最好的语言,于是她简单学习之后写了几行php代码。
        用get方式拿到a的flag；
        接着用？b=2222+%20绕开is_numeric()检查b为数值拿到b;
## 第九题：小宁写了一个登陆验证页面，随手就设了一个密码。
        字典爆破；先检索，再加入playload，接着跑字典，点长度升降序找出flag;
## 第十题：baby_web:
      显示1.php,用hackerbar重定向index.php，得到网络->index.php的response，拿到flag
## 第11题：Training-WWW-Robots
        直接robots.txt，找到/fl0g.php,即得flag
## 第12题：X老师告诉小宁其实xff（HTTP X-Forwarded-For和referer是可以伪造的。
        考察伪造请求头，HEADER，直接在hackerbar改；
        X-Forwarded-For 是一个 HTTP 扩展头部。HTTP/1.1（RFC 2616）协议并没有对它的定义，
        它最开始是由 Squid 这个缓存代理软件引入，用来表示 HTTP 请求端真实 IP。
        Referer 请求头包含了当前请求页面的来源页面的地址，即表示当前页面是通过此来源页面里的链接进入的。
        服务端一般使用 Referer 请求头识别访问来源，
## 第13题：小宁写了个ping功能,但没有写waf,X老师告诉她这是非常危险的，你知道为什么吗
        ping （Packet Internet Groper），中文名称因特网包探索器，是一种计算机网络管理应用，
        该程序通常被用于确认因特网上的一台主机是否可达 [1]。Ping是工作在 TCP/IP网络体系结构中应用层的一个服务命令， 
        用linux相关知识：1.ping 127.0.0.1 连接到本机；
        2.Linux可同时执行两个指令，（两个都执行：a;b（两个中执行后一个（管道用法（a|b
        基本语法

        find [路径] [匹配条件] [动作]
        路径：指定查找的目录路径，默认为当前目录。
        匹配条件：用于过滤文件，例如按名称、类型、大小等。
        动作：对匹配的文件执行操作，如删除、复制等。
        find / -name "flag*"
        cat /(抓包)
## 第14题：gift_F12,来自NSSCTF，认真读代码即可，前缀为nssctf
## 第15题：baby.http；
         a[]=0&b1[]=1&b2[]=2&c1=QNKCDZO&c2=s878926199a
         preg_match绕过用数组，a[];
         要求md5值相等：
         QNKCDZO（0e830400451993494058024219903391
        s878926199a（0e545993274517709034328855841020
        s155964671a（0e342768416822451524974117254469
        s214587387a（0e848240448830537924465865611904
        s214587387a（0e848240448830537924465865611904
        s878926199a（0e545993274517709034328855841020
        任选两个，即得flag
        通过0e开头骗服务器
## 第16题：ez_ez_php，
直接flag.php，发现flag is in ‘flag’,直接进/flag,拿下
        [09:34:26] 200 -   45B  - /flag                                             
        [09:34:26] 200 -  102B  - /flag.php      
        kali扫一下
## 第17题：Do_you_know_http;
        Please use 'WLLM' browser!，注意看返回的./php
        改useragent与xff
## 第18题：webftp:
先爆破出密码，接着扫kali,在phpxxx.php,进去翻environment
## 第19题：jicao
        正常传参，json格式：json={"x":"wllm"}
        对应：($id=="wllmNB"&&$json['x']=="wllm")
## 第20题： unserialize3:
编写php,new出相关参数，因_wakeup()如果是传参数大于实际便可绕过；
        则输入2即可；
## no.21:PHP2
        有index.phps;查看php源代码的文件；
        urldecode：将输入转为url格式
        使用bp中的编码工具加密admin数据(两次加密)
        最后简单get
## no.22:ics-06；
云平台报表中心收集了设备管理基础服务的数据，但是数据被删除了，只有一处留下了入侵者的痕迹。
        找到特殊网页，改id;用bp爆破后id=2333出flag
## no.23:inget
        sql注入，/?id='or'1=1
        得到flag，但不对，放弃

