# Docker

Example run:
docker run -d -e UID=1003 -e UIG=1003 -e 'JVM_OPTS=-d64 -server -Xmx16G -Xms1G' --volumes-from mcdata -p 25565:25565 --name mc drphlux/minecraft
