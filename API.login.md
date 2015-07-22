## 用户登录

#### 调用地址

https://api.bilibili.tv/login

需要 App Key；此API调用权限需要额外申请，具体请联系网站客服。

#### 参数

|字段|必选|类型|说明|
|----|----|----|----|
|userid/email|true|string|帐号名或邮箱|
|pwd|true|string|明文密码|
|captcha|true|string|验证码 (请访问 https://secure.bilibili.tv/captcha 获取，需启用COOKIE 并需要传递至此API)|

#### 返回

|返回值字段|字段类型|字段说明|
|----------|--------|--------|
|mid|int|会员ID|
|access_key|string|用户授权密钥|
|expires|int|用户授权密钥过期时间|

#### 错误代码

|代码|说明|
|----|----|
|-625|密码重试次数过多|
|-626|帐号不存在|
|-627|密码不正确|
|-628|密码不安全|
