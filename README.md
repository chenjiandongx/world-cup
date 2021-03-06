# 世界杯模拟查询接口

#### 概况

假设现在我们有一个面试题。题目的要求是这样的

请你使用最熟悉的 Python web 框架根据 2018 世界杯小组赛情况实现一些查询功能接口。

数据参考链接：http://2018.sina.com.cn/schedule/group.shtml


#### 接口要求

> 分数相同根据球队名正序排序,未完成的小组赛在合理情况内自行决定比赛分数（小组赛今天已经结束）

* 返回所有 32 强所有球队，要求使用分页(参数 page 和 per_page 分别代表第几页和每页多少条记录)
* 返回每个小组净胜球最多的球队
* 返回比分差距最大的 3 场比赛记录(按照比赛日期逆序排序)
* 返回每个小组晋级的两只球队(排名优先级：积分、净胜球、球队名)
* 数据库使用 sqlite3


题目拿到了，分析一下需求，然后就可以开码了
首先需要拿到数据，题目已经给出了参考链接，数据是由 js 动态生成的，一番分析之后，顺利的拿到数据。清理一下，保存为 [world_cup.json](https://github.com/chenjiandongx/world-cup/blob/master/world_cup.json)。
数据库要求使用 sqlite3，其实这也好，python 自带的电池。数据库 ORM 使用了 [pony](https://docs.ponyorm.com/)。

#### 项目结构
* model.py: 负责建立数据库模型
* controller.py: 负责数据库的操作
* api.py: 负责 web api，框架使用了 Flask


#### 其他文档
* [接口文档](https://github.com/chenjiandongx/world-cup/blob/master/api.md)
* [部署文档](https://github.com/chenjiandongx/world-cup/blob/master/deploy.md)


#### License
[MIT ©chenjiandongx](https://github.com/chenjiandongx)
