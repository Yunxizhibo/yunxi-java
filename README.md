### 云犀直播JAVA-SDK, 官方API部分
@author  holger <whjsjq@gmail.com>
@link
@version 1.0

### 1.初始化
```java
   YunxiApi.register(AccessKey, SecretKey);
```

### 2.获取活动列表
```java
   YunxiApi.getActivityList(page,pageSize,timestamp);
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
   YunxiApi.getActivityInfo(activityId,timestamp);
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
   YunxiApi.getActivityLiveStream(activityId,timestamp);
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
 
