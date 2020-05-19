### Docker给MongoDB设置用户密码

```text
没有用户和密码,MongoDB的客户端NoSQL Manager for MongoDB是无法连接的
设置用户和密码如下
#admin进入
docker exec -it 10b15378e5ae  mongo admin 
#创建用户和密码
db.createUser({ user: 'admin', pwd: 'mark2020', roles: [ { role: "userAdminAnyDatabase", db: "admin" } ] }); 

#验证一下对不对
db.auth("admin","123456");
#退出
exit

修改密码 
use admin;
switched to db admin
> db.changeUserPassword('admin','88889999'); 
```
```text
111.231.189.45
27018

READ_ME_TO_RECOVER_YOUR_DATA
admin
mark2020
```


### 常用命令
```text
show users：查看用户
show dbs：显示所有数据库
show collections：显示当前数据库下的所有集合
use 数据库名：使用某个数据库
db.auth('username','password')：用户验证
db.dropDatabase()：删除当前数据库
db.集合名.insert()：添加集合的内容
db.集合名.drop()：删除集合
db.集合名.find()：查看集合的内容
```
- [x] 集合
````text
//给指定集合添加记录
db.[collectionName].insert({...})
//查询一条记录和查询全部
db.collection.findOne()
db.collection.find()

//更新记录
db.[collection].update({查询条件},{$set:{更新内容}})

//删除
db.[collection].remove({删除条件})
//删除集合
db.[collection].drop()

//删除库
````

