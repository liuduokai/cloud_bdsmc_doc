# bdsm os系统数据字典

## 目录

### [1. sys_*数据表](#1)

#### [1.1 sys_dept](#1.1)

#### [1.2 sys_dept_lead](#1.1)

#### [1.3 sys_dept_user](#1.1)

#### [1.4 sys_file](#1.1)

#### [1.5 sys_menu](#1.1)

#### [1.6 sys_role](#1.1)

#### [1.7 sys_role_menu](#1.1)

#### [1.8 sys_role_user](#1.1)

#### [1.9 sys_user](#1.1)

#### [1.10 sys_user_login](#1.1)

## <div id = 1>1. sys_*数据表</div>

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


