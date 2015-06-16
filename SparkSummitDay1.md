Spark Summit 2015 Day 1
----------

今天是spark summit 2015 第一天, 总体感觉: ```人山人海, Data遍地```(人多, 大家都在聊data这个data那个). 具体的schedule 见这里<https://spark-summit.org/2015/schedule/>, 我主要听Developer Track. 记录一些见闻

## 上午: 广告和广告, 官方和赞助商
这种会议开场基本上都是广告, 最感兴趣的是databricks发布的cloud产品和timeful的的talk[A Tale of a Data-Driven Culture](https://spark-summit.org/2015/events/a-tale-of-a-data-driven-culture/)

#### databricks 亮相

* 就是去年的databricks cloud
* 去年还仅仅演示了Spark Streaming的功能, 今年功能比较全面, 包含:
	* notebook支持很多语言, markdown, sql, R, python, interactive coding && visualization, 从演示来看, 体验非常好
	* ML方面支持model server 一行代码发布, 之前是DataScientist做好模型交给Engineer 做一个在线server, 现在基本不需要engineer 介入(好悲伤要失业了)
	* 结构很有意思, 直接注册databricks account然后配置AWS Account, 然后databricks负责按需启动spark cluster 支持计算, 因此你的费用就是databricks 费用 + AWS instance的费用, 貌似不便宜
	
<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/spark_summit_2015/databricks_price.png" alt="price" title="databricks price" width="100%" />
	

#### Cloudera 和 HortonWorks 两家争相给Databricks 背书
* cloudera 早就集成了spark 发行
* Hortonworks 做了一个开源的[zepplin](https://zeppelin.incubator.apache.org/) 

#### Timeful: A Tale of a Data-Driven Culture
* 主要讲如何构建Data-driven的文化

#### 常规的做法

* 构建Data-driven, 大家想到的第一件事就是hire more SQL monkeys
* 这种做法不scale, 而且Loop 非常长: 
		
	```
	产品提出想法 -> SQL monkey 跑数据, 出报表 -> 跟产品解释 -> 产品又提出想法 -> SQL monkey 跑数据  ........
	```
	
* 最终结果就是SQL monkey 不耐烦, 事情不了了之
	
* 事情的本质在于
> * Most in your company want ** Answer ** from your data
> * Most are capable of finding answers from data, ** GIVEN  The Right Tool ** 
> * ** Your Goal is to find that tool that minimize friction to data ** 
	
##### 建议的做法
* 全员 ``` SQL monkey```
* 数据部门专注做工具, 方便PM等使用
* 速度速度速度, 降低迭代成本, Fail fast

最后贴几张拍的PPT

<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/spark_summit_2015/timeful-0.jpg" alt="timeful-0" title="timeful-0" width="100%" />
<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/spark_summit_2015/timeful-1.jpg" alt="timeful-1" title="timeful-1" width="100%" />
<img src="https://raw.githubusercontent.com/haitaoyao/blog_pic/master/spark_summit_2015/timeful-2.jpg" alt="timeful-2" title="timeful-2" width="100%" />

##### 总结


	


## 下午

##### Spark DataFrames: Simple and Fast Analysis of Structured Data

#### Spark-­on-­YARN: The Road Ahead


#### Making Sense of Spark Performance

