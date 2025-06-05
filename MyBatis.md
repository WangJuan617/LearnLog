JavaSE -> JavaWeb -> SSM -> 基于SSM的项目 ->Java高级 ->基于微服务的项目



SSM:spring,springmvc,mybatis

SSM:spring,springmvc,mybatis.

![屏幕截图 2025-05-15 212343](E:\githubcode\LearnLog\MyBatis.assets\E%5Cgithubcode%5CLearnLog%5CMyBatisimages%5C%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202025-05-15%20212343.png)

mybatis和JDBC的区别：框架，比自己封装的工具类更全面些。

是一个基于java的持久层框架。

SQLmaps数据库的数据和java数据的一个映射关系。封装过程。

---



> **持久化层技术**是计算机软件开发中用于处理数据持久化的技术体系，主要解决数据在应用程序与数据库（或其他持久化存储介质）之间的交互问题。

> - **持久化（Persistence）**：指将数据从内存（如应用程序运行时的数据）保存到**持久化存储介质**（如数据库、文件系统、云存储等），确保数据在程序关闭或系统重启后不会丢失。
> - **持久化层（Persistence Layer）**：是软件架构中的一个**逻辑分层**，位于业务逻辑层（应用层）与底层数据源之间，负责实现数据的**增、删、改、查（CRUD）操作**，以及对象与数据存储格式的转换。
>
> **2. 非关系型数据库（NoSQL）持久化技术**
>
> 适用于非结构化或半结构化数据（如 JSON、键值对），支持高并发和水平扩展。
>
> - 键值存储：
>   - **Redis**：内存型键值数据库，支持持久化（RDB/AOF），常用于缓存、计数器等场景。
> - 文档存储：
>   - **MongoDB**：基于文档（BSON 格式）的数据库，提供丰富的查询功能，适合海量数据存储。
> - 列存储：
>   - **Cassandra**：分布式列存储数据库，适合高写入吞吐量的场景（如日志、实时数据）。
>
> **3. 其他持久化技术**
>
> - 文件存储：
>   - 通过文件系统（如本地文件、HDFS）存储数据，适用于日志记录、大数据批处理（如 Apache Hadoop）。
> - 对象存储：
>   - 云服务中的对象存储（如 AWS S3、阿里云 OSS），用于存储非结构化文件（图片、视频等），支持高可用性和海量存储。
> - 搜索引擎与数据仓库：
>   - **Elasticsearch**：基于 Lucene 的搜索和分析引擎，支持实时数据存储与复杂检索。
>   - **Apache Hive**：构建在 Hadoop 上的数据仓库，用于处理大规模结构化数据，支持 SQL-like 查询（HiveQL）。
>
> **四、持久化层技术的选择原则**
>
> 1. 数据结构与业务需求
>    - 结构化数据、强事务性场景：优先选关系型数据库 + ORM 框架（如 Hibernate、MyBatis）。
>    - 非结构化数据、高并发读写：选 NoSQL 数据库（如 MongoDB、Redis）。
> 2. 性能与扩展性
>    - 单机应用或中小规模数据：传统关系型数据库即可。
>    - 分布式、海量数据场景：需结合分布式数据库（如 MySQL 集群）或 NoSQL 技术。
> 3. 开发效率与学习成本
>    - 快速开发：ORM 框架（如 Hibernate）可减少代码量，但需学习框架特性。
>    - 高性能优化：手动编写 SQL（如 MyBatis）或直接使用 JDBC/[ADO.NET](https://ado.net/)，灵活性更高。
> 4. 技术栈兼容性
>    - Java 生态：常用 Hibernate、MyBatis、Spring Data JPA。
>    - Python 生态：常用 SQLAlchemy、Django ORM。
>    - 云原生场景：优先考虑云厂商提供的数据库服务（如 AWS RDS、Google Cloud Spanner）。
>
> **五、总结**
>
> 持久化层技术是软件架构的核心组成部分，其目标是**高效、可靠地管理数据存储与访问**。选择合适的技术需综合考虑数据类型、业务场景、性能需求及团队技术栈。随着云计算和大数据的发展，现代持久化层往往采用**混合架构**（如关系型数据库 + NoSQL + 缓存），以满足复杂业务的多样化需求。

# Mybatis特性

MyBatis特性 
1） MyBatis 是支持定制化 SQL、存储过程以及高级映射的优秀的持久层框架
2） MyBatis 避免了几乎所有的 JDBC 代码和手动设置参数以及获取结果集
3） MyBatis可以使用简单的XML或注解用于配置和原始映射，将接口和Java的POJO（Plain Old Java Objects，普通的Java对象）映射成数据库中的记录
4） MyBatis 是一个 半自动的ORM（Object Relation Mapping）框架





# 速成：

![1747395432930](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747395432930.png)

表现层：页面展示的

业务层：逻辑处理的

持久层：对数据进行持久化的

---

![1747395677567](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747395677567.png)

硬编码：字符串信息有可能会变动，维护性差一些。



Mybatis简化：硬编码--->配置文件；操作繁琐---->自动完成

![1747395836685](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747395836685.png)

步骤：查询user表中所有数据

1. 创建user表，添加数据
2. 创建模块，导入坐标
3. 编写Mybatis核心配置文件 -->  替换连接信息，解决硬件编码问题
4. 编写SQL映射文件  --> 统一管理sql语句，解决硬编码问题
5. 编码：

                    1. 定义POJO类
                    2. 加载核心配置文件，获取 sqlSessionFactory对象
                    3. 获取SqlSession对象，执行sql语句
                    4. 释放资源

mybatis.org/mybatis-3/zh/getting-started.html

## 详细：

2. **创建模块**，导入坐标---->**加入mybatis依赖**，mysql驱动，单元测试依赖，日志依赖。

3. 编写Mybatis核心配置文件---->**创建名为mybatis-config.xml文件**，从官网粘贴详细内容

> 每个基于 MyBatis 的应用都是以一个 SqlSessionFactory 的实例为核心的。SqlSessionFactory 的实例可以通过 SqlSessionFactoryBuilder 获得。而 SqlSessionFactoryBuilder 则可以从 XML 配置文件或一个预先配置的 Configuration 实例来构建出 SqlSessionFactory 实例。

> XML 配置文件中包含了对 MyBatis 系统的核心设置，包括获取数据库连接实例的数据源（DataSource）以及决定事务作用域和控制方式的事务管理器（TransactionManager）

> environment 元素体中包含了事务管理和连接池的配置。mappers 元素则包含了一组映射器（mapper），这些映射器的 XML 映射文件包含了 SQL 代码和映射定义信息。

4. 编写SQL映射文件 ------->

   > mappers 元素则包含了一组映射器（mapper），这些映射器的 XML 映射文件包含了 SQL 代码和映射定义信息。

创建xxmapper.xml映射文件，-------xx表名。粘贴网页上的xml映射语句。

```xml
<!--
	namespace：名称空间
-->
<mapper namespace="test">
	<select id="selectAll" resultType="User">
    	selet * from Blog where id =#{}
    </select>
</mapper>
```

**id:sql语句的唯一标识。resultType：对应的返回结果的一个类型。：类的路径**

5. 定义POJO类--------->java对应的类。
6. 在mybatis-config.xml文件中加载sql映射文件。

```xml
<mappers>
    <!--加载sql映射文件-->
    //这里写路径。
    <mapper resource="xxmapper.xml"/>
</mappers>
```

7. 写一个main类demo--------官网中复制代码：从xml中构建sqlSessionFactory

 

```java
//1.加载mybatis的核心配置文件，获取sqlSessionFactory
String resource = "mybatis-config.xml";-----相对路径
InputStream inputStream = Resources。getResourceAsStream（reaource）；
sqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
```

```java
//2. 获取SqlSession对象，用它来执行sql
        SqlSession sqlSession = sqlSessionFactory.openSession();
```

```java
 //3. 执行sql-----------传入sql语句唯一标识，前面要跟名称空间，将来有很多mappper.xml文件。名称空间就可以很好地区分。
        List<User> users = sqlSession.selectList("test.selectAll");
        System.out.println(users);
```

```java
 //4. 释放资源
        sqlSession.close();
```



# Mapper代理开发



目的：解决原生方式中的硬编码

简化后期执行sql

![1747451734624](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747451734624.png)

![1747452109792](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747452109792.png)

## 详细：

1. 将Mapper接口和SQL映射文件放置在同一目录下。

**资源下写分层包，写成/------------com/wangjuan/mapper。不然不会分层。**

2. 把名称空间更改了，参数和返回值类型一致：

```xml
<mapper namespace="test">
	<select id="selectAll" resultType="com.itheima.pojo.User">
	select *
	from tb_user;
	</select>
</mapper>
```

```xml
接口的权限类名
resultType:返回值
接口中一定有一个叫selectAll的方法，返回user
List<User> selectAll();
    
    
<mapper namespace="com.itheima.mapper.UserMapper">
	<select id="selectAll" resultType="com.itheima.pojo.User">
        明确查出来的是一个集合
	select *
	from tb_user;
	</select>
</mapper>
```

3. **在mapper接口中定义方法，方法名就是sql映射文件中的sql语句的id。并保持参数类型和返回值一样。**

   ```java
   要返回集合，返回的就是一个一个的User对象。因为查询的不止一个
   Public interface UserMapper{
       List<User> selectAll();
   }
   ```

4. 在main方法类中：

   ```java
    //2. 获取SqlSession对象，用它来执行sql
           SqlSession sqlSession = sqlSessionFactory.openSession();
   //3. 执行sql
   //List<User> users = sqlSession.selectList("test.selectAll");
   //3.1 获取UserMapper接口的代理对象
   UserMapper userMapper = sqlSession.getMapper(UserMapper.class);
   List<User> users = userMapper.selectAll();
   
   SYstem.out.println(users);
   ```

**逻辑：倒着推。**

---



# Mybatis 核心配置文件

![1747460089206](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747460089206.png)

mybatis-config.xml

- environments（环境配置）：<!--配置数据库连接环境信息，可以配置多个environment，通过default属性切换不同的environment。-->
  - environment（环境变量）<!--可以多配几个不同的数据库，只需要切换environments的default中的内容就行-->
    - transactionManager（事务管理器）<!--被springboot接管-->
    - dataSource（数据源）<!--数据库连接池--><!--也被springboot接管-->



typeAiases别名：最方便的是包扫描，不用在意resultType的大小写。

```java
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>

    <typeAliases>
        <package name="com.itheima.pojo"/>
    </typeAliases>
    
    <!--
    environments：配置数据库连接环境信息。可以配置多个environment，通过default属性切换不同的environment
    -->
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="1234"/>
            </dataSource>
        </environment>

        <environment id="test">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="0061700"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!--加载sql映射文件-->
       <!-- <mapper resource="com/itheima/mapper/UserMapper.xml"/>-->

        <!--Mapper代理方式-->
        <package name="com.itheima.mapper"/>

    </mappers>
```

# 配置文件增删改查

将sql语句写到配置文件中

要完成的功能列表清单：

1. 查询

   查询所有数据

   查看详情

   条件查询

2. 添加

3. 修改

   修改全部字段

   修改动态字段

4. 删除

   删除一个

   批量删除



**MyBatis插件：是一款基于IDEA的快速开发插件，为效率而生。**

> **主要功能：XML和接口方法相互跳转**

> **根据接口方法生成statement**



---

## 1. 查询所有数据:

![1747463286171](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747463286171.png)

能分析出来三件事：1，sql语句咋写。2，完成这个功能要不要参数。3，完成之后返回什么样的结果。



Mybatis完成操作需要几步？三步：编写接口方法   - >  编写sql -->执行方法



**数据库表的字段名称 和 实体类的属性名称 不一样，则不能自动封装数据**                

   * 起别名：对不一样的列名起别名，让别名和实体类的属性名一样  

        *缺点：每次查询都要定义一次别名 

     ​               *sql片段：                                                                           

     ​                    *缺点：不灵活

   *   resultMap：映射                                  

     1. 定义<resultMap>标签
     2. 在<select>标签中，使用 resultMap属性替换 resultType属性。

```xml
<select id="selectAll" resultType="com.wangjuan.pojo.Brand">
    select *
    from tb_brand;
</select>
```

<!--通过起别名，和实体类属性一样-->

```xml
  <select id="selectAll" resultType="com.wangjuan.pojo.Brand">
        select id,brand_name as brandName,company_name as companyName,ordered,description,status
        from tb_brand;
    </select>
```

<!--sql片段-->

```xml
    <sql id="brand_column">
        select id,brand_name as brandName,company_name as companyName,ordered,description,status
    </sql>
    <select id="selectAll" resultType="com.wangjuan.pojo.Brand">
        select
            <include refid="brand_column"/>
        from tb_brand;
    </select>
```

<!--resultMap-->

```xml
<!--    id:唯一标识-->
<!--    type：映射的类型，支持别名-->
    <resultMap id="brandResultMap" type="brand">

          <!--        id是完成主键字段的映射，
							column：列的名称---数据库中的
							property：是属性名
					   result是完成一般字段的映射
							column：列的名称
							property：是属性名
            
-->
        <result column="brand_name" property="brandName" />
      
        <result column="company_name" property="companyName" />

    </resultMap>
    <select id="selectAll" resultMap="brandResultMap">
        select *
        from tb_brand;
    </select>
```

---

`resultType="com.wangjuan.pojo.Brand"` 所表达的意思是，MyBatis 会把查询 `tb_brand` 表得到的每一行数据，都映射成为 `com.wangjuan.pojo.Brand` 类的一个对象。这里有一个重要的前提，即 `Brand` 类的属性名必须和数据库表的列名保持一致，或者通过 `@Column` 注解来建立映射关系。

| 特性     | resultType                     | resultMap                      |
| -------- | ------------------------------ | ------------------------------ |
| 映射方式 | 自动映射（依赖命名规则）       | 手动配置映射关系               |
| 适用场景 | 简单查询，列名与属性名完全匹配 | 复杂查询，命名不一致或嵌套关系 |
| 性能     | 较高（无需额外解析映射配置）   | 略低（需要解析映射配置）       |
| 灵活性   | 低（无法处理复杂映射）         | 高（可自定义任何映射关系）     |

mybatis-config.xml

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>

    <typeAliases>
        <package name="com.wangjuan.pojo"/>
    </typeAliases>
    
    <!--
    environments：配置数据库连接环境信息。可以配置多个environment，通过default属性切换不同的environment
    -->
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="0061700"/>
            </dataSource>
        </environment>

        <environment id="test">
            <transactionManager type="JDBC"/>
            <dataSource type="POOLED">
                <!--数据库连接信息-->
                <property name="driver" value="com.mysql.cj.jdbc.Driver"/>
                <property name="url" value="jdbc:mysql:///mybatis?useSSL=false"/>
                <property name="username" value="root"/>
                <property name="password" value="0061700"/>
            </dataSource>
        </environment>
    </environments>
    <mappers>
        <!--加载sql映射文件-->
       <!-- <mapper resource="com/itheima/mapper/UserMapper.xml"/>-->

        <!--Mapper代理方式-->
        <package name="com.wangjuan.mapper"/>

    </mappers>


</configuration>
```

logback.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <!--
        CONSOLE ：表示当前的日志信息是可以输出到控制台的。
    -->
    <appender name="Console" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>[%level] %blue(%d{HH:mm:ss.SSS}) %cyan([%thread]) %boldGreen(%logger{15}) - %msg %n</pattern>
        </encoder>
    </appender>

    <logger name="com.itheima" level="DEBUG" additivity="false">
        <appender-ref ref="Console"/>
    </logger>


    <!--

      level:用来设置打印级别，大小写无关：TRACE, DEBUG, INFO, WARN, ERROR, ALL 和 OFF
     ， 默认debug
      <root>可以包含零个或多个<appender-ref>元素，标识这个输出位置将会被本日志级别控制。
      -->
    <root level="DEBUG">
        <appender-ref ref="Console"/>
    </root>
</configuration>
```

Brand

```java

public class Brand {

    // id 主键
    private Integer id;
    // 品牌名称
    private String brandName;
    // 企业名称
    private String companyName;
    // 排序字段
    private Integer ordered;
    // 描述信息
    private String description;
    // 状态：0：禁用  1：启用
    private Integer status;

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getBrandName() {
        return brandName;
    }

    public void setBrandName(String brandName) {
        this.brandName = brandName;
    }

    public String getCompanyName() {
        return companyName;
    }

    public void setCompanyName(String companyName) {
        this.companyName = companyName;
    }

    public Integer getOrdered() {
        return ordered;
    }

    public void setOrdered(Integer ordered) {
        this.ordered = ordered;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public Integer getStatus() {
        return status;
    }

    public void setStatus(Integer status) {
        this.status = status;
    }

    @Override
    public String toString() {
        return "Brand{" +
                "id=" + id +
                ", brandName='" + brandName + '\'' +
                ", companyName='" + companyName + '\'' +
                ", ordered=" + ordered +
                ", description='" + description + '\'' +
                ", status=" + status +
                '}';
    }
}

```

Mapper 

```java

public interface Mapper {
    List<Brand> selectAll();
}

```



```java
public class MybatisTest {
    @Test
    public void testSelectAll()throws IOException {
        //1.获取sqlSessionFactory    
//1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
    String resource = "mybatis-config.xml";
    InputStream inputStream = Resources.getResourceAsStream(resource);
    SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

    //2.  获取SqlSession对象
    SqlSession sqlSession = sqlSessionFactory.openSession();

    //3.  获取mapper接口的代理对象
    BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

    //4. 执行方法
    List<Brand> brands=brandMapper.selectAll();
    System.out.println(brands);

    //5. 释放资源
    sqlSession.close();
}
```
BrandMapper.xml

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="com.wangjuan.mapper.BrandMapper">
<!--
<select id="selectAll" resultType="com.wangjuan.pojo.Brand">
    select *
    from tb_brand;
</select>
-->

<!--    <sql id="brand_column">-->
<!--        select id,brand_name as brandName,company_name as companyName,ordered,description,status-->
<!--    </sql>-->
<!--    <select id="selectAll" resultType="com.wangjuan.pojo.Brand">-->
<!--        select-->
<!--            <include refid="brand_column"/>-->
<!--        from tb_brand;-->
<!--    </select>-->
    
<!--    id:唯一标识-->
<!--    type：映射的类型，支持别名-->
    <resultMap id="brandResultMap" type="brand">
<!--        id是主键字段的映射，result是一般字段的映射
            column列的名称，property是属性
-->
        <result column="brand_name" property="brandName" />
        <result column="company_name" property="companyName" />

    </resultMap>
    <select id="selectAll" resultMap="brandResultMap">
        select *
        from tb_brand;
    </select>
```

BranMapper

```java
public interface BrandMapper {

//    查询所有
    public List<Brand> selectAll();

    // 查看详情：根据id查询
    Brand selectById(int id);
}
```



## 2.查看详情

![1747470038128](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747470038128.png)

```java
public interface BrandMapper {

//    查询所有
    public List<Brand> selectAll();

    // 查看详情：根据id查询 ------方法名要和映射文件的名称一样。
    Brand selectById(int id);
}
```

```java
public class MybatisTest {

public void testSelectById()throws IOException {
    //有一个位置接收参数
    int id =1;
    //1.获取sqlSessionFactory

    //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
    String resource = "mybatis-config.xml";
    InputStream inputStream = Resources.getResourceAsStream(resource);
    SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

    //2.  获取SqlSession对象
    SqlSession sqlSession = sqlSessionFactory.openSession();

    //3.  获取mapper接口的代理对象
    BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

    //4. 执行方法
   Brand brand = brandMapper.selectById(id);
   System.out.println(brand);

    //5. 释放资源
    sqlSession.close();
}
```

#{}里的字符串和接口方法里的参数名称保持一致。

```XML
<!--
* 参数占位符：
    1.#{}:会将其替换成？ 为了防止sql注入
    2.${}:拼sql，会存在SQL注入问题
    3. 使用时机：
        *参数传递的时候：#{}
        *表名或列名不固定的情况下：${}

* 参数类型：parameterType:可以省略。
* 特殊字符处理：
    1. 转义字符：
    2. CDATA区：
        -->
 <!--   <select id="selectById" parameterType="int" resultMap="brandResultMap">
        select *
        from tb_brand where id =#{id} ;
    </select>-->

    <select id="selectById" parameterType="int" resultMap="brandResultMap">
        select *
        from tb_brand where id
                                <![CDATA[
                                <
                            ]]>
                                #{id} ;
    </select>
</mapper>
```

![1747472923375](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747472923375.png)

## 3.多条件查询

mybatis如何接受多个参数。

1. 条件表达式
2. 如何连接

![1747473289449](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747473289449.png)

返回一个list的集合

​                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           

![1747472981580](E:\githubcode\LearnLog\MyBatis.assets\C%5CUsers%5C27101%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5C1747472981580.png)

​                          

**三种不同的参数接收方式**                                                      

**参数占位符**：写成**对象的属性名**，规避很多问题。

三个参数的值传递到sql语句对应的占位符的位置，不知道哪个参数传递到哪个占位符--------->@param标注 （“status”）对位上 占位符 #{status}

自动的给参数占位符设置值。

### （1）散装参数

BrandMapper.xml

```xml

<!--
    条件查询
-->
<select id="selectByCondition" resultMap="brandResultMap">
    select *
    from tb_brand where status =#{status}
    and company_name like #{companyName}
    and brand_name like #{brandName}
</select>
```



BrandMapper.java

@**Param**给到sql里面哪个占位符。

```java
/*    条件查询
       *参数接收
            1. 散装参数：如果方法中有多个参数，需要使用@Param("SQL参数占位符名称")
            2. 对象参数:对象的属性名称要和参数占位符一致
            3. map集合参数

            * */
    List<Brand> selectByCondition(@Param("status") int status,@Param("companyName") String companyName,@Param("brandName") String brandName);
}

```

MybatisTest.java

```java

@Test
    public void testSelectByCondition()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为";
        String brandName="华为";

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";


        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
       List<Brand> brands = brandMapper.selectByCondition(status,companyName,brandName);
       System.out.println(brands);
        //5. 释放资源
        sqlSession.close();
    }
