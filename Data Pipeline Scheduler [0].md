Data Pipeline Scheduler [0]
--------------
* Spark Summit 2015 前夜倒时差, 继续扯淡

## 美好的开始
故事的开始总是美好的, 刚启动的计算任务一般都是这么简单的一个德行:

1. 获取日志数据/DB数据
2. 做一些简单的ETL
3. 计算报表

谁家的Data Pipeline不是从这么美好开始的(如下图)

<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/data_pipeline_scheduler/DPS1.png" alt="简单的任务" title="简单的任务" width="350" />

#### 'so easy' 的实现
* crontab 一下搞定, 
* 1点钟开始拉日志是不是, 
* 3点钟开始ETL是不是, 
* 5点钟开始计算报表是不是? 
* 顶多加一个重试机制, 保证半夜不被报警信息吵醒(什么? 你的计算任务不具有幂等性? OMG~)


## 噩梦的开始
* 是不是数据源开始多起来了?
* 是不是数据源开始'不靠谱'起来, 经常早上起床发现某重要指标昨天为0, 找了半天原因发现原来其他部门同事的数据源还没有ready? 然后各种修改 crontab 任务启动时间是不是?
* 是不是计算集群也开始不稳定了? 经常算到一半各种资源调度问题? Job 有时会失败?

任务依赖变成了下面这个样子(可能还更复杂):

<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/data_pipeline_scheduler/DPS2.png" alt="复杂的任务" title="复杂的任务" width="350" />

* 业务部门同事开始抱怨数据服务不靠谱了是不是?
* 时不时要给人发邮件说昨天数据还没算完, 给人赔不是是不是?

## 痛定思痛, 我们需要一个调度系统了是不是!
整理一下***功能性***需求, 其实需要解决的核心问题:

* 任务依赖管理. 保证任务在前置任务完成后再执行,避免空跑任务
* 任务生命周期管理. 任务失败追踪, 失败后重试, 重试一直不成功后报警

还有*** 非功能性需求*** :

* 引入调度系统, 所有任务由调度系统调度, 那调度系统的HA 很重要. 
* 任务依赖可视化: 方便规划任务
* 任务失败恢复: 一旦任务失败, 故障恢复后如何继续完成失败的workflow
* 调试友好: 新开发任务时如何方便调试
* 任务部署: 统一调度任务后, 计算任务代码如何部署? 可能涉及跨部门代码部署

## 我们都是架子工: 找开源方案攒一个
整理一下市面上可选的开源方案:

* [Azkaban](http://data.linkedin.com/opensource/azkaban) linkedin 大厂出品
* [luigi](https://github.com/spotify/luigi) Spotify 出品
* [airflow](https://github.com/airbnb/airflow) Airbnb 出品

肯定还有其他方案, 就不列举了.


## EOF 
* 一宿没睡太困了. 今天先写到这里. 本着想当```好架子工``` 的原则, 下回我们先造一个简单的轮子, 再评估现有轮子的优劣.

