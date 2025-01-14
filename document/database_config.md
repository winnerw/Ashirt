# 用户信息

### 个人信息表(account)

| 字段               | 类型         | 可为空 | 描述                       |
| ------------------ | ------------ | ------ | -------------------------- |
| 用户id(**user_id**)     | int(11)      |        | 主键，外键，可与第三方联结 |
| 密码(password)     | varchar (20) |        | 登陆密码                   |
| 昵称(nickname)     | varchar (20) |        | 昵称                       |
| 邮箱(email)        | varchar (20) |        | 用户的账户邮箱             |
| 电话号码(phone_num) | varchar (16)     |        | 用户的电话号码             |
| 头像(head_picture)  | varchar(255)  | √      | 图片的路径信息             |
| 城市(city)         | Varchar(10)  | √      | 居住城市                   |

### 个人设计表(design)

| 字段                 | 类型         | 可为空 | 描述                         |
| -------------------- | ------------ | ------ | ---------------------------- |
| 用户id(**user_id**)       | int(11)      |        | 外键，可与第三方联结   |
| 产品ID(**product_id**)    | int (11)     |        | 主键，外键，标识用户所设计出的衣物 |
| 款式ID(**style_id**)      | int(11)      |        | 外键，区别各用户设计的款式   |
| 是否公布(publish)    | char(1)      |        | 选择是否公布                 |
| 设计图(design_picture) | varchar(255)  |        | 图片的路径信息               |
| 创作时间(design_time) | datetime     |        | 创作完成的时间               |
| 尺寸(size)           | varchar(6)   |        | 用户衣服的尺寸               |
| 衣物面料(material)   | varchar (10) |        | 衣物所选择的面料款式         |
| 设计思路(thought)    | varchar(255) | √      | 用户设计的原因及想法         |
| 价格(price)          | int (5)      |        | 衣服的标价                   |

# 设计

### 款式表 (style)

| 字段                 | 类型        | 可为空 | 描述                       |
| -------------------- | ----------- | ------ | -------------------------- |
| 款式ID(**style_id**)      | int(11)     |        | 主键，区别各用户设计的款式 |
| 文字(style_describe)  | varchar(30) | √      | 款式文字描述               |
| 款式图(style_picture) | varchar(255) |        | 图片的路径信息             |
| 上传时间(upload_time) | datetime    | √      | 款式上传的时间             |
| 价格(price)          | int(5)      |        | 款式预期的售价             |
| 颜色(color)          | varchar(10)    |        | 款式的颜色                 |
| 款式名称(name)          | varchar(10)    |        | 款式的名称                 |

### 图标类别表 (category)

| 字段                  | 类型        | 可为空 | 描述               |
| --------------------- | ----------- | ------ | ------------------ |
| 图标类别(**category_id**) | int(11)     |        | 主键               |
| 图标类别名(name)      | varchar(10) |        | 图标的名字         |
| 图标类别图(category_picture) | varchar(255) |        | 代表图标的路径信息 |

### 图标表(item)

|         字段          |    类型     | 可为空 |      描述      |
| :-------------------: | :---------: | :----: | :------------: |
|    图标ID(**item_id**)    | int(11) |        |      主键      |
| 图标类别(**category_id**)  | int(11) |        |      外键      |
| 图标图片(item_picture) | varchar(255) |        | 图标的路径信息 |

### 用户评论表(comments)

| 字段              | 类型      | 可为空 | 描述                         |
| ----------------- | --------- | ------ | ---------------------------- |
| 评论ID(**comment_id**) | int(11) |  | 主键，区别于每条评论 |
| 用户ID(**user_id**)    | int(11)   |        | 外键，区别于各个用户   |
| 产品ID(**product_id**) | int(11)   |        | 外键，标识用户所设计出的衣物 |
| 发布内容(details) | char(255) |        | 用户对衣物设计的评价         |
| 发布时间(time)    | datetime  | √ | 用户评论发布时间             |
| 所处楼数(floor)   | int(3)    |        | 用户所处评论区的楼数         |

### 平台使用说明表(tutorial)

| 字段                 | 类型         | 可为空 | 描述                         |
| -------------------- | ------------ | ------ | ---------------------------- |
| 教程编号(**tutorial_id**) | int(11)      |        | 主键，使用说明中视频教程编号 |
| 教程文字(detial)     | varchar(255) |        | 教程的文字描述               |
| 教程视频(video)      | varchar(255)  |        | 教程中所使用视频的路径信息   |

### ID format

| ID          | Index |
| ----------- | ----- |
| user_id     | 19... |
| category_id | 18... |
| product_id  | 17... |
| item_id     | 16... |
| style_id    | 15... |
| tutorial_id | 14... |
| comment_id  | 13... |
