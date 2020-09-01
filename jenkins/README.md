docker run \
  --rm \
  -u root \
  -p 8080:8080 \
  -v jenkins-data:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v "$HOME":/home \
  jenkinsci/blueocean
指令說明：
jenkins-data:/var/jenkins_home \
將 jenkins-data 映射到 Docker volume（/var/jenkins_home），並命名為 jenkins-data（volume：用於保存 Docker container 內的資料，當 container 被刪掉時，資料仍保存在指定的資料夾。）
# jenkins docker 初始化demo

sources.list 将apt源替换为阿里云源

plugins.txt 是jenkins要安装的插件列表，可以按自己的需求进行更改

构建：
```
docker built --tag <name>:<tag> .
```

使用：
```
docker run -d -p 8080:8080 -p 50000:5000 -v /var/run/docker.sock:/var/run/docker.sock <name>:<tag>
```

windows下绑定挂载docker套接字使用：
```
docker run -d -p 8080:8080 -p 50000:5000 -v //var/run/docker.sock:/var/run/docker.sock <name>:<tag>
```

