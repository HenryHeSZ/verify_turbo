## 插件说明

替换文件即可直接部署，按文件夹路径部署即可！

授权码有效期控制，支持被添加邀请码校验，被邀请用户可获得试用功能、邀请人可以增加天数，采用本地Sqlite数据库存储



## 部署过程注意事项，仔细看！

### 第一步

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/001.png)

首先替换项目主目录的config.py，然后打开config.json文件，添加以下参数

```json
    "accept_friend": False,     # 控制是否自动通过好友，受friend_password值影响，为真此项失效，可选项，默认为关
    "friend_password": True,    #  控制是否根据邀请码自动通过好友，不受accept_friend值影响，可选项，默认为关
    "hours_extension"：24,       #  控制授权裂变插件的邀请人奖励时间，单位小时
```



### 第二步

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/002.png)

路径：chatgpt-on-wechat\channel\wechat，把这两个文件名的文件进行替换



### 第三步

然后把godcmd和verify_turbo两个**文件夹**放到chatgpt-on-wechat\plugins下，配置verify_turbo目录内的json内容

```json
{
  "whitelist": false,		# 控制白名单功能，机器人的好友朋友圈权限设置为不看他朋友圈就是白名单用户，值为true时，白名单用户直通所有服务
  "group_lock": false,		# 控制群聊锁，值为true时，机器人在群聊被@会检测是否有提供激活码，没有则提示输入，针对单个用户，非整个群聊
  "trial_days": 1,			# 控制被邀请的新好友可获得试用的天数，正整数类型，默认为1
  "trial_reminder": "您已获得{days}天试用！\n{activation_code}",	# 控制新好友通过后得到的信息体，{days}和{activation_code}占位符分别对应试用天数和试用的激活码，请注意不要删除占位符，可自行搭配
  "restricted_reminder": "未激活，请输入激活码···",	# 控制未激活用户的提示语，可添加发卡平台链接，请自行编辑
  "authorization_expires": "激活码已过期，请输入新的激活码···"		# 控制输入授权码后，授权码已过期的提示语句
}
```



## 完成，重启项目即可，请务必检查各项配置是否输入无误！不然影响启动！



![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/003.png)

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/004.png)

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/006.png)

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/007.png)

![](https://github.com/chazzjimel/verify_turbo/blob/main/doc/images/005.jpg)
