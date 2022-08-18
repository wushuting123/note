# 命令

## 上传jar包到本地仓库

### 格式

mvn install:install-file "-Dfile={jar包的全路径}" "-DgroupId={jar包的groupid}" "-DartifactId={jar包的aritfactid}" "-Dversion={jar包的版本}" "-Dpackaging=jar"

### 语句

mvn install:install-file "-Dfile=/Users/wushuting/资源/后端/aspose-cells-22.7.jar" "-DgroupId=com.aspose" "-DartifactId=aspose-cells" "-Dversion=22.7" "-Dpackaging=jar"