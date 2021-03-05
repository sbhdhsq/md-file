# RESTful

#### Representational State Transfer ——表现层状态转化

1. 看Url就知道要什么资源
2. 看http method就知道针对资源干什么
3. 看http status code就知道结果如何

`对接口开发提供了一种可以广泛适用的规范，为前端后端交互减少了接口交流的成本，是约定大于配置的体现。`

#### 符合REST接口URI

`例如`

* GET /api/dogs/{id}

> 获取一个小狗

* GET /api/dogs

> 获取所有小狗

* POST lapi/dogs

> 添加小狗信息

* PUT lapi/dogs/{id}

> 修改小狗信息

* DELETE /api/dogs/{id}

> 删除一只小狗

#### 常用注释

1. 径传参@PathVariabl
2. URL传参@RequestParam
3. 请求体body（form）@RequestParam 
4. 请求体body（json）@RequestBody

<img src="C:\Users\h227\Desktop\作业临时区\Snipaste_2021-03-04_20-53-00.png" alt="Snipaste_2021-03-04_20-53-00" style="zoom:100%;" />