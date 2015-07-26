## 读取视频信息

> 如需获取分P，需要以不同页码多次调用本接口 -- @fython

#### 调用地址

http://api.bilibili.cn/view

需要 App Key

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|id|true|int|AV号|
|page|true|int|页码|
|fav|false|int|是否读取会员收藏状态 (默认 0)|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|play|int|播放次数|
|review|int|评论数|
|video_review|int|弹幕数|
|favorites|int|收藏数|
|credit|int|评分数量|
|coins|int|推荐数量(硬币数)|
|title|string|标题|
|description|string|简介|
|tag|string|关键字|
|pic|string|封面图片URL地址|
|pages|string|返回记录的总页数|
|author|string|投搞人|
|mid|int|投搞人ID|
|cid|int|视频源及弹幕编号 弹幕地址 http://comment.bilibili.cn/<cid>.xml|
|offsite|string|Flash播放调用地址（如果沒有此项则此视频无法在站外播放）|
|create_at|string|视频发布日期|
|favorited|bool|当前帐号收藏状态|
|spid|未知|未知|
|tid|int|分区号|
|allow_feed|int|未知|
|allow_bp|int|未知|
|partname|String|分P名|
|src|String|未知|
|face|String|投稿者头像|
|typename|String|分类名|
