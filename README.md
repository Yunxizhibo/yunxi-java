### 云犀直播JAVA-SDK, 官方API部分
@author  holger <wanghj@yunxi.tv>
@link
@version 1.0

### 1.初始化
```java
   YunxiApi.register(AccessKey , SecretKey);
```

### 2.获取活动列表
```java
   YunxiApi.getActivityList(page , pageSize , timestamp);
```
#### 返回数据(json)：
```json
   {
        "statusCode":"状态码(int型)",
        "data": {
            "activities": [
                {
                    "id":"ID",
                    "title":"标题",
                    "startTime":"创建时间",
                    "coverUrl":"封面",
                    "shareUrl":"分享地址"
                },
                {
                    "....":"...",
                },
                {
                    "....":"...",
                }
            ],
            "pageCount":"pageCount"
        }

    }
```

### 3.获取活动资料
```java
   YunxiApi.getActivityInfo(activityId , timestamp);
```

#### 返回数据(json)：
```json
     {
        "statusCode":"状态码(int型)",
        "data": {
            "activity": {
                "id":"ID",
                "title":"标题",
                "startTime":"创建时间",
            }
        }
    }
```

### 4.获取直播视频资料
```java
   YunxiApi.getActivityLiveStream(activityId , timestamp);
```
#### 返回数据(json)：
```json
    {
        "statusCode":"状态码(int型)",
        "data": {
            "livestream": {
                "id":"ID",
                "businessId":"商户ID",
                "streamId":"流ID",
                "paid":"直播套餐 3为免费版 2为专业版",
                "coverUrl":"封面地址",
                "commentAudit":"是否开启评论审核 0 关闭 1 开启",
                "publishUrl":"推流地址",
                "hlsLiveUrl":"HLS 协议视频地址",
                "rtmpLiveUrl":"RTMP 协议视频地址",
                "hlsPlaybackUrl":"原视频回放地址 当回放视频需要替代是请用replacePlayBackUrl",
                "replacePlayBackUrl":"视频回放地址 当该地址为NULL时用hlsPlayBackUrl 反之用replacePlayBackUrl回放地址",
                "snapshot":"截屏封面",
                "startedAt":"直播开始时间",
                "enddAt":"直播结束时间"
            },
            "wechatPlayUrl":"微信嵌入地址",
            "webPlayUrl":"网页嵌入地址",
            "appPlayUrl":"app嵌入地址",
            "embedPlayerUrl":"播放器嵌入地址",
            "totalNum":"围观人数"
        }
     }
```

### 5.获取直播视频评论列表
```java
YunxiApi.getCommentsList(lsId, page, pageSize, timestamp);
```
#### 返回数据(json)：
```json
{
	"statusCode": "状态码(int型)",
	"data": {
		"comments": [{
				"id": "评论ID",
				"userId": "评论用户id",
				"username": "评论用户名",
				"avatar": "评论头像",
				"content": "评论内容",
				"floor": "评论楼层",
				"createdAt": "评论时间"
				"official": "0 用户评论 1 官方评论 2 商户红包 3 用户红包 4 用户领取红包提示 "
			},
			{
				...
			},
			{
				...
			}
		],
		"pageCount": "总页数"
	}
}
```

### 6.保存直播视频评论
```java
YunxiApi.saveComment(lsId, 62968005, "十有八九", avatar, content, timestamp);
```
#### 返回数据(json)：
```json
{
	"statusCode": "状态码(int型)",
	"data": {
		"comment" {
			"id": "评论ID"
			"userId": "评论用户id",
			"username": "评论用户名",
			"avatar": "评论头像",
			"content": "评论内容",
			"floor": "评论楼层",
			"createdAt": "评论时间"
		}
	}
}
```

### 7.直播同步白名单评论
```java
YunxiApi.saveWhitelist(activityId, name, mobile, timestamp);
```
#### 返回数据(json)：
```json
{
	"statusCode": "状态码(int型)",
	"data": {}
}
```

### 8.第三方用户登录
```java
YunxiApi.userLogin(username, name, mobile, appUserId, avatar, gender, returnUrl, timestamp);
```
#### 返回数据：

 登录成功后返回returnUrl页⾯ 

### 9.获取用户详资料
```java
YunxiApi.getUserInfo(appUserId, timestamp);
```
#### 返回数据(json)：
```json
{
	"statusCode": "状态码(int型)",
	"data": {
		"user": {
			"id": 2341791245,
			"appUserId": "2341791233",
			"username": "测试",
			"avatar": "用户头像地址",
			"gender": "1"
		}
	}
}
```

### 10.更新用户信息
```java
YunxiApi.updateUserInfo(username, name, mobile, appUserId, avatar, gender, timestamp);
```
#### 返回数据(json)：
```json
{
	"statusCode": "状态码(int型)",
	"data": {
		"user": {
			"id": 2341791245,
			"appUserId": "2341791233",
			"username": "测试",
			"avatar": "用户头像地址",
			"gender": "1"
		}
	}
```
