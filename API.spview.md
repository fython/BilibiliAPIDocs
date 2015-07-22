## 读取番剧专题信息

#### 调用地址

http://api.bilibili.cn/spview

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|spid|true|int|专题SPID|
|season_id|false|int|专题分季ID|
|bangumi|false|int|设置为1时只返回番剧类视频 设置为0时只返回普通视频 不设置则返回所有视频|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|result|int|返回的记录总数目|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|title|string|标题|
|cover|string|封面图片地址|
|aid|int|视频ID|
|click|int|点击数|
