# 1.修改项目配置文件 application.yml
   active: docker

# 2.先进JAVA项目根路径 maven打包
   mvn clean package


# 3.构建镜像__容器组（当你改变本地代码，也可重新构建镜像）
   docker-compose build

# 4.配置host

   # jeecgboot
   127.0.0.1   jeecg-boot-redis
   127.0.0.1   jeecg-boot-mysql
   127.0.0.1   jeecg-boot-system

# 5.启动镜像__容器组（也可取代运行中的镜像）
   docker-compose up -d

docker-compose logs -f

jeecg-boot-system    | 2021-03-16 11:48:57.583 [main] WARN  o.s.b.w.s.c.AnnotationConfigServletWebServerApplicationContext:559 - Exception encountered during context initialization - cancelling refresh attempt: org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'sysMessageTemplateServiceImpl': Unsatisfied dependency expressed through field 'baseMapper'; nested exception is org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'sysMessageTemplateMapper' defined in URL [jar:file:/jeecg-boot/jeecg-boot-module-system-2.4.2.jar!/BOOT-INF/classes!/org/jeecg/modules/message/mapper/SysMessageTemplateMapper.class]: Unsatisfied dependency expressed through bean property 'sqlSessionFactory'; nested exception is org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'sqlSessionFactory' defined in class path resource [com/baomidou/mybatisplus/autoconfigure/MybatisPlusAutoConfiguration.class]: Unsatisfied dependency expressed through method 'sqlSessionFactory' parameter 0; nested exception is org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'dataSource' defined in class path resource [com/alibaba/druid/spring/boot/autoconfigure/DruidDataSourceAutoConfigure.class]: Invocation of init method failed; nested exception is org.springframework.boot.autoconfigure.jdbc.DataSourceProperties$DataSourceBeanCreationException: Failed to determine a suitable driver class
jeecg-boot-system    | 2021-03-16 11:48:57.676 [main] INFO  org.apache.catalina.core.StandardService:173 - Stopping service [Tomcat]
jeecg-boot-system    | 2021-03-16 11:48:57.798 [main] INFO  o.s.b.a.l.ConditionEvaluationReportLoggingListener:136 -
jeecg-boot-system    |
jeecg-boot-system    | Error starting ApplicationContext. To display the conditions report re-run your application with 'debug' enabled.
jeecg-boot-system    | 2021-03-16 11:48:57.801 [main] ERROR o.s.b.diagnostics.LoggingFailureAnalysisReporter:40 -
jeecg-boot-system    |
jeecg-boot-system    | ***************************
jeecg-boot-system    | APPLICATION FAILED TO START
jeecg-boot-system    | ***************************
jeecg-boot-system    |
jeecg-boot-system    | Description:
jeecg-boot-system    |
jeecg-boot-system    | Failed to configure a DataSource: 'url' attribute is not specified and no embedded datasource could be configured.
jeecg-boot-system    |
jeecg-boot-system    | Reason: Failed to determine a suitable driver class
jeecg-boot-system    |
jeecg-boot-system    |
jeecg-boot-system    | Action:
jeecg-boot-system    |
jeecg-boot-system    | Consider the following:
jeecg-boot-system    |  If you want an embedded database (H2, HSQL or Derby), please put it on the classpath.
jeecg-boot-system    |  If you have database settings to be loaded from a particular profile you may need to activate it (no profiles are currently active).
jeecg-boot-system    |
jeecg-boot-system exited with code 1