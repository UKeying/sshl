# SSH免密码快速登录

用来解决 linux 下没有合适的工具可以快速登录到服务器的问题

配置好密码以后，可以使用本工具制定服务器IP便可以直接登录到服务器

而不需要输入服务器密码

本工具需要配合 sshpass 命令使用

sshpass 详情请转：https://sourceforge.net/projects/sshpass/

# 使用方法

步骤一：安装并配置服务器信息

将本工具 sshl 复制到 /bin 目录 或 /usr/bin 目录下 并赋予写权限

并配置服务器密码信息到 /etc/sshl_pass 文件

密码信息请遵从以下格式一行一个配置  密码中如果有特殊符号请使用url编码

root:pass@192.168.1.1:22#tagName

步骤二：使用

如果第一个参数为 -p 则表示获取密码
使用 -l 则表示获取记录列表
使用 -lt 则表示只获取有tag的记录

支持三种输入

1. 直接输入IP
   sshl [-p] ${host_ip} [ ${user} [ ${port} ] ]

2. 输入sftp:// 协议链接
   sshl [-p] sftp://[ ${user} [ :${pass} ]@ ] ${host_ip} [ :${port} ]
   
3. 输入服务器标示
   sshl [-p] ${tag_name}
