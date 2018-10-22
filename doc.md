# 接口目录

1. [login](#1)
2. [logout](#2)
3. [refresh](#3)
4. [me](#4)
5. [updateMe](#5)
6. [pick](#6)
7. [gnss](#7)
8. [Update](#8)
9. [Del](#9)
10. [listPois](#10)
11. [addImage](#11)
12. [addPos](#12)
13. [delPos](#13)
14. [delImage](#14)
15. [listPoses](#15)
16. [assignPoi](#16)
17. [searchPoi](#17)
18. [listDevices](#18)
19. [listDevices3](#19)
20. [listSensors](#20)
21. [poi](#21)
22. [device](#22)

****

# 接口详情

## <div id = 1>1.login</div>

****

### 简介

* 使用账户的用户名和密码请求该接口，该接口会返回用于后续操作验证身份的tokan，该账户的信息以及用户所属项目的信息
  
### 请求

#### 请求地址

cloud.bdsmc.net:8000/login

#### 请求方式

* get
* options
  
#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|email|是|用户名|
|password|是|密码|

#### 请求示例

cloud.bdsmc.net:8000/login?email=xx&password=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "access_token": "xxx",
    "token_type": "xxx",
    "me": {
        "id": xx,
        "email": "xx",
        "name": "xx",
        "phone": "xx",
        "gender": xx,
        "id_number": "xx",
        "home": "xx",
        "project_id": xx,
        "type": xx,
        "created_at": "xx",
        "updated_at": "xx",
        "pro_blo": xx,
        "project": {
            "id": xx,
            "name": "xx",
            "type": xx,
            "created_at": "xx",
            "updated_at": "xx",
            "lt_point": "xx",
            "rd_point": "xx",
            "sate_path": "xx",
            "sate_lvl": "xx",
            "map_path": "xx",
            "map_change_lvl": "xx,18",
            "pro_bord_path": "xx",
            "user_id": xx,
            "center_point": "xx"
        }
    },
    "expires_in": xx
}
```

##### 参数列表

|参数|作用|
|:-:|:-:|
|access_token|进行后续操作验证身份所需要的token|
|token_type|token类型|
|me|用户个人相关信息|
|id|用户id|
|emali|邮箱|
|name|姓名|
|phone|手机|
|gender|性别|
|id_number|身份证号码|
|home|住址|
|project_id|所属项目|
|type|用户类型|
|created_at|创建时间|
|updated_at|更新时间|
|pro_blo|暂无作用|
|project|所属项目信息，内容参见相关接口|
|expires_in|token有效时间|

#### 请求失败

1. 输入密码错误次数过多（超过4次）
2. 输入了错误的用户名和密码

****

## <div i = 2>2.logout</div>

****

### 简介

* 此账户登出，注销此账户的token

### 请求

#### 请求地址

cloud.bdsmc.net:8000/logout

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/logout
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "Successfully logged out"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效

****

## <div id = 3>3.refresh</div>

****

### 简介

* 重置token的有效时间

### 请求

#### 请求地址

cloud.bdsmc.net:8000/refresh

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/refresh

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "access_token": "xx",
    "token_type": "xx",
    "me": {
        "id": xx,
        "email": "xx",
        "name": "xx",
        "phone": "xx",
        "gender": xx,
        "id_number": "xx",
        "home": "xx",
        "project_id": xx,
        "type": xx,
        "created_at": "xx",
        "updated_at": "xx",
        "pro_blo": xx,
        "project": {
            "id": xx,
            "name": "xx",
            "type": xx,
            "created_at": "xx",
            "updated_at": "xx",
            "lt_point": "xx",
            "rd_point": "xx",
            "sate_path": "xx",
            "sate_lvl": "xx",
            "map_path": "xx",
            "map_change_lvl": "xx",
            "pro_bord_path": "xx",
            "user_id": xx,
            "center_point": "xx"
        }
    },
    "expires_in": xx
}
```

##### 参数列表

* 与login接口返回参数一致

#### 请求失败

* token值无效

****

## <div id = 4>4.me</div>

****

### 简介

* 获取当前登陆用户信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/me

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/me

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": xx,
    "email": "xx",
    "name": "xx",
    "phone": "xx",
    "gender": xx,
    "id_number": "xx",
    "home": "xx",
    "project_id": xx,
    "type": xx,
    "created_at": "xx",
    "updated_at": "xx",
    "pro_blo": xx
}
```

##### 参数列表

* 与login接口返回参数一致

#### 请求失败

* token值无效

***

## <div id = 5>5.updateMe</div>

****

### 简介

* 更新当前登录用户的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/updateMe

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|name|否|姓名|
|phone|否|手机|
|gender|否|性别|
|home|否|住址|
|id_number|否|身份证号|

#### 请求示例

cloud.bdsmc.net:8000/updateMe?name='xx'&phone='123456'

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效

***

## <div id = 6>6.pick</div>

****

### 简介

* 将一条数据插入到传感器数据表（displacementsensor1）中，并判断数据是否超过预警上下限，若超过预警上下限则在数据库警报表中插入一条新信息并通过mqtt进行通知

### 请求

#### 请求地址

cloud.bdsmc.net:8000/pick

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|传感器id|
|time|是|数据时间|
|value|是|传感器数据|

#### 请求示例

cloud.bdsmc.net:8000/pick?id=xx&time=xx&value=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id在sensors表中不存在

***

## <div id = 7>7.gnss</div>

****

### 简介

* 给设备或监测点添加gnss信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/gnss

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|type|是|添加数据目标的类型，type=1时向设备添加信息，type=2时候向监测点添加信息|
|lat|是|经度|
|lng|是|纬度|
|height|是|高程|

#### 请求示例

cloud.bdsmc.net:8000/pick?type=x&lat=xx&lng=xx&&height=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "update_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* 设备或监测点不存在

***

## <div id = 8>8.Update</div>

****

### 简介

* 作用未知，新建一个user对象，若请求中有用户相关信息，则将新对象的相应值赋值，再将当前用户的id赋给此对象中的user_id字段
* ps:此接口中存在问题，插入新对象时插入了不存在的的字段，因此无法正常运行

### 请求

#### 请求地址

cloud.bdsmc.net:8000/Update

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|phone|否|手机|
|name|否|姓名|
|id_number|否|身份证号|
|home|否|住址|
|gende|否|性别|

#### 请求示例

cloud.bdsmc.net:8000/Update?phone=xx&name=xx

****

### 返回

#### 请求成功

无法请求成功

##### 返回示例

无

##### 参数列表

* 无

#### 请求失败

插入了不存在的数据项，任何情况下都会请求失败

***

## <div id = 9>9.Del</div>

****

### 简介

* 接口实现不存在，仅在路由表中有相关字段

***

## <div id = 10>10.listPois</div>

****

### 简介

* 显示登录账户所属的项目下的所有监测点信息，同时返回监测点中设备与照片信息，若登录账户为管理员账户，则列出所有监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listPois

#### 请求方式

* get
* options

#### 参数

* 无

#### 请求示例

cloud.bdsmc.net:8000/listPois

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": xx,
        "id2": xx,
        "project_id": xx,
        "user_id": xx,
        "lngflag": xx,
        "lng": xx,
        "latflag": xx,
        "lat": xx,
        "altitude": xx,
        "init": xx,
        "name": "xx",
        "location": "xx",
        "props": "",
        "created_at": "xx",
        "updated_at": "xx",
        "pinyin": "xx",
        "devices2": [],
        "photos": [],
        "devices": []
    },
    ......
]
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|id|监测点id|
|id2|监测点id2|
|project_id|监测点所属项目id|
|user_id|监测点负责人用户id|
|lngflag|经度标志|
|lng|经度|
|latflag|纬度标志|
|lat|纬度|
|altitude|高度|
|init|未知参数|
|name|监测点名称|
|location|监测点|
|props|未知参数|
|created_at/updated_at|创建/更新时间|
|pinyin|监测点拼音|
|decives2|监测点设备2|
|photos|监测点图像|
|device|监测点设备|


#### 请求失败

* token值无效
* 用户的projectid字段出现问题

***

## <div id = 11>11.addImage</div>

****

### 简介

* 向相应的项目添加图片，可以向项目添加项目照片和项目的信息图片

### 请求

#### 请求地址

cloud.bdsmc.net:8000/addImage

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|poi_id|是|监测点id|
|image|否|项目图片|
|info_image|否|项目信息图片|

#### 请求示例

cloud.bdsmc.net:8000/addImage?poi_id=xx
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "poi_id": "200",
    "path": "file/5bcd3680d083b_u=195531778,3494036849&fm=26&gp=0.jpg",
    "info_path": null,
    "updated_at": "2018-10-22 10:31:28",
    "created_at": "2018-10-22 10:31:28",
    "id": 85
}
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|poi_id|监测点id|
|path|监测点图片路径|
|infopath|监测点信息图片路径|
|updated_at/created_at|创建/更新时间|
|id|图片id|

#### 请求失败

* token值无效
* poi_id参数错误

***

## <div id = 12>11.addPos</div>

****

### 简介

* 向photopostions表中添加信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/addPos

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|photo_id|是|照片id|
|device_id|是|设备id|
|x|是|在图片中坐标的x值|
|y|是|在图片中坐标的y值|

#### 请求示例

cloud.bdsmc.net:8000/addPos?photo_id=xx&device_id=xx&x=xx&y=xx
****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "photo_id": "x",
    "device_id": "xx",
    "x": "x",
    "y": "x",
    "updated_at": "x",
    "created_at": "x",
    "id": x
}
```

##### 参数列表

|名称|说明|
|:-:|:-:|
|photo_id|照片id|
|device_id|设备id|
|x|是|在图片中坐标的x值|
|y|是|在图片中坐标的y值|
|updated_at/created_at|创建/更新时间|
|id|记录表中的id|
#### 请求失败

* token值无效
* photo_id或device_id错误

****

## <div id = 13>13.delPos</div>

****

### 简介

* 删除photopostions表中信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/delPos

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|photopostions表中记录id|

#### 请求示例

cloud.bdsmc.net:8000/delPos?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "del_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id错误

****

## <div id = 14>14.delImage</div>

****

### 简介

* 删除图片

### 请求

#### 请求地址

cloud.bdsmc.net:8000/delImage

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|所需删除图片的id|
|del_flag|否|若存在该项字段说明只删除图片表中的一项信息，若值为1删除项目图片，若为其他值删除项目描述图片

#### 请求示例

cloud.bdsmc.net:8000/delImage?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "del_ok"
}
```

##### 参数列表

* 无

#### 请求失败

* token值无效
* id错误

****

## <div id = 15>15.listPoses</div>

****

### 简介

* 查询一张图片中的所有描述信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listPoses

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|所需查询图片的id|

#### 请求示例

cloud.bdsmc.net:8000/listPoses?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": xx,
    "poi_id": xx,
    "path": "xx",
    "created_at": "xx",
    "updated_at": "xx",
    "info_path": "xx",
    "devices": [
        {
            "id": xx,
            "photo_id": xx,
            "device_id": xx,
            "x": xx,
            "y": xx,
            "created_at": "xxx",
            "updated_at": "xxx",
            "device": null
        },
        ......
    ]
    "photopostions": [
        {
            "id": xx,
            "photo_id": xx,
            "device_id": xx,
            "x": xx,
            "y": xx,
            "created_at": "xx",
            "updated_at": "xx",
            "device": xx
        },
        ......
    ]
}

```

##### 参数列表

|名称|说明|
|:-:|:-:|
|id|查询图片的id|
|poi_id|所属监测点的id|
|path|图片路径
|created_at/updated_at|创建/更新时间|
|info_path|项目信息图片路径|
|devices|监测点图片中的设备信息|
|photopostions|图片中描述信息的参数|

#### 请求失败

* token值无效
* id错误

****

## <div id = 16>16.assignPoi</div>

****

### 简介

* 将一个监测点分配给一个用户，仅有管理员账户可以调用此接口

### 请求

#### 请求地址

cloud.bdsmc.net:8000/assignPoi

#### 请求方式

* post
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|poiId|是|监测点id|
|id|是|管理该监测点的账户id|

#### 请求示例

cloud.bdsmc.net:8000/listPoses?poiId=xx&id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "message": "assign_ok"
}

```

##### 参数列表

* 无
#### 请求失败

* token值无效
* 调用该接口用户不是管理员账户
* poiId或id存在问题

****

## <div id = 17>17.searchPoi</div>

****

### 简介

* 使用监测点名称或设备id搜索监测点

### 请求

#### 请求地址

cloud.bdsmc.net:8000/searchPoi

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|$q|是|搜索参数|

#### 请求示例

cloud.bdsmc.net:8000/searchPoi/xxxxxxx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": xx,
        "id2": xx,
        "project_id": xx,
        "user_id": xx,
        "lngflag": xx,
        "lng": xx,
        "latflag": xx,
        "lat": xx,
        "altitude": xx,
        "init": xx,
        "name": "xx",
        "location": "xx",
        "props": "xx",
        "created_at": "xx",
        "updated_at": "xx",
        "pinyin": "xx",
        "photos": [xx],
        "devices2": [
            {
                "id": xx,
                "id2": "xx",
                "poi_id": xx,
                "latflag": xx,
                "lat": xx,
                "lngflag": xx,
                "lng": xx,
                "altitude": xx,
                "init": xx,
                "name": "xx",
                "type": xx,
                "dimension": "xx",
                "unit": "xx",
                "color":"xx",
                "online": xx,
                "created_at": "xx",
                "updated_at": "xx",
                "report_cycle": xx,
                "communication_way": xx,
                "version_number": xx,
                "company_name_header": xx,
                "mac": "xx"
            },
            ......
        ],
        "devices": [
            {
                "id": xx,
                "id2": "xx",
                "poi_id": xx,
                "latflag": xx,
                "lat": xx,
                "lngflag": xx,
                "lng": xx,
                "altitude": xx,
                "init": xx,
                "name": "xx",
                "type": xx,
                "dimension": "xx",
                "unit": "xx",
                "color": "xx",
                "online": xx,
                "created_at": "xx",
                "updated_at": "xx",
                "report_cycle": xx,
                "communication_way": xx,
                "version_number": xx,
                "company_name_header": x,
                "mac": "xx"
            },
            ......
         ]
    }

```

##### 参数列表

参数与[listPois](#10)接口中返回参数一致

#### 请求失败

* token值无效
* 当前用户不属于相关项目
* 查询参数出现问题

****

## <div id = 18>18.listDevices</div>

****

### 简介

* 列出监测点下所有设备的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listDevices

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/listDevices?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": xx,
        "id2": "xx",
        "poi_id": xx,
        "latflag": xx,
        "lat": xx,
        "lngflag": xx,
        "lng": xx,
        "altitude": xx,
        "init": xx,
        "name": "xx",
        "type": xx,
        "dimension": "xx",
        "dimension": "xx",
        "color": "xx",
        "online": 0,
        "created_at": "xx",
        "updated_at": "xx",
        "report_cycle": xx,
        "communication_way": xx,
        "version_number": xx,
        "company_name_header": xx,
        "mac": "xx"
    },
    ......
]

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|设备id|
|id2|设备id2|
|poi_id|监测点id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|设备名称|
|type|设备类型|
|dimension|范围|
|color|颜色|
|online|在线|
|created_at/updated_at|创建/更新时间|
|report_cycle|报告周期|
|communication_way|通信方式|
|version_number|版本号|
|company_name_header|公司名称头|
|mac|设备mac|

#### 请求失败

* token值无效
* 调用该接口用户不属于该项目或者不是管理员账户

****

## <div id = 19>19.listDevices3</div>

****

### 简介

* 将用户所属的监测点的设备信息，按分页参数返回

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listDevices3

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|ps|是|每页数据条数|
|pn|页码|

#### 请求示例

cloud.bdsmc.net:8000/listDevices3?ps=xx&pn=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "count": 46,
    "result": [
        {
            "id": 612,
            "id2": "844424933539840",
            "poi_id": 176,
            "latflag": 0,
            "lat": 28.726615,
            "lngflag": 0,
            "lng": 111.623234,
            "altitude": 56.654451,
            "init": 0,
            "name": "0",
            "type": 0,
            "dimension": "0",
            "unit": "0",
            "color": "0",
            "online": 0,
            "created_at": "2018-09-13 10:53:44",
            "updated_at": "2018-09-13 10:54:36",
            "deleted_at": "2018-09-13 10:54:36",
            "report_cycle": null,
            "communication_way": null,
            "version_number": null,
            "company_name_header": "BDWX",
            "mac": "000300000034",
            "pname": "鼎城区花岩溪乡党家庵村滑坡",
            "poi_location": "鼎城区花岩溪乡党家庵村滑坡"
        },
        ......
    ]
}

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|count|符合条件的内容总条数|
|result|查询得到的监测点信息|

#### 请求失败

* token值无效
* 用户不是监测点的负责人或者管理员

****

## <div id = 20>20.listSensors</div>

****

### 简介

* 将用户所属的监测点的设备信息，按分页参数返回

### 请求

#### 请求地址

cloud.bdsmc.net:8000/listSensors

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|设备id|

#### 请求示例

cloud.bdsmc.net:8000/listSensors?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
[
    {
        "id": 149,
        "id2": "1129215706660872",
        "device_id": 165,
        "lng": 0,
        "lat": 0,
        "name": "小时雨量",
        "type": 0,
        "dimension": "",
        "unit": "ml",
        "min": -100,
        "max": 100,
        "up1": 80,
        "down1": 70,
        "up2": 60,
        "down2": 50,
        "value": 100,
        "color": "",
        "created_at": "2018-05-31 16:27:19",
        "updated_at": "2018-05-31 16:27:19",
        "deleted_at": null,
        "seq": 1
    },
    ......
]

```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|传感器id|
|id2|传感器id2|
|device_id|设备id|
|lng|经度|
|lat|纬度|
|name|名称|
|type|类型|
|dimension|范围|
|unit|单位|
|min|最小值|
|max|最大值|
|up1|一级预警上限|
|down1|一级预警下线|
|up2|二级预警上限|
|down2|二级预警下线|
|value|数值|
|color|颜色|
|created_at/updated_at/deleted_at|增删改时间|
|seq|排序号|


#### 请求失败

* token值无效
* 设备id出现错误

****

## <div id = 21>21.poi</div>

****

### 简介

* 根据id返回相应监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/poi

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/poi?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 85,
    "id2": 0,
    "project_id": 12,
    "user_id": 20,
    "lngflag": 0,
    "lng": 112.708638,
    "latflag": 0,
    "lat": 27.979172,
    "altitude": 0,
    "init": 0,
    "name": "nx21",
    "location": "道林镇靳水村季鱼塘上游组（滑坡）",
    "props": "",
    "created_at": "2018-09-13 11:49:41",
    "updated_at": "2018-09-13 11:49:41"
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|监测点id|
|id2|监测点id2|
|project_id|项目id|
|user_id|用户id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|监测点名称|
|location|监测点位置|
|props|参数|
|created_at/updated_at|增改时间|



#### 请求失败

* token值无效
* 监测点id出现问题
* 用户不属于此监测点项目或管理员

****

## <div id = 22>22.poi</div>

****

### 简介

* 根据id返回相应监测点的信息

### 请求

#### 请求地址

cloud.bdsmc.net:8000/poi

#### 请求方式

* get
* options

#### 参数

|参数名|是否必填|说明|
|:-:|:-:|:-:|
|id|是|监测点id|

#### 请求示例

cloud.bdsmc.net:8000/poi?id=xx

****

### 返回

#### 请求成功

##### 返回示例

```json
{
    "id": 85,
    "id2": 0,
    "project_id": 12,
    "user_id": 20,
    "lngflag": 0,
    "lng": 112.708638,
    "latflag": 0,
    "lat": 27.979172,
    "altitude": 0,
    "init": 0,
    "name": "nx21",
    "location": "道林镇靳水村季鱼塘上游组（滑坡）",
    "props": "",
    "created_at": "2018-09-13 11:49:41",
    "updated_at": "2018-09-13 11:49:41"
}
```

##### 参数列表

|参数|说明|
|:-:|:-:|
|id|监测点id|
|id2|监测点id2|
|project_id|项目id|
|user_id|用户id|
|latflag|经度标志|
|lat|经度|
|lngflag|纬度标志|
|lng|纬度|
|altitude|高程|
|init|初始化|
|name|监测点名称|
|location|监测点位置|
|props|参数|
|created_at/updated_at|增改时间|



#### 请求失败

* token值无效
* 监测点id出现问题
* 用户不属于此监测点项目或管理员

****