# report.GitHub.io

信息探测

1、⽤arp探测⼯具	扫描192.168.22.0段





2、masscan扫描端⼝





3、使⽤nmap进⾏端⼝信息探测

 
 

后期IP发⽣变化，第⼀层靶机IP更改为192.168.22.129。
第⼀层WEB渗透
1、访问38080⻚⾯，spingboot组件查看⻚⾯与图标确认是spingboot组件


2、扫描⽬录看有没有Spring未授权访问漏洞，扫描到hello路径，访问提示Request method 'GET' not supported，使⽤post传参
 
 


3、测试是否存在log4j2漏洞，使⽤dnslog测试，确认存在CVE-2021-44228漏洞

 
 




4、利⽤jndi注⼊⼯具来实现，在kali中开启rmi服务和构造反弹shell的恶意类


 
5、nc开启监听





6、使⽤hackbar发送⼯具⽣成的rmi请求，挨个进⾏尝试




7、成功反弹shell


8、查看⽂件，发现存在.dockerenv，判断当前为docker内
 
 

9、想远程下载监测脚本，发现没有curl、wget、scp、vi、vim等命令10、找寻⽂件，在root⽬录下发现flag.txt，得到貌似账号密码
 

11、ssh连接，成功登陆并获得root权限，发现内⽹IP10.0.1.6
 
 


第⼆层 内⽹渗透
1、使⽤linux脚本进⾏主机探测



2、使⽤kali⽣成msf⻢
 
 


3、打开msf进⾏监听

 
4、将msf⻢上传到第⼀层靶机，并运⾏，成功监听到shell








5、内⽹路由添加

 
 

6、开启socks代理

 
 

7、在/etc/proxychains4.conf添加代理


8、使⽤nmap进⾏端⼝扫描，开启445端⼝，测试是否存在永恒之蓝漏洞

 
 

9、使⽤代理启动msf



10、使⽤ms17010模块测试，存在永恒之蓝漏洞
 
 


11、使⽤ms17010⾃动化攻击模块，因为挂代理问题，总是⽆法正常得到shell


 

12、可根据http://www.bw08.top/archives/duoceng进⾏操作，这⾥不赘述了

 
13、拿到win7权限后使⽤mimikatz，得到域账号root/Red12345


14、在桌⾯找到第⼆个flag


15、	定位域控
 
 

16、


17、通过ping定位到域控地址


18、添加路由
 
 

19、 得知域⽤户，使⽤CVE-2021-42287直接到域控，exp链接，⽬前只能在kali上反弹到
shell
 
 

20、得到最终flag

