## 读取番剧专题信息

#### 调用地址

http://api.bilibili.cn/bangumi

需要 App Key

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|btype|false|int|番剧类型 2:二次元新番 3:三次元新番 默认:所有|
|weekday|false|int|周日:0 周一:1 周二:2 周三:3 依此类推|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|title|string|标题|
|cover|string|封面图片地址|
|bgmcount|int|番剧当前总集数|
|weekday|int|番剧周信息|
|lastupdate|int|最后更新时间(UNIX Timestamp)|
|lastupdate_at|date|最后更新时间|
|new|boolean|是否最近有更新|
