## 读取用户收藏信息

#### 调用地址

http://api.bilibili.cn/favourite?ver=2

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|ver|false|int|API版本 推荐使用2 以下文档基于版本2|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过300，默认为10。|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|

#### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|aid|int|视频编号|
|typename|string|视频分类|
|title|string|视频标题|
|create_at|string|收藏日期|
|pic|string|封面图片地址|


## 添加收藏

#### 调用地址

http://api.bilibili.cn/favourite/add

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|添加的视频编号|

#### 错误代码

|代码|说明|
|----|----|
|-607|超过收藏上限|


## 删除收藏

#### 调用地址

http://api.bilibili.cn/favourite/del

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|删除的视频编号|
