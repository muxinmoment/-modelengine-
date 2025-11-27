# 步骤一：清理旧版本镜像
为避免缓存或版本冲突，先清理旧容器与镜像：

# 停止并删除现有容器
docker compose down

# 查看 Nexent 镜像
docker images --filter "reference=nexent/*"

# 删除 Nexent 镜像
# Windows PowerShell:
docker images -q --filter "reference=nexent/*" | ForEach-Object { docker rmi -f $_ }
# （可选）清理未使用的镜像与缓存
docker system prune -af

# 🔄 步骤二：更新代码并部署
git pull
cd nexent/docker
cp .env.example .env
bash deploy.sh

# 🗄️ 步骤三：同步数据库
✅ 方法一：使用 SQL 编辑器（推荐）
打开 SQL 编辑器，新建 PostgreSQL 连接。
在 /nexent/docker/.env 中找到以下信息：
Host
Port
Database
User
Password
填写连接信息后测试连接，确认成功后可在 nexent schema 中查看所有表。
新建查询窗口。
打开 /nexent/docker/sql 目录，按文件名中的日期顺序查看 SQL 脚本。
根据上次部署日期，依次执行之后的每个 SQL 文件。
⚠️ 注意事项

升版本前请备份数据库，生产环境尤为重要。
SQL 脚本需按时间顺序执行，避免依赖冲突。
.env 变量可能命名为 POSTGRES_HOST、POSTGRES_PORT 等，请在客户端对应填写。  