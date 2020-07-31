# 项目介绍

在Mac OS下，实现与服务器进行便捷的文件上传和下载操作,rz和sz。


## 安装lrzsz

1. 安装支持rz和sz命令的lrzsz：`brew install lrzsz`

2. 在本地/usr/local/bin/目录下保存iterm2-send-zmodem.sh 和iterm2-recv-zmodem.sh两个脚本

3. 设置一下两个脚本的权限，一般 chmod 777 就行了

```bash
chmod 777 /usr/local/bin/iterm2-*
```

## 安装iTerm2

（略）

## 配置触发器

1. 设置Iterm2的Tirgger特性，profiles->default->editProfiles->Advanced中的Tirgger

添加两条trigger，分别设置 Regular expression，Action，Parameters，Instant如下：

```
1.第一条
        Regular expression: rz waiting to receive.\*\*B0100
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-send-zmodem.sh
        Instant: checked
2.第二条
        Regular expression: \*\*B00000000000000
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
        Instant: checked
```

![如图](https://github.com/unixhot/iterm2-zmodem/blob/master/static/lrzsz.png)

