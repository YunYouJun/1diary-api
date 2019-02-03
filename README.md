# 1diary-api

Guess [1diary](http://1diary.me) api.

本文档仅为尝试，不代表官方。

## API

### Login

> GET <http://api.1diary.me/login>

**Parameters**

| Argument | Type | Description |
| - | - | - |
| a | String | 账号（手机/邮箱） |
| w | String | 加密后的密码 |
| type | Number | 账号类型(1:日记云, 2:坚果云, 3:box) |

Example

```url
http://api.1diary.me/login?a=me@yunyoujun.cn&w=xxx&type=1
```

**Response**  `Type: json`

| Argument | Type | Description |
| - | - | - |
| code | Number | 状态码 |
| id | String | 用户 ID |
| msg | String | 消息 |
| token | String | 令牌 |

Example:

```json
{
    "code": 200,
    "id": "123456789a",
    "msg": "login success",
    "token": "exampletokenstring"
}
```

### Diary Info

> GET <http://api.1diary.me/get>

**Parameters**

| Argument | Type | Description |
| - | - | - |
| a | String | 账号（手机/邮箱） |
| w | String | 加密后的密码 |
| type | Number | 账号类型（ 1 为永久版） |
| token | String | 令牌 |

**Response**    `Type: json`

| Argument | Type | Description |
| - | - | - |
| code | Number | 状态码 |
| msg | String | 消息 |
| data | Object | 数据 |

data

| Argument | Type | Default | Description |
| - | - | - | - |
| catagory | Array | [] | 种类 |
| createdAt | Datatime | - | 注册时间 |
| dataVersion | Number | - | 数据版本 |
| json | Array[Object] | - | 日记（多篇日记则为数组内多个对象） |
| model | - | "[]" | - |
| objectId | String | - | - |
| orderNum | Number | - | - |
| tag | - | "[]" | - |
| updatedAt | Datatime | - | 更新时间 |
| userId | String | - | - |
| createAt | - | - | - |
| updateAt | - | - | - |
| xdd | String | - | - |

json

| Argument | Type | Default | Description |
| - | - | - | - |
| address | String | - | 地址 |
| city | String | - | 城市 |
| color | String | - | - |
| content | String | - | 日记内容 |
| contentType | Number | - | - |
| createTime | Timestamp | - | 创建时间 |
| dayOfMonth | Number | - | 当月第几日 |
| deleted | Boolean | false | 是否被删除 |
| device | String | - | 设备 |
| historyTime | Number | - | - |
| images | String | - | 图片存储地址（多张图片以 `|` 划分） |
| isForce | Boolean | - | - |
| isHidden | Boolean | - | 是否隐藏 |
| isSynced | Boolean | - | 是否已同步 |
| latitude | float | - | 维度 |
| localImages | String | - | 本地图片 |
| longitude | float | - | 经度 |
| monthOfYear | Number | - | 当年第几月 |
| recordTime | Timestamp | - | 记录时间 |
| tag | - | - | 标签 |
| temperature | String | - | 温度 |
| title | String | - | 标题 |
| type | String | - | 类型 |
| updateTime | Timestamp | - | 更新时间 |
| uuid | String | - | 通用唯一识别码 |
| weather | String | - | 天气 |
| year | Number | - | 年份 |

Example

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "catagory": [],
        "createdAt": "2019-01-17 22:58:17",
        "dataVersion": 0,
        "json": [
            {
                "address": "xx区",
                "city": "xxx市",
                "color": "#F8F8F8",
                "content": "虽说是大寒，但今天阳光不错。",
                "contentType": 0,
                "createTime": 1547970971849,
                "dayOfMonth": 20,
                "deleted": false,
                "device": "MIX 2",
                "historyTime": 0,
                "images": "",
                "isForce": false,
                "isHidden": false,
                "isSynced": false,
                "latitude": 34.471336,
                "localImages": "",
                "longitude": 119.249159,
                "monthOfYear": 1,
                "recordTime": 1547970971849,
                "tag": "",
                "temperature": "5℃",
                "title": "",
                "type": "",
                "updateTime": 1547982039698,
                "uuid": "bd32fecd-00bb-45f8-808a-3865e3359595",
                "weather": "多云",
                "year": 2019
            }
        ],
        "model": "[]",
        "objectId": "",
        "orderNum": 0,
        "tag": "[]",
        "updatedAt": "2019-01-20 19:00:40",
        "userId": "",
        "createAt": "",
        "updateAt": "",
        "xdd": "b10b6a99d1"
    }
}
```