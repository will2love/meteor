流星实时数据开发平台
-------------
<pre>
一个实时地干离线的活的平台！
基于hive sql，能进行任何复杂业务的sql运算。号称：只有想不到，没有做不到！
UV，PV，新UV，跟踪类指标，在线时长、在线人数等等，都可以算，并且是0误差！
</pre>

##### 一、特点：
<pre>
1、支持任何量级的0误差去重！
2、支持任何量级的大表join！
3、支持创建中间表
4、分钟级时延，一般为2分钟。
</pre>

##### 二、使用技术
<pre>
1、框架：kafka，spark-stream，spark-sql，redis集群，cassandra（可选），mysql
2、开发语言：java，scala
</pre>

##### 三、示意图
![image](https://github.com/meteorchenwu/meteor/blob/chenwu/mc/src/main/webapp/img/overview.jpg)

##### 四、理念
<pre>
1、系统按固定间隔（如1min）去kafka拉数据，叫时间片数据。
2、系统将各时间片数据转换成表，基于hive sql进行运算。
3、系统对各时间片数据独立无干扰进行运算。每个表系统都会自动加上当前时间片的uuid。
4、通过函数:c_sum,c_distinct,c_join,c_max和c_min.利用redis或cassandra,对所有时间片进行全局运算。
</pre>

##### 四、安装
[查看说明](https://github.com/meteorchenwu/meteor/blob/chenwu/README.md)


