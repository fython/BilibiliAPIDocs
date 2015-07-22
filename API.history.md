## 读取播放历史信息

#### 调用地址

http://api.bilibili.cn/history

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|results|int|返回的记录总数目|
|list|object|返回数据|

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