```



### （2）对象参数

如果三个参数属于同一个对象的话，把他们封装成一个对象，把对象传递到方法selectByCondition里面来，

```java
public interface BrandMapper {
List <Brand> selectByCondition(Brand brand);
```

把Brand数据封装成对象，传到方法里Brand brand。

```java
public class MybatisTest {
    
@Test
    public void testSelectByCondition()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为";
        String brandName="华为";

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";

        //封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
        brand.setCompanyName(companyName);
        brand.setBrandName(brandName);


        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
//       List<Brand> brands = brandMapper.selectByCondition(status,companyName,brandName);
       List<Brand>brands = brandMapper.selectByCondition(brand);
    System.out.println(brands);
        //5. 释放资源
        sqlSession.close();
    }
}

```



### （3）map集合参数

```java
public interface BrandMapper {
List <Brand> selectByCondition(Map map);
```

map里键的名称和Mapper.xml里的参数占位符里的名称一致

```java
@Test
    public void testSelectByCondition()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为";
        String brandName="华为";

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";

        /*//封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
        brand.setCompanyName(companyName);
        brand.setBrandName(brandName);
*/

    Map map = new HashMap();
    map.put("status",status);
    map.put("companyName",companyName);
    map.put("brandName",brandName);

        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
//       List<Brand> brands = brandMapper.selectByCondition(status,companyName,brandName);
//       List<Brand>brands = brandMapper.selectByCondition(brand);
    List<Brand>brands = brandMapper.selectByCondition(map);
    System.out.println(brands);
        //5. 释放资源
        sqlSession.close();
    }
}
```

SQL语句设置多个参数有几种方式？

1）散装参数：需要使用@parm（“SQL中的参数占位符名称”）

2）实体类封装参数：只需要保证SQL中的参数名和实体类属性名对应上，即可设置成功

3）map集合：只需要保证SQL中的参数名和map集合的键的名称对应上，即可设置成功。

---

如果三个条件，哪怕少一个条件都查不了。

### （4）动态条件查询

#### 多条件

![1748936559738](E:\githubcode\LearnLog\MyBatis.assets\E%5Cgithubcode%5CLearnLog%5CMyBatis.assets%5C1748936559738.png)

SQL语句会随着用户的输入或外部条件的变化而变化，我们称为动态SQL。

---

BrandMapper.xml

```xml
  <!--
       动态条件查询
       * if:条件判断
            *test：逻辑表达式
       *问题：
            *(1)恒等式-过度一下，把每个条件过度一下-where 1=1
            *(2)<where> 替换where关键字
   -->
    <select id="selectByCondition" resultMap="brandResultMap">
        select *
        from tb_brand
        <where>
        <if test="status !=null">status =#{status}</if>
        <if test="companyName !=null and companyName !=''">and company_name like #{companyName}</if>
        <if test="brandName !=null and brandName !=''">and brand_name like #{brandName}</if>
        </where>
    </select>
