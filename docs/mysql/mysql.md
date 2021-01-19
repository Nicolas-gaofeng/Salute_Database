## 一、下载

1. 下载MYSQL安装包。

MYSQL官方网站：https://dev.mysql.com/downloads/mysql/

![image-20210120013051478](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120013051.png)

MSI Installer注意有两个，这两个有什么区别呢？

第一个（大小是10多M）是联网在线安装，会在线下载安装包。
第二个（大小是200多M）是离线安装，这里我们选第二个（上图红框的那个，已经同时包含了32位和64位安装包），下载到本地进行安装。点击“Downloda”进入下载页面。

2. 在下载页面，选择最下面的：No thanks，just start my download.，进入下载状态。

![image-20210120013132557](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120013132.png)

3. 下载完成后本地就有安装文件了，通过文件名可以看出是哪个版本的mysql数据库，本次安装下图红框的mysql数据库版本8。

## 二、安装

1. 双击安装软件开始安装

![image-20210120013707563](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120013707.png)

2. 初始页面，可能等待一小会。

   ![image-20210120013844322](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120013844.png)

3. 左边界面是安装到了哪一步，下图是选择安装类型，选Server only（只安装mysql），然后点击“next”。

![img](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120013525.jpeg)

4. 点击Execute开始安装

![image-20210120015422247](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120015422.png)

5. 点击next

![image-20210120015513508](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120015513.png)

6. 点击next

![image-20210120015527151](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120015527.png)

7. 默认，继续点击next

![image-20210120015612453](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120015612.png)

8. 密码验证方式（Authentication Method）这一步很重要

第一个是强密码校验，mysql推荐使用最新的数据库和相关客户端，MySQL8换了加密插件，所以如果选第一种方式，很可能你的navicat等客户端连不上mysql8。

所以这里一定要选第二个（下图红框的地方），因为我们后面使用mysql客户端navicat版本是9.X，它链接mysql用的是就是这个加密算法，所以这一步很重要。（重要的事情说三遍）

![image-20210120020500954](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120020501.png)

选完，点击next继续

9. 设置密码，需要牢记，最好将登陆用户名（是root）和密码（下图的地方设置）记录到其他地方，因为后面要用这个密码连接数据库。输入完，点击next继续。 在这里我设置为mysql。

![image-20210120021317952](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021318.png)

10. 默认点击next继续。

![image-20210120021428116](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021428.png)

11. 点击执行（Execute）安装

![image-20210120021649608](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021649.png)

12. 点击Finish

![image-20210120021721572](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021721.png)

13. 点击next

![image-20210120021754899](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021754.png)

14. 安装完点击“finish”

![image-20210120021839756](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021839.png)

## 三、验证安装

1. 按下图操作从开始菜单中打开刚刚安装的mysql命令行客户端，点击mysql 8.0 command line client -unicode

![image-20210120021931725](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120021931.png)

2. 输入密码

![image-20210120022039879](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120022039.png)

如果能显示出下面红线类似的内容表示安装成功。红线标出的是mysql数据库版本号，可与下图版本号不一样，以实际安装的版本为准。

![image-20210120022115246](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120022115.png)



## 四、navicat安装

### 1. 简介

Navicat Premium 是一套數據庫管理工具，讓你以單一程序同時連接到 MySQL、MariaDB、SQL Server、SQLite、Oracle 和 PostgreSQL 數據庫。 此外，它與 Drizzle、OurDelta 和 Percona Server 兼容，並支持 Amazon RDS、Amazon Aurora、Amazon Redshift、SQL Azure、Oracle Cloud 和 Google Cloud 等云數據庫。

結合了其他 Navicat 成員的功能，Navicat Premium 支持大部份在現今數據庫管理係統中使用的功能，包括存儲過程、事件、觸發器、函數、視圖等。
Navicat Premium 能使你快速地在各種數據庫係統間傳輸數據，或傳輸到一份指定 SQL 格式和編碼的純文本文件。計劃不同數據庫的批處理作業並在指定的時間運行。其他功能包括導入向導、導出向導、查詢創建工具、報表創建工具、數據同步、備份、工作計劃及更多。

Navicat 的功能足以符合專業開發人員的所有需求，但是對數據庫服務器的新手來說又相儅容易學習。

### 2. 下载

navicat安装包 ：链接：https://pan.baidu.com/s/1KODRaKhA2pMkKYwjsqQyAw 提取码：x9zr 

破解补丁：链接：https://pan.baidu.com/s/1t7E4MG1tgMKZpWjOCkZMKA 提取码：vebn 

### 3. 安装

1. navicat默认安装即可，安装完毕后，将破解补丁复制到安装目录下，运行破解补丁，先patch；

![image-20210120024157941](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120024158.png)

2. 选择语言和版本

![image-20210120024245105](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120024245.png)

3. 断网，运行navicat，弹出注册页面，如果沒有弹出注册页面，手动在菜单打开：帮助->注册，然后点击注册机的generate按鈕，注册码会自动填写到navicat

![image-20210120024450762](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120024450.png)

4. 点击navicat注冊界面的激活按钮，提示手动激活；

![image-20210120024601891](C:\Users\zgf\AppData\Roaming\Typora\typora-user-images\image-20210120024601891.png)

5. 点击手动激活，然后将得到的RequestCode复制到注册机

![image-20210120024734944](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120024735.png)

6. 点击注册机左下方的Generate按钮，生成ActivationCode，复制粘贴到navicat的激活码框，完成激活；

![image-20210120030120568](C:\Users\zgf\AppData\Roaming\Typora\typora-user-images\image-20210120030120568.png)

7. 激活完成

   ![image-20210120030227287](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120030227.png)

### 4. 连接数据库

1. 点击左上角 “连接” - 选择 “MySQL”

![image-20210120030906069](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120030906.png)

2.输入如下信息，然后点击 “确定”

```text
连接名：127.0.0.1    （127.0.0.1是本机IP）
主机：localhost     （本机）
端口：3306          （默认MySQL的端口就是3306）
用户名：root         （如果自己不设置用户名，默认就是 root）
密码：******         （就是安装MySQL时候设置的密码）
```

![image-20210120031004859](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031004.png)

3. 这时候可以看到已连接上的数据库，和数据库下面的表名

![image-20210120031030320](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031030.png)

4. 可以右键 - “新建数据库”

![image-20210120031107378](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031107.png)

5. 输入如下信息，然后点击 “确定”

```text
数据库名：school		（这个可以自定义，这里只是举个例子）
字符集：utf8		 （这个就是字符编码，现在通用的就是utf-8）
排序规则：			（这个暂时不用填写）
```

![image-20210120031142239](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031142.png)

6. 数据库创建完成后，双击打开，选择 “表” - 右键 - 新建表

![image-20210120031205680](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031205.png)

7. 在 “名”这一列可以输入字段名，点击 “添加字段”可以添加多个字段，“类型”就是该字段的类型，“长度”也可以自定义

![image-20210120031223412](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031223.png)

8. 点击左上角的 “保存”，输入表名

![image-20210120031254380](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031254.png)

9. 这时候，一个数据库的表就创建完成了，这张表是student，里面的字段有 name、age、gender、class，可以随意添加记录进去

![image-20210120031315992](https://gitee.com/zgf1366/pic_store/raw/master/img/20210120031316.png)

## 五、问题

如果遇到问题，移动到这个文章有每一个问题的解决办法：

https://zhuanlan.zhihu.com/p/37851412