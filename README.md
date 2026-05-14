# Medical-Big-Data-Collection-Subsystem2
## 快速启动

### 环境要求
- JDK 8+
- MySQL 8.0
- Redis 6.0+
- Kafka 3.x(可选,无 Kafka 时降级为本地日志)
- Maven 3.6+

### 步骤

1. 克隆项目
```bash
git clone https://github.com/<your-name>/medreg.git
cd medreg
```

2. 导入数据库
```bash
mysql -uroot -p < docs/medreg.sql
```

3. 修改配置
```yaml
# application-dev.yml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/medreg
    username: root
    password: your_password
  redis:
    host: localhost
    port: 6379
  kafka:
    bootstrap-servers: localhost:9092
```

4. 启动
```bash
mvn clean package -DskipTests
java -jar medreg-service/target/medreg-service.jar
```

5. 访问接口文档
