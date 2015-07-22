## 读取用户登陆信息

#### 调用地址

http://api.bilibili.cn/log/login

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过300，默认为10。|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|time|int|登陆时间|
|time_at|string|登陆时间|
|ip|string|登陆IP|
|geo|string|登陆地理信息|
