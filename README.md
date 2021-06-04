# Assets View

------

Assets View 资产发现、网络拓扑管理系统采用PHP+MYSQL开发，资产扫描部分采用C语言基于<em>SNMP.</em>协议以及nmap实现网络资产拓扑发现, 可对网络设备资产进行扫描、发现、管理，并对设备开发端口、服务、漏洞信息(后续会添加漏洞扫描功能)进行管理,采用Echarts对资产进行可视化展示，并对网络拓扑进行可视化展示、操作！

> * Codeigniter、nmap
> * PHP、Mysql、C
> * Bootstrap+jquery+Echart

<img src="https://i.loli.net/2021/06/04/flIBgbiWHmz4EAn.png" alt="Assets View Dashboard" style="zoom:150%;" />

## 环境搭建

1. XAMPP下载

    我们使用PHP服务器组件XAMPP 5.6.40(就是开发环境的集成,减少配置)

    链接:[XAMPP](https://sourceforge.net/projects/xampp/files/XAMPP%20Linux/5.6.40/)

2. 安装和启动XAMPP

    ```bash
    # 添加执行权限
    sudo chmod +x xampp-linux-x64-5.6.40-1-installer.run
    # 安装xampp,完成后自动启动
    sudo ./xampp-linux-x64-5.6.40-1-installer.run
    # 安装目录为lampp
    cd lampp
    # 关闭后,再次启动,命令行方式
    sudo ./xampp
    # 图形化方式
    sudo ./manager-linux-x64.run
    ```

    安装过程一路next即可

3. 启动apache 和 MySql 服务

    浏览器访问`http://localhost:80`,出现正常界面,说明安装成功

## 项目部署

1. 进入部署目录

    我的xampp安装在`/opt/lampp`

    ```bash
    # htdocs/ 即为项目部署目录,只要将项目整个复制进去,即可完成部署
    cd /opt/lampp/htdocs
    # 导入项目
    sudo git clone https://github.com.cnpmjs.org/tiaotiaopig/AssetsView.git
    ```

2. 导入数据

    使用MySQL管理工具或者命令行方式运行sql脚本

    > username=root
    >
    > password='' # 密码为空
    >
    > 连接上后,创建数据库**assets_scan**,编码**utf8**
    >
    > 选择**assets_scan**数据库,执行sql脚本
    >
    > 位于**AssetsView/data/db/**目录下

3. 运行项目

    在浏览器输入:[AssetsView](http://localhost/AssetsView),即可看到项目运行

    用户名: assets    密码: 1q2w3e

    


### 关于作者

* Cryin'   https://cryin.github.io/
* Hardy    https://hardyguo.github.io/

------
### Project Site
Home Page:https://github.com/Cryin/AssetsView

------
## 使用帮助

Assets View资产发现、网络拓扑管理系统共包含两个功能模块，如下:

- [x] 资产管理、网络拓扑可视化展示、操作.
- [x] 设备资产、网络拓扑发现.
- [ ] 资产搜索
- [ ] 手动增加资产

<img src="https://i.loli.net/2021/06/04/kVmuScgAFHnthzv.png" alt="Network Topology" style="zoom: 150%;" />

用户可先在Assets View资产发现、网络拓扑管理系统中使用Assets Scan模块创建任务,程序会调用后端C模块采用SNMP及nmap进行资产扫描、网络拓扑发现。并将数据存入mysql数据库。前端程序会对数据进行同步并展示到页面中。用户可以可以通过资产和服务管理功能对资产进行编辑、删除等管理操作

<img src="https://i.loli.net/2021/06/04/sROJMFwf2xIWrYK.png" alt="Assets" style="zoom:150%;" />

------

目前php端展示与C后端资产发现模块在同步开发当中，并未合并到一起。后续计划持续开发中....

> * 网络拓扑展示优化、可视化操作管理.
> * PHP调用C端网络拓扑发现接口.
> * 资产搜索功能.
> * 手动添加资产.
> * 漏洞扫描模块.


作者:Cryin' & Hardy
2016 年 09月 20日    
