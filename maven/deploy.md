# Maven  deploy命令

deploy命令允许maven在本地编译并install项目，随后部署到远程仓库内
https://blog.csdn.net/chenaini119/article/details/52764543

## 用法

### deploy某个jar包  

**mvn deploy:deploy-file  
-DgroupId=targetGroupId  
-DartifactId=targetArtifactId  
-Dversion=targetVersion  
-Dpackaging=jar  
-Dfile=xxx.jar  
-Durl=tartgetUrl   
-DrepositoryId=targetRepositoryId**


### deploy项目下所有jar包  
 
**mvn deploy -DskipTests**


## pom和setting配置

需要在pom文件下配置**distributionManagement**  
在setting文件下配置**server账户密码**  （setting文件要注意是否开启本地override）

例子：  
pom.xml  
```
<distributionManagement>
    <repository>
        <id>targetId</id>  
        <url>https://tartgetUrl.cn</url>
    </repository>
</distributionManagement>
```
setting.xml
```
<servers>
    <server>
        <id>targetId</id>
        <username>yourName</username>
        <password>yourPassword</password>
    </server>
</servers>
```

注意，pom和setting的 id应该是一样的
