# Ubuntu-sshd-gcc-py

带有GCC以及Python2.7，3.4环境的以及sshd的ubuntu

## 镜像标签

- rastasheep/ubuntu-sshd:12.04 (precise)
- rastasheep/ubuntu-sshd:12.10 (quantal)
- rastasheep/ubuntu-sshd:13.04 (raring)
- rastasheep/ubuntu-sshd:13.10 (saucy)
- rastasheep/ubuntu-sshd:14.04 (trusty)
- rastasheep/ubuntu-sshd:16.04 (xenial)

## 源镜像来源

- [precise (12.04) minimal](http://packages.ubuntu.com/precise/ubuntu-minimal)
- [quantal (12.10) minimal](http://packages.ubuntu.com/quantal/ubuntu-minimal)
- [raring (13.04) minimal](http://packages.ubuntu.com/raring/ubuntu-minimal)
- [saucy (13.10) minimal](http://packages.ubuntu.com/saucy/ubuntu-minimal)
- [trusty (14.04) minimal](http://packages.ubuntu.com/trusty/ubuntu-minimal)
- [Xenial (16.04) minimal](http://packages.ubuntu.com/xenial/ubuntu-minimal)

其他使用:
- [openssh-server](https://help.ubuntu.com/community/SSH/OpenSSH/Configuring)

配置:

  - `PermitRootLogin yes`
  - `UsePAM no`
  - exposed port 22
  - default command: `/usr/sbin/sshd -D`
  - root password: `root`

## 调用例子

```bash
$ sudo docker run -d -P --name test_sshd rastasheep/ubuntu-sshd:14.04
$ sudo docker port test_sshd 22
  0.0.0.0:49154

$ ssh root@localhost -p 49154
# The password is `root`
root@test_sshd $
```
