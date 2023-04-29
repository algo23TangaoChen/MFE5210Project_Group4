参考vnpy的架构，实现事件驱动型回测框架。  

核心：  
1.回测类：封装了模拟交易所类、策略类和订单管理类  
2.事件类：事件队列（参考vnpy）  
3.引擎类：封装了事件类，是模拟交易所类、策略类和订单管理类的父类  

数据库：  
1.数据来源：tqsdk历史行情数据，现存储了全合约2023年1月3日到2023年1月11日的level1 Tick数据  
2.数据库：dolphinDB（免费版）  
3.功能：读取、写入历史数据，读取目前存入数据概况（合约、时间区间、总条数）  


模拟交易所：  
1.发送行情  
2.管理订单&成交  
3.撮合订单  

#策略类  
1.产生买卖信号  
2.用买入并持有策略进行测试  

订单管理类  
1.管理仓位&账户  
2.产生下单信号  



database -> dataengine -> tickdata -> event -> strategy -> signal -> order manmage sys -> excution
db.database.get_database() -> simExchange.publish_md() -> core.event -> stratgey -> oms -> simExchange.cross_limit_order()


0.看半成品, 
1.移动数据库、换数据 ！
2.买入并持有-》双均线 （vnpy）选
3.risk manager ！
4.algo trading 
5.tca 
6.可视化 
7.部分成交 选 
8.GUI 选
9.PPT ！

