# Bluebell

Bluebell 是一个基于 **Go** 的社区/论坛类 Web 项目示例，包含用户、帖子、社区等基础功能，适合作为 Go Web 后端的学习、实践和二次开发模板。

项目采用典型的分层结构，集成了路由、控制器、配置管理以及前端静态资源，并提供了完整的数据库建表 SQL。

---

##  功能简介

  **用户模块**：用户注册、登录、信息管理
  **社区模块**：社区列表、社区详情
  **帖子模块**：发帖、帖子列表、帖子详情
  **Web 接口**：基于 HTTP API 的后端服务
  **数据库脚本**：提供用户 / 社区 / 帖子相关 SQL
  **前端资源**：已构建好的静态页面资源

---

##  项目结构

```text
bluebell/
├── bin/                 # 构建产物目录
├── conf/                # 配置文件（开发 / 本地）
├── controller/          # 控制器层（HTTP Handler）
├── dao/                 # 数据访问层（如果后续扩展）
├── models/              # 数据模型
├── router/              # 路由定义
├── setting/             # 配置加载与初始化
├── static/              # 前端静态资源（JS / CSS / 图片）
├── templates/           # HTML 模板
├── bluebell_user.sql    # 用户表 SQL
├── bluebell_post.sql    # 帖子表 SQL
├── bluebell_community.sql # 社区表 SQL
├── wait-for.sh          # 启动辅助脚本
└── main.go              # 项目入口（如适用）
```

---

##  技术栈

* **语言**：Go
* **Web 框架**：Gin（或类似轻量 HTTP 框架）
* **配置管理**：YAML
* **数据库**：MySQL（SQL 可直接执行）
* **前端**：已构建的静态资源（Vue / Webpack 构建产物）

---

##  快速开始

### 1️⃣ 初始化数据库

在 MySQL 中依次执行：

```sql
source bluebell_user.sql;
source bluebell_community.sql;
source bluebell_post.sql;
```

### 2️⃣ 修改配置

根据本地环境修改配置文件：

```text
conf/config.yaml
conf/dev.yml
```

主要包括：

* 数据库连接信息
* 服务端口
* 日志配置

### 3️⃣ 启动服务

```bash
go run main.go
```

或使用热加载工具（如 air）：

```bash
air
```

### 4️⃣ 访问应用

```text
http://localhost:8080
```

---

##  适用人群

* Go Web 初学者
* 想了解完整后端项目结构的开发者
* 学习 Gin / REST API / SQL 设计的实践者

---

##  License

本项目仅用于学习与交流，如用于生产环境请自行评估和完善。

---

##  致谢

感谢 Go 社区与相关开源项目的支持。欢迎 Fork、Star 和改进本项目。
