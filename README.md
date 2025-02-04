# SteamHostSync
第一次用go写的项目，写的比较烂，欢迎大佬指出错误。

## 1. 实现
对Hosts进行一个新的更  
解决Steam、github访问问题

## 2. 使用方法
## 自动方法(使用工具)
推荐使用Hosts管理工具[SwitchHosts](https://github.com/oldj/SwitchHosts) 
[SwitchHosts备用下载源](https://nas.iaimi.info/s/nT5pb8jMQp32QwB)
### 开机自启动SwitchHosts
win + R 后执行 `shell:startup`    
![](/img/1.png)  
将快捷方式复制进去即可  
![](/img/2.png)  
### 配置SwitchHosts实现自动更新  
可选的URL有:
如果访问不到GitHub可以尝试将`github.com`替换为`hub.fastgit.xyz`(国内镜像)
1. ALL: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts`  
2. Steam: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts_steam`  
3. github: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts_github`    
`镜像地址:`
4. All: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts`  
5. Steam: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts_steam`  
6. github: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts_github`  

![](/img/3.png)

## 手动方式
#### 1. hosts 文件在每个系统的位置不一，详情如下:
- Windows 系统：`C:\Windows\System32\drivers\etc\hosts`
- Linux 系统：`/etc/hosts`
- Mac（苹果电脑）系统：`/etc/hosts`

#### 2. 修改方法
复制下面的内容至hosts尾部(追加在文本末尾)

```
#github Start
140.82.113.25			alive.github.com
140.82.113.26			live.github.com
185.199.110.154			github.githubassets.com
140.82.113.22			central.github.com
185.199.111.133			desktop.githubusercontent.com
####			assets-cdn.github.com
185.199.108.133			camo.githubusercontent.com
185.199.109.133			github.map.fastly.net
151.101.1.194			github.global.ssl.fastly.net
140.82.113.4			gist.github.com
185.199.111.153			github.io
140.82.113.3			github.com
192.0.66.2			github.blog
140.82.113.5			api.github.com
185.199.111.133			raw.githubusercontent.com
185.199.110.133			user-images.githubusercontent.com
185.199.111.133			favicons.githubusercontent.com
185.199.111.133			avatars5.githubusercontent.com
185.199.108.133			avatars4.githubusercontent.com
185.199.108.133			avatars3.githubusercontent.com
185.199.109.133			avatars2.githubusercontent.com
185.199.108.133			avatars1.githubusercontent.com
185.199.110.133			avatars0.githubusercontent.com
185.199.110.133			avatars.githubusercontent.com
140.82.113.9			codeload.github.com
16.15.179.102			github-cloud.s3.amazonaws.com
3.5.3.216			github-com.s3.amazonaws.com
54.231.128.25			github-production-release-asset-2e65be.s3.amazonaws.com
52.216.212.57			github-production-user-asset-6210df.s3.amazonaws.com
52.216.212.57			github-production-repository-file-5c1aeb.s3.amazonaws.com
185.199.109.153			githubstatus.com
140.82.114.17			github.community
20.99.227.183			github.dev
185.199.109.133			media.githubusercontent.com
#github End
# Last Update Time : 2025-01-23 04:21:28 

#steam Start
23.194.74.106			steamcommunity.com
23.60.37.156			www.steamcommunity.com
104.117.247.50			media.steamcommunity.com
23.220.151.221			store.steampowered.com
23.194.74.106			api.steampowered.com
23.194.74.106			help.steampowered.com
23.215.55.134			steamcdn-a.akamaihd.net
23.60.37.156			steam-chat.com
#steam End
# Last Update Time : 2025-01-23 04:21:29 

#Ubisoft_download Start
23.201.69.21			static3.cdn.Ubi.com
23.220.176.4			static2.cdn.Ubi.com
193.108.91.206			static1.cdn.Ubi.com
#Ubisoft_download End
# Last Update Time : 2025-01-23 04:21:29 

#Blizzard Start
34.125.163.138			prod.actual.battle.net
#Blizzard End
# Last Update Time : 2025-01-23 04:21:29 

#Github: https://github.com/Clov614/SteamHostSync

```

## 激活生效
大部分情况下是直接生效，如未生效可尝试下面的办法，刷新 DNS：
1. Windows：在 CMD 窗口输入：`ipconfig /flushdns`
2. Linux 命令：`sudo nscd restart`
3. Mac 命令：`sudo killall -HUP mDNSResponder`  

## 手动配置Source.yaml文件添加新hosts  
手动下载可执行文件第一次执行后会在目录生成Source.yaml文件，可手动配置。  

```
ua : Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
platforms:
  -
    #github :
    - github            #数组的第一个值为对应平台
    - alive.github.com  #后续值为需要解析ip地址的域名
    - live.github.com
    - github.githubassets.com
    - central.github.com
    - desktop.githubusercontent.com
    - assets-cdn.github.com
    - camo.githubusercontent.com
    - github.map.fastly.net
    - github.global.ssl.fastly.net
    - gist.github.com
    - github.io
    - github.com
    - github.blog
    - api.github.com
    - raw.githubusercontent.com
    - user-images.githubusercontent.com
    - favicons.githubusercontent.com
    - avatars5.githubusercontent.com
    - avatars4.githubusercontent.com
    - avatars3.githubusercontent.com
    - avatars2.githubusercontent.com
    - avatars1.githubusercontent.com
    - avatars0.githubusercontent.com
    - avatars.githubusercontent.com
    - codeload.github.com
    - github-cloud.s3.amazonaws.com
    - github-com.s3.amazonaws.com
    - github-production-release-asset-2e65be.s3.amazonaws.com
    - github-production-user-asset-6210df.s3.amazonaws.com
    - github-production-repository-file-5c1aeb.s3.amazonaws.com
    - githubstatus.com
    - github.community
    - github.dev
    - media.githubusercontent.com
  -
    #steam:
    - steam
    - steamcommunity.com
    - www.steamcommunity.com
    - store.steampowered.com
    - api.steampowered.com
    - help.steampowered.com
    - store.akamai.steamstatic.com
    - steamcdn-a.akamaihd.net
    - cdn.akamai.steamstatic.com
    - steam-chat.com
    - community.akamai.steamstatic.com
```
