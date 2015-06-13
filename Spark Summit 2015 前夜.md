今年第二次参加湾区的Spark Summit. 现在家倒时差, 没事儿写两句


# 去年回顾
去年参加 Spark Summit 最关注的是Intel 的 StreamSQL 和 DataBricks Cloud

## [StreamSQL](https://github.com/thunderain-project/StreamSQL)
### 简介
* Intel出品
* 直接写SQL, 简化实时计算开发
* 基于spark Streaming

### 至今回顾
* 没看到社区很大关注和使用, Code 至今没有更新, 1.4 是否兼容未知
* 多个stream join 计算不止如何实现

## [Databricks Cloud](https://databricks.com/product/databricks)
### 简介
* AWS based, 简化spark 部署维护
* [Apache Zeppelin](https://zeppelin.incubator.apache.org/) 类似的UI, 简化数据可视化

### 至今回顾 
* 虽说AWS 已经进入中国, 但是账号体系和墙外的AWS 完全隔离, 导致Databricks和社区人员一度因为没有AWS cn-north-1 region的账号而无法测试spark-ec2 脚本, 更别提支持墙内使用Databricks Cloud 产品了. 
* 数据在国内AWS S3, 墙外AWS 其他region 数据互通是个大问题.
* 也没有听到后续使用者的反馈, 不知是Databricks 没有后续大力投入还是其他原因
* Apache Zeppelin 值得看好. 简直就是一个看上去实现更简单的HUE(已经无力吐槽HUE了)

# 今年

### 个人关注
* [Spark Tungsten](https://databricks.com/blog/2015/04/28/project-tungsten-bringing-spark-closer-to-bare-metal.html) , 能否让我从计算 memory 的搬砖活儿中走出
* SparkR , 后续计划将数据分析师的支持都走spark R, 尤其关注Spark R 对hive table兼容.
* Spark 跟hadoop社区抱团情况, 比如HortonWorks 和 Cloudera 
* 

### 疑问:
* 为何通篇没有了Databricks Cloud 的topic? 难道Databricks 已经放弃了这个产品?
* 貌似没有人提spark on AWS 的整合. 社区提供的spark-ec2 槽点如下:
	1. 不支持中国区AWS
	1. error handling不好, 例如, 如果aws 启动ec2 失败, 脚本会hang 住
	1. 扩展性不好, 不能根据业务实现一些简单的hook操作(例如对instance打tag)


# EOF
* 倒时差很难受

 


