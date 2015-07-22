## 读取视频排行信息

#### 调用地址

http://api.bilibili.cn/tags

需要 App Key

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|tid|true|int|分类编号 new排序为必填 其他为可选|
|page|false|int|结果分页选择 默认为第1页|
|pagesize|false|int|单页返回的记录条数，最大不超过100，默认为30。|
|tags|true|string|需要搜索的TAG|
|order|false|string|排序方式|

##### 排序方式

|字段|说明|
|----|----|
|default|按新投稿排序|
|new|按新评论排序|
|review|按评论数从高至低排序|
|hot|按点击从高至低排序|
|damku|按弹幕数从高至低排序|
|comment|按推荐数从高至低排序|
|promote|按宣传数排序（硬币）|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|name|string|分类名称|
|results|int|返回的记录总数目|
|pages|int|返回的记录总页数|
|list|array|返回数据|

##### 返回字段 "list" 子项

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|aid|int|视频编号|
|typeid|int|视频分类ID|
|typename|string|视频分类名称|
|title|string|视频标题|
|subtitle|string|视频副标题|
|play|int|播放次数|
|review|int|评论数|
|video_review|int|弹幕数|
|favorites|int|收藏数|
|author|string|视频作者|
|mid|int|视频作者ID|
|create|string|视频创建日期|
|description|string|视频简介|
|pic|string|封面图片地址|
|credit|int|评分数量|
|coins|int|推荐数量|
|duration|string|视频时长|
