# 简单的招聘网站示例
基于 Flask / Jinja2 / Bootstrap / MySQL 开发，仿照拉勾网的风格，实现了招聘网站的必需功能

## 环境
* Python 3
* MySQL

## 快速开始

#### 1. 安装 Python 依赖
```sh
$ pip3 install -r requirements.txt

PyMySQL

pip uninstall markupsafe
pip install markupsafe==2.0.1

pip uninstall SQLAlchemy
pip install SQLAlchemy==1.3.15

pip uninstall Flask_Migrate
pip install Flask_Migrate==2.5.3

pip install bleach==4.1.0


```

flask_uploads.py

from werkzeug import secure_filename,FileStorage 
to
from werkzeug.utils import secure_filename
from werkzeug.datastructures import FileStorage
```

​```aiignore
D:\Users\HJ\PycharmProjects\job-web-demo\.venv\Lib\site-packages\flask_share\__init__.py

from flask import current_app, Markup ,request, Blueprint, url_for
to
from flask import current_app, request, Blueprint, url_for
from markupsafe import Markup
```

#### 2. 修改配置文件

根据自己情况，修改 `job_web/config.py`

主要是 `SQLALCHEMY_DATABASE_URI` 数据库的链接

#### 3. 创建数据库

根据上面配置中的库名，创建数据库

#### 4. 利用 flask-migrate 建表

命令行终端，先进入项目目录，然后依次执行下列命令：

```sh
$ export FLASK_APP=manage.py
# windows 系统：set FLASK_APP=manage.py

$ flask db init
$ flask db migrate
$ flask db upgrade
```

![image-20250223141105013](docs\image-20250223141105013.png)

![image-20250223141520248](docs\image-20250223141520248.png)

#### 5. 生成测试数据（可选）

可执行 [test_data.py](https://github.com/zkqiang/job-web-demo/blob/master/data/test_data.py) 生成一些随机数据

## 实现功能
* 个人和企业两种角色的注册登录编辑
* 职位和企业的索引页、详情页及搜索功能
* 个人简历上传和投递操作
* 企业对职位的增删改查上下线，及对简历的反馈处理

## TODO
- [ ] 职位和企业的条件筛选
- [ ] 管理员后台和权限功能
- [ ] 简历支持 PDF，并将 PDF 转图片在线浏览
- [ ] 职位和企业该为列表展示
- [ ] 个人对职位收藏

## 运行截图
![pic](docs/1.png '首页')
![pic](docs/2.png '职位详情')
![pic](docs/3.png '企业详情-在招岗位')
![pic](docs/4.png '企业管理-职位管理')
![pic](docs/5.png '个人管理-求职记录')

# Issue
> MySQL GROUP BY 的问题 
> 关闭 ONLY_FULL_GROUP_BY
> https://www.cnblogs.com/Wayou/p/mysql_group_by_issue.html


