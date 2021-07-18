# 使用python 玩股票  (代码基于python3 数据库为mysql)
首先申明:使用本项目中的程序抓取或分析股票数据进行的投资行为,造成的损失本人概不负责,如果不能接受请勿查看下载及使用相关代码


安装使用准备：
     
    1、下载代码：git clone https://github.com/newhackerman/TDXPystock.git
    2、安装好mysql数据库，执行init.sql里的SQL语句完成数据结构的初始化
    3、执行pip install -r requirements.txt 安装好项目所需要的python包
    4、建一个数据库连接配置文件：mysqlconfig.json 里面内容为：{"host":"xxxxxx","user":"xxxxxx","password":"xxxxxx","database":"xxxxxx","tushare":"xxxxxx"}  xxxxxx使用真实的配置代替
    5、代码中使用的一些文件配置路径，请根据自己真实的环境修改
        
---------
功能使用说明：

一、结合通达信操作准备
      
      1、导出个股竞价数据  
         
         早盘开盘后（9.25分）当集合竞价数据生成完成了    
         执行util\TDX_OpenDataOutput.py  会将A股个股数据，板块数据，主要指数数据导出到excel
         也可以执行：通达信早盘数据导出入库并写可用自定义文件.py　一键完成 A股个股数据，板块数据，主要指数数据导出到ｔｘｔ  ，并完成早盘数据入库，写入通达信调用
              
      2、写北向资金数据
         执行 util/WriteToTDX.py   可以更新最新的北资变动数据，并写入通达信（注意修改自己的通达信目录）
      --通达信数据导出完成

二、 南北向资金查询与分析
        
        python 南向资金.py  #获取南向资金,并入库
        python 北向资金.py  #获取北赂资金并入库
        
        python 南向资金分析工具.py  （具体功能见程序输入菜单）
        python 北向资金分析工具.py 


三、 A股信息简介与主营（已整合，不再维护此功能）
      
      先执行 stocklist= get_stockInfo()方法获取主营数据
      insertstockinfomation(stocklist)  #将数据写入到表中 
      
      python A股信息简介与主营.py  第一   #即可查询简介中含有‘第一’关键字的股票 
      
四、早盘板块异动
       
      （需要先将数据写通达信文件）
       执行通达信早盘板块异动.py
       此功能将会读到板块竞价数据，通过自定的条件算出今日异动的板块
       
       
五、早盘主力异动个股提示
       
       执行通达信早盘异动将会算出早盘异动的个股（需要先将数据写通达信文件）
       
六、早盘选股

        执行通达信早盘选股.py 
        会根据导出的txt 算出符合量比组合条件或换手组合条件筛选出符合 条件的个股 

七、查询概念相关联的股票或个股对应的相关概念，与主营业务，公司亮点（支持多条件查询）
   
         概念与早盘数据查询.py 
         python 概念与早盘数据查询.py  "info like '%光伏%'"'"   #查询光伏概念相关的股票
         
         python 概念与早盘数据查询.py  “name='中直股份'”         #查询中直股份的概念与主营业务，公司亮点（支持多只个股查询例："name in('隆基股份','通威股份')"）

         python 概念与早盘数据查询.py stockopendata name='福耀玻璃'  #查询耀玻璃 的早盘数据
        --此功能需要结合其它工具更新相关数据（暂时放弃维护）
        
八、A股、港股、美股优秀企业初步筛选（特别是A股，减少暴雷的机率）
       
       python A股领先企业.py
       
       python 港股领先企业.py
       
       python 美股领先企业.py   #获取港股(数据来源于富途证券的"股票百科")关键字:['全球领先' , '行业第一' , '全球第一' ,'市占率第一', '全球最大' , '龙头' ,'全球唯一','中国最大']
        
  九、A股，港股，美股，期货等行情数据下载
     
     util/asShare_unit.py   此代码提供A股，港股，美股，期货等行情数据下载
 
 
        
感谢您的关注，使用中有任何疑问，请与我联系：QQ:860760123  微信：newhackerman@163.com ,也可以新建issues                         

如果您认为还不错，也可以随意打赏

![打赏码](http://a1.qpic.cn/psc?/V50pq8k53VZO9a3umeIZ2wCqaK3By0Ps/bqQfVz5yrrGYSXMvKr.cqVxfLFaYy4E4HwL0Zduhn*Bk5YYQ.Ny0K.TtQVqPBgzetsBsws0o2rCt5Y8uo2PFu5aE6Z.q0U8VnJmbCC7.4*c!/c&ek=1&kp=1&pt=0&bo=8gLKAgAAAAABFwg!&tl=3&vuin=860760123&tm=1613354400&sce=60-2-2&rf=0-0)

