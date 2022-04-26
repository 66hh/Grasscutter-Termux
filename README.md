# Grasscutter-Termux

本项目用于在Termux中运行Grasscutter

# 使用方法

1.使用以下命令安装mongoDB

mkdir -p /data/data/com.termux/files/usr/data/db
chmod 777 -R /data/data/com.termux/files/usr/data
curl -LO https://its-pointless.github.io/setup-pointless-repo.sh
bash setup-pointless-repo.sh
pkg update
pkg install -y mongodb
nohup mongod 2>&1 &

2.按照以下步骤安装jdk

curl -LO https://download.oracle.com/java/18/latest/jdk-18_linux-aarch64_bin.tar.gz
tar -zxvf jdk-18_linux-aarch64_bin.tar.gz

配置vim ~/.zshrc，增加如下内容
export JAVA_HOME=jdk路径
export PATH=$PATH:$JAVA_HOME/bin:.
export CLASSPATH=$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib/dt.jar:.

3.克隆此仓库并运行服务器

git clone https://github.com/66hh/Grasscutter-Termux.git
cd Grasscutter-Termux
java -jar grasscutter.jar
