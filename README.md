##mongodb

####安装MongoDB
- MongoDB的数据存放在db目录中，但这个目录在安装时不会主动创建，需要手动创建。请注意：数据目录应该放在根目录下（如：c:\ 或 d:\）
- 为了在命令行中运行MongoDB服务器，需要在安装目录执行mongod.exe文件。
- 创建log日志文件
- 创建启动配置文件 mongodb.config
- 创建libs目录 存放mongodb的启动程序

####开启MongoDB
- cmd 启动 切换到安装目录，执行mongod程序
	- 方式1：命令 mongod.exe + 配置启动参数
	- 方式2：命令 mongod.exe --config + 配置文件地址
- shell启动 切换到安装目录，执行mongod程序
	- 方式1：命令 ./mongod --config + 配置文件地址
- 启动配置mongodb.config文件示例：
	- dbpath=d:/data/db
	- logpath=d:/data/log/mongodb.log
	- port=8081
	- serviceName=myMongoDB

- 启动参数：
	- ```--bind_ip``` 参数：绑定服务ip地址，若绑定127.0.0.1 则只能本机访问，不指定默认本地所有ip访问。
	- ```--logpath``` 参数：指定MongoDB的日志文件。
	- ```--logappend``` 参数：无
	- ```--dbpath``` 参数：指定数据库路径 d:/data/db
	- ```--port``` 参数：指定端口，默认为27017
	- ```--serviceName``` 参数：指定服务名称
	- ```--serviceDisplayName``` 参数：指定服务名称，有多个MongoDB服务执行时用。
	- ```--install``` 参数：指定作为一个windows服务安装

####链接MongoDB
- shell命令链接：./mongo --host 数据库地址+端口号  (注意：貌似不能使用127.0.0.1)