Section1： 后端配置  gin路由、config配置

> [配置文件工具go-ini](https://ini.unknwon.io/docs/intro/getting_started)

Section2: [gorm使用](https://gorm.io/index.html)

SECTION2： 创建controller接口 、路由  

SECTION3: 编写查找用户、添加用户 接口

>1. ShouldBindJSON / Query(Key)
>2. c.JSON
>3. gin.H
>4. gorm {select, insert}

SECTION4：用户密码加密(bcrypt, scrypt)

好文https://astaxie.gitbooks.io/build-web-application-with-golang/content/zh/09.5.html

SECTION5: 更新用户，删除用户

> 1. gorm {delete软删除}
> 2. gin   c.Param c.Query  的区别是什么  获取入参 
>    1. Param是在路由里设置uri/:id   实际postman传输的uri/123   代码获取时用c.Param("id") = 123
>    2. c.Query是在路由里设置uri  实际postman传世的uri?query(如id=3&limit=10) 代码获取时用c.Query("id") = 3
>    3. shouldBindJSON是post用body获取的

SECTION6:博客增删改查

> 1. Preload 模型关联 看看别的吧
> 2. jwt 包实现登录



<font color=red>出现的问题：</font> 

> 1. category、user、article都在一个model包下   按照之前的喜欢命名 insert 、getById 会重复  目前只能每个方法后加上Category、user的后缀  有没有更好的办法解决
> 2. retrun 抽离公共方法返回  code、msg、data为参数
> 3. 入参加日志、 sql加日志 
> 4. context