</mapper>
```

![1748938908966](E:\githubcode\LearnLog\MyBatis.assets\E%5Cgithubcode%5CLearnLog%5CMyBatis.assets%5C1748938908966.png)

---

#### 单条件

![1748939309907](E:\githubcode\LearnLog\MyBatis.assets\E%5Cgithubcode%5CLearnLog%5CMyBatis.assets%5C1748939309907.png)

1. 先写一个方法：

```java
public interface BrandMapper {
/*
* 单条件动态查询
* */
List <Brand> selectByConditionSingle(Brand brand);

}

```

2. 

```xml
Brandmapper.xml
<select id="selectByConditionSingle" resultMap="brandResultMap">
        select *
        from tb_brand
        where
            <choose><!--相当于swich-->
                <when test="status !=null">
                    status =#{status}
                </when><!--相当于case-->
                <when test="companyName !=null and companyName !=''">
                    and company_name like #{companyName}
                </when>
                <when test="brandName !=null and brandName !=''">
                    and brand_name like #{brandName}
                </when>
                <otherwise><!--相当于default-->
                    1=1
                </otherwise>
            </choose>
    </select>
</mapper>
```

或者这样：

```xml
  <select id="selectByConditionSingle" resultMap="brandResultMap">
        select *
        from tb_brand
        <where>
        <choose><!--相当于swich-->
            <when test="status !=null">
                status =#{status}
            </when><!--相当于case-->
            <when test="companyName !=null and companyName !=''">
                and company_name like #{companyName}
            </when>
            <when test="brandName !=null and brandName !=''">
                and brand_name like #{brandName}
            </when>

        </choose>
        </where>
    </select>
