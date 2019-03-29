# egg-admin

### 说明：

- 基于egg架构的自动生成接口的框架

### 数据接口:

等待更新

### 目录结构:

- admin — 客户端后台管理系统
- sever - 服务端，基于node的后台开发
- ptadmin.sql - mysql的sql 语句

### 模块分析：

1. Column 栏目模块（数据库）注释:原则上不暴露给其他用户
  	- 对于表的增删改查操作
  		- 新建数据库
  		- 修改数据库
  		- 删除数据库
  			
  	- 字段
  		- 增字段(产生随机标识)
  		- 删字段
  		- 改字段(通过标识来修改字段(identifies))
  		
2. Program 系统模块
  	- 增删改字段的信息
  	- 验证码模块
  		-图片验证码管理 (接口确定即可) 
  	- 短信管理 目前未完成
  	- 邮箱管理 e_mail 作为邮箱的配置
  	- 图片管理(这里做压缩的功能)
   - 文件管理 设置存储位置，标题，内容
3. People 人员模块
  	- 人员的增加
  		- 注册
  			- 手机号注册
  			- 邮箱注册
  			 
  		- 后台增加(用户名为唯一标识)
  	
  			(people 来控制人员的信息   people_ext 人员扩展信息)
  	
  	- 人员的删除
  	- 人员的修改
  	- 登录 
  		- 邮箱登录 
  		- 手机登录
  	- 角色
  	   - role 角色表 来控制

        ```
        1000 增
        1100 增删
        1110 增删改
        1111 增删改查
        0100 删
        0110 删改
        0111 删改查
        0011 改查
        0001 查

        角色 
        角色id    表                                          增删改权限      可以控制字段
        xxxx     9DA6E0E3-302E-98B4-6B6B-68639CD887DD        1000           name||&&||name||&&||sex
        ``` 	
4. DataDictionary 数据词典
   - 新建数据词典
   - 管理数据词典 
   - 暂不处理 

5. Template 模板模块
	- 采集管理(暂不处理)
   - 模板管理(暂不处理) 
  
  		
  ---------------------

### 代码规范 

-	flag 作为核心的代码来判断整个框架的请求参数


| 参数        | 含义     | 备注    | 
| --------   | -----:  |  -----:   | 
| 0          | 成功     | 通过infos,可以拿到数据
| 1          | 请求失败  | 原则上应该在msg返回错误提示 | 
|10001       | 没有权限  | 前端这边应该有个判断，跳回某个页面|

- 分页返回规范
	
	```
	 {
	    "flag": 1,
	    "pages": {
	        "total": 63, //总页数
	        "currentPage": "1",//当前页
	        "pageSize": "1" //一页加载多少
	    },
	     "infos": [
        	{
            "id": 1,
            "facility": "ipad 2",
            "issue": "屏幕",
            "price": "150",
            "processing": "更换外屏",
            "Stick": "1"
        	}
   		 ]
	 }

---------------------

### 代码使用：
- npm i egg-init -g
- npm i nodeinstall -g
- npm i

### 源码地址：

https://github.com/MYQ1996/egg-admin