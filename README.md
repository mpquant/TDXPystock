# testOne
使用方法：
---------
一、---通达信操作：
   1、导出个股竞价数据
   
   早盘开盘后（9.25分）当集合竞价数据生成完成了
    
    定位到在A股板块信息列表中，选择"选项，数据导出"--导出所有数据---格式为EXCEL" 等待几十秒后打开文件，删除今日未开盘的个股，
    再另存为EXCEL为 xls的文件
   2、导出板块竞价数据
   
    定位到板块指数列表，在列表中，点选所有板块，选择"选项，数据导出"--导出所有数据---格式为EXCEL" 等待几秒后打开文件
    再另存为excel (格式选择 excel97~2003的xls )
---通达信数据导出完成

二、---写数据：

       写竞价数据 执行：执行“通达信写自定义总价数据文件.py”  
       此功能会将导出的板块与个股的竞价数据导入到通达信用，以供通达信自写指标读取使用
三、---早盘板块异动
       
       执行通达信早盘板块异动.py
       此功能将会读到板块竞价数据，通过自定的条件算出今日异动的板块
       
       
四、---早盘主力异动个股提示
       
       执行通达信早盘异动将会算出早盘异动的个股
       
五、 --- 早盘选股

        执行通达信早盘选股.py 
        会根据导出的excel 算出符合量比组合条件或换手组合条件筛选出符合 条件的个股 

感谢您的关注，使用中有任何疑问，请与我联系：QQ:860760123  微信：newhackerman@163.com                          

通达信数据文件读取.py   读取通信数据文件转换为CSV（本地日线数据，5分钟数据）
DataCcodeandDecode.py  杂文件，编解码
students.py    学习案例，未写完
shangseqiuxuanhao.py   随机生成双色球号码