</mapper>
```

1. 测试方法

```java

@Test
    public void testSelectByCondition()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为";
        String brandName="华为";

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";

        //封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
//        brand.setCompanyName(companyName);
//        brand.setBrandName(brandName);
/*

    Map map = new HashMap();
    map.put("status",status);
    map.put("companyName",companyName);
    map.put("brandName",brandName);
*/

        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
//       List<Brand> brands = brandMapper.selectByCondition(status,companyName,brandName);
//       List<Brand>brands = brandMapper.selectByCondition(brand);
   List<Brand>brands = brandMapper.selectByConditionSingle(brand);
    System.out.println(brands);
        //5. 释放资源
        sqlSession.close();
    }
}

```



## 4.添加

![1748949517522](E:\githubcode\LearnLog\MyBatis.assets\1748949517522.png)

在表tb_brand里面写字段名称，values写占位符。

1. BrandMapper

```java

/*
添加
*/
    void add(Brand brand);
}

```

2. BrandMapper.xml

```xml

    <insert id="add">
        insert into tb_brand(brand_name,company_name,ordered,description,status)
        values (#{brandName},#{companyName},#{ordered},#{description},#{status})
    </insert>
```

3. MyBatisTest.java

```java

    @Test
    public void testAdd()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为手机";
        String brandName="华为";
        String description="手机中的战斗机";
        int ordered=100;

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";

        //封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
       brand.setCompanyName(companyName);
        brand.setBrandName(brandName);
        brand.setDescription(description);
        brand.setOrdered(ordered);
/*

    Map map = new HashMap();
    map.put("status",status);
    map.put("companyName",companyName);
    map.put("brandName",brandName);
*/

        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession();

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
        brandMapper.add(brand);

        //提交事务
        sqlSession.commit();
        //5. 释放资源
        sqlSession.close();
    }
}

