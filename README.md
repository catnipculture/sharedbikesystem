> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

系统有管理员、用户两个角色。

校园共享单车管理系统主要分为6个模块分别是系统用户管理模块、单车信息管理模块、学生信息管理模块、租金管理模块、信息统计模块、租赁信息管理模块

1.系统用户管理模块分为三个小模块:

(1)添加用户信息：用户注册个人信息，填写信息资料并提交后，可以登陆该系统。

(2)删除用户信息：对系统中已经注册完毕的用户信息，进行删除操作。

(3)修改用户信息：对系统中已经存在的用户信息，进行修改操作。

2.单车信息管理模块分为三个小模块:

(1)增加单车信息：添加新增的单车信息。

(2)删除单车信息：部分单车报废或丢失时，删除相应的单车信息。

(3)查询单车信息：对单车使用情况进行查询。

3.租户信息管理模块分为三个小模块:

(1)租户信息添加：可添加新的租户信息。

(2)租户信息修改：后台管理员有相应权限修改、删除用户信息，用户可对自己的基本信息进行修改。

(3)租户信息查询：可对系统中已注册的用户信息进行查询。

4.租金信息管理模块分为四个小模块:

(1)租金信息统计：租金部分为共享单车的实际收入，每笔租金都有明确来往记录信息。

(2)租金退还管理：学生在还车后缴纳租金，并返还押金，如果超时还车或未还车，租金会按一定比例扣留。

5.租赁信息管理模块分为两个小模块:

(1)租赁记录查询：当学生借取单车时，可快速查询到借车记录。

(2)租赁信息查询：当用户还车时，在租赁信息中可查找到学生的租赁历史记录。

6.信息统计模块:

此模块是对账使用记录租金流水、保有押金、车辆总计、在库车辆、学生总计、借车人数等数据进行统计。

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)

# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/a86ee42124820d14732b50da55a8740f.png)

![img](https://i-blog.csdnimg.cn/img_convert/d589ed95f7803a86cb2f53fae53c955a.png)

### 项目截图

前台

![8702b73cc6f445e0a64c26e9a776ddcd](https://i-blog.csdnimg.cn/img_convert/aedc1422efe84ce0242e5f780d579203.png)

![7551d70f12b47727094f3bfae697c1e9](https://i-blog.csdnimg.cn/img_convert/e464e99ffd9958e3c769808530aa1215.png)

后台

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue0](https://i-blog.csdnimg.cn/img_convert/5a3fe8ac6d09aad2eda813d5d392ae70.png)

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue1](https://i-blog.csdnimg.cn/img_convert/c9a43c148607101fffa69bd04917b187.png)

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue2](https://i-blog.csdnimg.cn/img_convert/ac4b3600f93ece5f8e8b5c319a34f65e.png)

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue3](https://i-blog.csdnimg.cn/img_convert/c951abec1ab1f03736cde5b2bba7312d.png)

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue5](https://i-blog.csdnimg.cn/img_convert/42347dd49757bcf319fae4829e7272fd.png)

![ssm060基于SSM的高校共享单车管理系统的设计与实现vue6](https://i-blog.csdnimg.cn/img_convert/1496aa495b978080b7fd9b2b3eeb8940.png)

### 代码

```
  //保存数据
        SystemResourcesDO systemResourcesDO = new SystemResourcesDO();
        systemResourcesDO.setCreateTime(System.currentTimeMillis());
        systemResourcesDO.setModifyTime(System.currentTimeMillis());
        systemResourcesDO.setJsonData(JSON.toJSONString(deviceResources));
        systemResourcesDO.setDataType(2);
        systemResourcesMapper.insert(systemResourcesDO);

        Integer yesterdayOnlineDeviceCount = getYesterdayOnlineDeviceCount();
        deviceResources.setYesterdayOnlineDeviceCount(yesterdayOnlineDeviceCount);
        return SingleResponse.of(deviceResources);
```
