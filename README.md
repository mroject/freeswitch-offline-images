# freeswitch Offline Images

freeswitch version: 1.10.6

**download iso file**: [mroject/freeswitch offline image 1.0.0](https://github.com/mroject/freeswitch-offline-images/releases/tag/1.0.0)

In a private network or no network environment, install FreeSWITCH offline and use the iso image to quickly install it.

在私网或者无网络环境，离线安装FreeSWITCH，使用iso镜像快速安装。


as below(如下):

1. download freeswitch.org-1.10.6.v2.iso(下载freeswitch.org-1.10.6.v2.iso镜像文件)
2. Upload the ISO file to the host, such as /tmp.(上传ISO文件至主机，如/tmp)
3. Mount image(挂载镜像): `mount /tmp/ freeswitch.org-1.10.6.v2.iso /media/iso/ -o loop`
4. Create a local YUM source(创建本地yum源):
```shell
[FreeSWITCH-Offline]
name=FreeSWITCH Local Resource
baseurl=file:///media/iso
enabled=1
gpgcheck=0
```
5. Update YUM source(更新yum源): `yum clean all && yum makecache`
6. installation(执行安装):
```shell
yum install -y freeswitch-config-vanilla
systemctl enable freeswitch
systemctl start freeswitch
```

completed!
