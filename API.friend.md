## 读取粉丝信息

#### 调用地址

http://api.bilibili.cn/friend/fans

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
|record_id|int|好友记录编号|
|fid|int|好友帐号ID|
|addtime|int|添加时间|
|uname|string|好友暱称|
|face|string|好友头像地址|


## 读取我的关注信息

#### 调用地址

http://api.bilibili.cn/friend/attention

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
|record_id|int|好友记录编号|
|fid|int|好友帐号ID|
|addtime|int|添加时间|
|uname|string|好友暱称|
|face|string|好友头像地址|


## 读取我的悄悄关注信息

#### 调用地址

http://api.bilibili.cn/friend/whisper

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
|record_id|int|好友记录编号|
|fid|int|好友帐号ID|
|addtime|int|添加时间|
|uname|string|好友暱称|
|face|string|好友头像地址|


## 读取我的互粉好友

#### 调用地址

http://api.bilibili.cn/friend/fans_eachother

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|game_id|false|int|获取已安装/未安装游戏好友|
|game_status|false|bool|获取已安装/未安装游戏好友 (true 已安装 false 未安装)|
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
|fid|int|好友帐号ID|
|uname|string|好友暱称|
|face|string|好友头像地址|


## 读取我的黑名单信息

#### 调用地址

http://api.bilibili.cn/friend/badlist

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
|record_id|int|记录编号|
|fid|int|黑名单帐号ID|
|addtime|int|添加时间|
|uname|string|黑名单暱称|
|face|string|黑名单头像地址|


## 添加黑名单

#### 调用地址

http://api.bilibili.cn/friend/badlist/add

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要添加的黑名单帐号|


## 取消黑名单

#### 调用地址

http://api.bilibili.cn/friend/badlist/del

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要取消的黑名单帐号|


## 添加关注

#### 调用地址

http://api.bilibili.cn/friend/attention/add

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要添加的关注帐号|


## 取消关注

#### 调用地址

http://api.bilibili.cn/friend/attention/del

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要取消的关注帐号|


## 添加悄悄关注

#### 调用地址

http://api.bilibili.cn/friend/whisper/add

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要添加的关注帐号|


## 取消悄悄关注

#### 调用地址

http://api.bilibili.cn/friend/whisper/del

需要 App Key 并验证登录状态(Access key)

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|mid|true|int|要取消的关注帐号|
