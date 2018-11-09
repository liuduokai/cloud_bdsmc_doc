# bdsm os系统数据字典

## 目录

### [1. sys_*数据表](#1)

#### [1.1 sys_dept](#1.1)

#### [1.2 sys_dept_lead](#1.2)

#### [1.3 sys_dept_user](#1.3)

#### [1.4 sys_file](#1.4)

#### [1.5 sys_menu](#1.5)

#### [1.6 sys_role](#1.6)

#### [1.7 sys_role_menu](#1.7)

#### [1.8 sys_role_user](#1.8)

#### [1.9 sys_user](#1.9)

#### [1.10 sys_user_login](#1.10)

## <div id = 1>1. sys_* 数据表</div>

### <div id = 1.1>1.1 sys_dept</div>

#### 说明：系统部门数据表

#### 表中字段
|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|name|部门名称|
|parent_id|上级部门id|
|level|部门级别|
|seq|排序号|
|remark|备注|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.2>1.2 sys_dept_lead</div>

#### 说明：部门领导数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|dept_id|部门名称|
|lead_id|部门领导id|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.3>1.3 sys_dept_user</div>

#### 说明：部门账户数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|dept_id|部门名称|
|user_id|部门账户id|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.4>1.4 sys_file</div>

#### 说明：部门账户数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|dept_id|部门名称|
|user_id|部门账户id|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.5>1.5 sys_menu</div>

#### 说明：系统菜单数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|name|菜单名称|
|path|菜单路径|
|redirect|重定向路径|
|icon|菜单图标|
|hidden||
|cache||
|parent_id|上级菜单id|
|level|菜单等级|
|seq|菜单排序号|
|type|菜单类型|
|remark|备注|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.6>1.6 sys_role</div>

#### 说明：系统规则数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|code||
|name||
|parent_id||
|edit||
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.7>1.7 sys_role_menu</div>

#### 说明：系统规则与菜单映射数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|role_id|规则id|
|menu_id|菜单id|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.8>1.8 sys_role_user</div>

#### 说明：系统规则用户映射数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|role_id|规则id|
|user_id|用户id|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|

### <div id = 1.9>1.9 sys_user</div>

#### 说明：系统用户数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|name|姓名|
|nick_name|昵称，现用作微信通知的备注名|
|sex|性别|
|birthday|生日|
|phone|手机号码|
|mail|邮箱|
|say||
|avatar|用户头像|
|we_chat|微信|
|qq|qq|
|open_we||
|open_qq||
|username|用户名|
|password|密码|
|reset_code|重置后密码|
|parent_id||
|parent_name||
|parent_username||
|level|用户等级|
|status|用户状态|
|remark|备注|
|json_info|json信息|
|operate_ip|操作者ip|
|operate_id|操作者id|
|operate_name|操作者名称|
|operate_time|操作时间|



### <div id = 1.10>1.10 sys_user_login</div>

#### 说明：用户登录日志数据表

#### 表中字段

|字段名|说明|
|:-:|:-:|
|id|主键，数据表中编号|
|user_id|用户id|
|user_name|用户名|
|login_ip|登录ip|
|login_time|登录时间|
|login_address|登录地址|
|login_system|登录系统|
|login_borrow|登录浏览器|
|login_borrow_version|登录浏览器版本|