```

要开启手动提交事务。

如果开启自动提交事务如下：

```java
        //2.  获取SqlSession对象
//        SqlSession sqlSession = sqlSessionFactory.openSession();
//        SqlSession sqlSession = sqlSessionFactory.openSession(true);//自动开启事务
        SqlSession sqlSession = sqlSessionFactory.openSession(false);//手动开启事务
        
```

**主键返回**

![1748952738543](E:\githubcode\LearnLog\MyBatis.assets\1748952738543.png)

插入数据的id值希望在某些地方用到。

设置一个属性keyProperty指向这个对象addOrder的主键id的名称。

![1748956549154](E:\githubcode\LearnLog\MyBatis.assets\1748956549154.png)

指向id的属性名称。

## 5.修改

### 修改全部字段

![1748956661232](E:\githubcode\LearnLog\MyBatis.assets\1748956661232.png)

1. BrandMapper.java

```java

    /**
     *修改
     */
    int update(Brand brand);
```

2. BrandMapper.xml

```xml
    <update id="update">
        update tb_brand
        set
            brand_name=#{brandName},
            company_name=#{companyName},
            ordered =#{ordered},
        description=#{description},
        status=#{status}
            where id =#{id};
    </update>
</mapper>
```

3. MyBatisTest.java

```java

    @Test
    public void testUpdate()throws IOException {
        //接收参数
        int status =1;
        String companyName="华为手机";
        String brandName="华为";
        String description="波导手机，手机中的战斗机";
        int ordered=100;
        int id =5;

        //处理参数
        companyName ="%"+companyName+"%";
        brandName ="%"+brandName+"%";

        //封装对象
        Brand brand = new Brand();
        brand.setStatus(status);
        brand.setCompanyName(companyName);
        brand.setBrandName(brandName);
        brand.setDescription(description);
        brand.setOrdered(ordered);
        brand.setId(id);
/*

    Map map = new HashMap();
    map.put("status",status);
    map.put("companyName",companyName);
    map.put("brandName",brandName);
*/

        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
//        SqlSession sqlSession = sqlSessionFactory.openSession();
//        SqlSession sqlSession = sqlSessionFactory.openSession(true);//自动开启事务
        SqlSession sqlSession = sqlSessionFactory.openSession(false);//手动开启事务

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
        int count = brandMapper.update(brand);
        System.out.println(count);

        //提交事务
        sqlSession.commit();
        //5. 释放资源
        sqlSession.close();}
}

