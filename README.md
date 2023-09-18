# 框架介绍

## 开发步骤

### 环境准备

- JDK >= 1.8 (推荐1.8版本)
- Mysql >= 5.7.0 (推荐5.7版本)
- Maven >= 3.0

### 必要配置

修改数据库连接，编辑 `resources` 目录下的 `application-druid.yml`

```yaml
# 数据源配置
spring:
    datasource:
        type: com.alibaba.druid.pool.DruidDataSource
        driverClassName: com.mysql.cj.jdbc.Driver
        druid:
            # 主库数据源
            master:
                url: 数据库地址
                username: 数据库账号
                password: 数据库密码
```

修改服务器配置，编辑resources目录下的application.yml

```yaml
# 开发环境配置
server:
  # 服务器的HTTP端口，默认为80
  port: 端口
  servlet:
    # 应用的访问路径
    context-path: /应用路径
```

### 启动服务

- 在 IDEA 中导入项目
- 等待自动的下载 Maven 依赖
- 创建数据库 `dj` 并导入脚本 `dj.sql`
- 打开项目，运行 `com.ruoyi.RuoYiApplication.java`
- 进入 127.0.0.1 访问, (默认账号/密码 admin/admin123)

## 部署系统

> 打包工程文件

在ruoyi项目的bin目录下执行 `package.bat` 打包Web工程，生成war/jar包文件。
然后会在项目下生成target文件夹包含war或jar

> 部署工程文件

1. jar 部署: `java –jar ruoyi.jar` 或者执行脚本：`ruoyi/bin/run.bat`
2. war 部署: `ruoyi/pom.xml` 中的packaging修改为war，放入tomcat服务器webapps
