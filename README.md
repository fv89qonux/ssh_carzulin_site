## 本项目实现的最终作用是基于SSH汽车出租平台租赁网站平台
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 交易流水管理
 - 利润统计
 - 汽车品牌管理
 - 用户管理
 - 管理员登录
 - 管理员管理
 - 订单管理和审核
 - 车辆管理
### 第2个角色为用户角色，实现了如下功能：
 - 个人中心管理
 - 提交租车订单
 - 查看个人租车记录
 - 查看我的订单
 - 查看所有租车信息
 - 查看汽车详细信息
 - 用户登录页面
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_carzulin_site

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [t_admin](#t_admin) | 管理员表 |
| [t_car](#t_car) |  |
| [t_car_category](#t_car_category) |  |
| [t_order](#t_order) |  |
| [t_rent](#t_rent) |  |
| [t_user](#t_user) | 用户表 |

**表名：** <a id="t_admin">t_admin</a>

**说明：** 管理员表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | adminname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 管理员名称  |
|  3   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  4   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  5   | realname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名字  |

**表名：** <a id="t_car">t_car</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | carImage |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | carNumber |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | carOilType |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | carType |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | dailyPrice |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | distance |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  9   | car_category_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  10   | isDiscount |   int   | 10 |   0    |    N     |  N   |       |   |
|  11   | isRecommend |   int   | 10 |   0    |    N     |  N   |       |   |

**表名：** <a id="t_car_category">t_car_category</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | cname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 分类名称  |
|  3   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |

**表名：** <a id="t_order">t_order</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | code |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  5   | state |   int   | 10 |   0    |    N     |  N   |       | 状态  |
|  6   | totalPrice |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | car_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  8   | rent_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  9   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |
|  10   | isDeal |   int   | 10 |   0    |    N     |  N   |       |   |
|  11   | finishTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_rent">t_rent</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  3   | rentTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  4   | returnTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    |   |
|  5   | car_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  6   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 用户ID  |

**表名：** <a id="t_user">t_user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | answer |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 答案  |
|  3   | email |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮箱  |
|  4   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  5   | loginName |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  7   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 电话  |
|  8   | question |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  9   | realname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名字  |