```

### 修改动态字段

字段是不固定的，sql语句不能写死。

![1749087908904](E:\githubcode\LearnLog\MyBatis.assets\1749087908904.png)

想改哪个字段就改哪个字段。--------写上对应的if条件判断。

BrandMapper.xml

```xml


    <update id="update">
        update tb_brand
        <set>
            <if test="brandName != null and brandName!=''">
                brand_name=#{brandName},
            </if>
        <if test="brandName != null and brandName!=''">
            ordered =#{ordered},
        </if>
        <if test="brandName != null and brandName!=''">
            description=#{description},
        </if>
        <if test="brandName != null and brandName!=''">
            status=#{status}
        </if>
</set>
            where id =#{id};
    </update>
</mapper>
```

## 6. 删除

### 删除一个

brandmapper.java

```java

    /**
     *删除
     */

    void deleteById(int id);
}
```

brandMapper.xml

```xml

    <delete id="deleteById">
        select from tb_brand where id =#{id}

    </delete>
</mapper>
```

MybatisTest.java

```java

    @Test
    public void testDeleteById()throws IOException {
        //接收参数

        int id =2;


        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
//        SqlSession sqlSession = sqlSessionFactory.openSession();
//        SqlSession sqlSession = sqlSessionFactory.openSession(true);//自动开启事务
        SqlSession sqlSession = sqlSessionFactory.openSession(false);//手动开启事务

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
        brandMapper.deleteById(id);
        //5. 释放资源
        sqlSession.close();}
}

