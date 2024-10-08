# restaurant-data-analyse  
**使用的技术点**：1.拼接数据：pd.contact([列1,列2...])  
2.分组进行统计:分组求和  
3.排序、切片Top10  
4.绘制柱状图走势和高度

### 一、对数据进行预处理：  
  通过观察excel表的内容，对数据有个初步的了解后，使用jupyterLab开始对数据进行预处理，包括：**处理NA、合并数据**；  
  通过对数据的观察，可以尝试从数据中得到以下信息:  
  ####1.订单表的长度  
  ####2.统计菜名的平均价格  
 ####3.什么菜最受欢迎  
 ####4.哪个订单ID点的菜最多  
 .....  
 处理NA时可以通过info，观察完数据后，发现含有数据的列无NA，而含有NA的列里没有任何数据，因此选择处理方式为删除含有NA的列。  
 在meal_order_detail表中，将日期均分为3份，每份10个天数，分成了三个子表，因此需要将这三个表连接起来形成一张完整的数据表（使用行连接）  
### 二、最受欢迎的菜分析并可视化：  
使用频数统计方法得出前十名最受欢迎的菜，然后使用matplotlib绘制图案，实现数据可视化。  

### 三、订单消费维度分析并可视化：  
1.得到点菜**种类**最多的订单中的前十名  
2.订单ID点菜**数量**最多的前十名，先得出订单中单道菜的消费总额（total_amounts），在这里将最常用的'order_id','counts','amounts','total_amounts'四列数据提取出来存储在一起（Group_sum），并且进行分组求和（'counts','amounts','total_amounts'）  
3.**消费额**前十名的订单ID，可以直接使用第二步时创建的Group_sum。  
4.**平均消费单价**最贵的订单前十名  
  
### 四、日期与时间维度进行点菜量分析：  
1.一天当中什么时间段点菜量比较集中，需要把data 中的 place_order_time 列的时间字符串转换为 datetime 对象  
2.哪一天点菜数目最多（排序选出前十名）  
3.查看星期几人数最多，点餐数最多，映射数据到星期
