## 搜索

#### 调用地址

http://api.bilibili.cn/search

需要 App Key

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|keyword|true|string|搜索的关键字，必须做URLencoding。|
|page|false|int|搜索结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过100，默认为20。|
|order|false|string|排序方式|

##### 排序方式

|字段|说明|
|----|----|
|default|综合排序|
|pubdate|按发布日期倒序排序|
|senddate|按修改日期倒序排序|
|id|按投稿ID倒序排序|
|ranklevel|按相关度排序|
|click|按点击从高至低排序|
|scores|按评论数从高至低排序|
|damku|按弹幕数从高至低排序|
|stow|按收藏数从高至低排序|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|type|string|mylist 我的列表 video 视频 special 专题|
|lid|int|我的列表编号 当type为mylist时才会出现|
|aid|int|视频编号 当type为video时才会出现|
|spid|int|专题编号 当type为special时才会出现|
|author|string|视频作者|
|play|int|播放次数|
|review|int|评论数|
|video_review|int|弹幕数|
|favorites|int|收藏数|
|title|string|视频/mylist/专题标题|
|description|string|视频/mylist/专题描述|
|tag|string|视频/mylist/专题关键字|
|pic|string|封面图片地址|

#### 错误代码

|代码|说明|
|----|----|
|-501|系统错误|
|-502|搜索正在进行中|
