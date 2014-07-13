

##使用帮助

###安装

请先确认已经安装Composer. 编辑项目中的 `composer.json` 文件，然后加入 `cooper/wechat`.

```
"require": {
	"cooper/wechat": "dev-master"
}
```

更新包 `composer update` 或者初始化包 `composer install`。

需要添加以下服务到系统。

打开 `app/config/app.php` ， 然后添加新的值到 `providers` 数组：

```
'Cooper\Wechat\WechatServiceProvider',
```

执行 `php artisan config:publish cooper/wechat` ,然后修改 `app/config/packages/cooper/wechat` 中的配置文件 `wechat.php` 。

把微信公众号的 `Token` `appId` `appSecret` 改为对应的。

##使用

todo

##类（说明）

###WeChatServer 主要实现的是“被动”接收消息和处理功能，如被动接收文本消息及回复，被动接收语音消息及回复等。

* getMessage 获取微信推送过来消息数据
* getXml4Txt (静态方法)获取文字消息XML
* getXml4ImgByMid (静态方法)获取图片消息XML
* getXml4VoiceByMid (静态方法)获取音频消息XML
* getXml4VideoByMid (静态方法)获取视频消息XML
* getXml4MusicByUrl (静态方法)获取音乐消息XML
* getXml4RichMsgByArray (静态方法)获取图文消息XML


###WeChatClient 主要实现的是“主动”请求功能，如发送客服消息，群发消息，创建菜单，创建二维码等。

* error (静态方法)返回错误信息对应的描述
* checkIsSuc (静态方法)判断结果状态
* getAccessToken 获取AccessToken
* setAccessToken 设置AccessToken
* upload 上传多媒体文件
* download 下载多媒体文件
* getMenu 获取自定义菜单
* deleteMenu 删除自定义菜单
* setMenu 设置自定义菜单
* sendTextMsg 发送文本消息（发送客服消息）
* sendImgMsg 发送图片消息（发送客服消息）
* sendVoice 发送语音消息（发送客服消息）
* sendVideo 发送视频消息（发送客服消息）
* sendMusic 发送音乐消息（发送客服消息）
* sendRichMsg 发送图文消息（发送客服消息）
* createGroup 创建分组
* renameGroup 修改分组名
* getAllGroups 查询所有分组
* moveUserById 移动用户分组
* getGroupidByUserid 查询用户所在分组
* getUserInfoById 获取用户基本信息
* getFollowersList 获取关注者列表

* getOAuthConnectUri 1、用户同意授权，获取code
* getAccessTokenByCode 2、通过code换取网页授权access_token
* refreshAccessTocken 3、刷新access_token（如果需要）
* getUserInfoByAuth 4、拉取用户信息(需scope为 snsapi_userinfo)

* getQrcodeImgByTicket 通过ticket换取二维码
* getQrcodeImgUrlByTicket 创建二维码ticket


##License
This is free software distributed under the terms of the MIT license