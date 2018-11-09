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

### 各表关联关系

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile userAgent=\&quot;Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36\&quot; version=\&quot;9.4.0\&quot; editor=\&quot;www.draw.io\&quot; type=\&quot;device\&quot;&gt;&lt;diagram id=\&quot;1790329f-1b12-bddd-c060-b77250247113\&quot; name=\&quot;第 1 页\&quot;&gt;5VpLc5swEP41HJsBxPOYpGl76UxncmhyylCjYCYYuUKO7f76SkjiIcHEcXiNk4MDK7GSvm+12l0wwO3m8B1H2/VPFMPMsM34YICvhm2DMKS/THDkAte1uSDBacxFVi24T/9BITSFdJfGsGh1JAhlJN22hSuU53BFWrIIY7Rvd3tGWXvUbZRATXC/ijJd+juNyZpLA9uv5T9gmqzlyJYnFvwnWr0kGO1yMZ5hg+fyjzdvIqlLLLRYRzHaN0TgzgC3GCHCrzaHW5gxaCVs/LlvPa3VvDHMySkPCFpeo2wnll4ci6ddAbGYHzlKTMpVQfacaYCb/Tol8H4brVjrnhoBla3JJqN3Fr0UaiEm8NA7NataMLUjiDaQ4CPtIh8wXQFSZUTOlcsl+5oUS0K5bhAChCwSdpBU2mss6IWAoxsaoEFj2F5GB7h5RnQFTWy8vzskG74UpTVf0w7B9lC30auE/Zf4PmUoSXOpkk6Ga+Wd5gff9mYF37I09EvQaLsKDV0kaa+/IBi9wFuUIUwlOcoh4ybNMkUUZWmS09sVBYUaPLhhkKXUC1yLhk0ax2yYTsDblAyCuWlKjCXqfhfqTgfo9hCg6ybPrBUjisHsBql6A+BMaY5OLzILdZaOvJ8EHq8TnhhuyfKQ8b0pDSfsOEUURGAeX7OYhXmiLCqKdNUGgS4UHx+aN48MPeoY6O0hJQ8CS3Zdt/BhYKwFOgpwdCpoh1ewdeiRCCdQepZueBvouR3gSRmGWUTS1/YkuhAVI/xCaXm4Nnxiiz3PVVjhsxePNSMdTZNiB56paOKL1jSVFFcLP4l1aU0fYl0yW/H82NoU72VWurAFUesrIUZwLrVW8IamAan9jIFJ5R4lvpZ+uIwVlHSkKOd7ULGZpA/t32fmoPuMB1azbTTLbUeVIDx3o5neG5oG3Gh6yFWGW59qozlTbjRXA5wFcRuY7zTEJw/iHOWsmDT6t7vD29IclwGPmq1PC48/oIeeIMaVdC7IQ1eFT7nv1Q19epRr9VjCCB46GPJk7ufdGpF37vRm491xhuJd1TQm73pOe/kns16bA/Z0lTnpphuQs4PnsiF3VFc2JeB6mseOfIraAkqhajDkeXqUON5rET0fk7W+hZZCvSkLfqC7hl7Ck8FI369TwxMooeKk5VCgJ3UaIEtK5rmxz5e4Kx7Qc8Mr5Vg/vUam6HIDR9U1XIgA9Fzy/Tz3FkD7LOCjPCspgbco7n37bOaVokIwXuEb6Jly6fkuOk5R8fVt/TgeLU7Rc+/PV472pgR8iKS395TqS4ftD7zRW9orPTUACXyFllMdW6h4yEDlt8evUW6iY6PblnUo+iccqm8/vNY3VfSCazzbaQ75jniCOkqXRc17WM5uUmewLh1Ug3WWH1y05w4dNZ6dLqN39Iz+4kOTMFQik/Hwprf1V6t8O9RfBoO7/w==&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>
<script type="text/javascript" src="https://www.draw.io/js/viewer.min.js"></script>