```

### ps:事务没提交（常见坑）

MyBatis 中增删改操作默认需要**手动提交事务**（查询不用）。如果代码里只执行了删除方法，但没提交事务，数据库里数据不会真的删除。
比如测试类里：

```java
// 错误写法：只执行删除，没提交
sqlSession.delete("deleteById", 3); 
// 正确：执行后提交事务
sqlSession.commit(); 
```

### 批量删除

![1749091553528](E:\githubcode\LearnLog\MyBatis.assets\1749091553528.png)

BrandMapper.java

```java

    /**
    *批量删除
     *
     * **/
    void deleteById(int[] ids);
}

```

BrandMapper.xml

```xml
 <!--
    mybatis会将数组参数，封装为一个map集合
    *默认：array = 数组。
    *使用@parm注解，改变map集合的默认key的名称。
    void deleteByIds(@param("ids) int[]ids);
    separator=","-分隔符的意思。
    open开始的时候是什么，close遍历完结束的时候拼什么。
    -->
    <delete id="deleteByIds">
        DELETE from tb_brand where id
        in(
            <foreach collection="ids" item="id" separator="," open="（" close="）"
            >
                #{id}
            </foreach>
             )
    </delete>
</mapper>
```

MyBatisTest.java

```java

    @Test
    public void testDeleteByIds()throws IOException {
        //接收参数

        int[] ids = {1,2,4};


        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession(false);//手动开启事务

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
        brandMapper.deleteByIds(ids);
        //提交事务
        sqlSession.commit();
        //5. 释放资源
        sqlSession.close();}
}

```



# 参数传递

![1749105385149](E:\githubcode\LearnLog\MyBatis.assets\1749105385149.png)

UserMapper.java

```java
/*
Mybatis 参数封装：
*单个参数：
	1.POJO类型：直接使用，属性名 和 参数占位符名称 一致
	2.Map集合：直接使用，键名 和 参数占位符一致
	3.Collection:封装为map集合，可以使用@param注解，替换map集合中默认的arg键名
		map.put("arg0",collection集合)；
		map.put("collection",collection集合)；
	4.List：封装为map集合，可以使用@param注解，替换map集合中默认的arg键名
		map.put("arg0",list集合)；
		map.put("collection",list集合)；
		map.put("list",list集合)；
	5.Array:封装为map集合，可以使用@param注解，替换map集合中默认的arg键名
		map.put("arg0",数组)
		map.put("array",数组)
	6.其他类型：直接使用
*多个参数：封装为map集合，可以使用@param注解，替换Map集合中默认的arg键名。
默认：
	map.put("arg0",参数值1)
	map.put("param1",参数值1)
	map.put("param2",参数值2)
	map.put("arg1",参数值2)
sql语句：
	username = #{arg0} and password = #{arg1}
arg0,1换成param也行。

---------------------------@param（"username"）
map.put("username",参数值1)




*/


User select(@param("username")String username,@param("password")String password)
    
    
1.
User select(Collection collection)
```

UserMapperTest.java

```java

    @Test
    public void testSelect()throws IOException {
   

        //1.获取sqlSessionFactory

        //1. 加载mybatis的核心配置文件，获取 SqlSessionFactory
        String resource = "mybatis-config.xml";
        InputStream inputStream = Resources.getResourceAsStream(resource);
        SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);

        //2.  获取SqlSession对象
        SqlSession sqlSession = sqlSessionFactory.openSession(false);//手动开启事务

        //3.  获取mapper接口的代理对象
        BrandMapper brandMapper = sqlSession.getMapper(BrandMapper.class);

        //4. 执行方法
       String username = "zhangsan";
       String password="123";

       User user= UserMapper.select(new HashMap())
        //提交事务
        sqlSession.commit();
        //5. 释放资源
        sqlSession.close();}
}
```

![1749129665678](E:\githubcode\LearnLog\MyBatis.assets\1749129665678.png)

![1749129702056](E:\githubcode\LearnLog\MyBatis.assets\1749129702056.png)

# 注解完成增删改查

![1749129791864](E:\githubcode\LearnLog\MyBatis.assets\1749129791864.png)

---

![1749129933620](E:\githubcode\LearnLog\MyBatis.assets\1749129933620.png)

