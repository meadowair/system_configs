### Bug List
#### apt软件包无法卸载
一般按照提示:
```bash
apt-get check # 查找出问题的包
apt-get install --fix-broken
```
但是这次遇到的问题是，上面的命令也无法搞定，并且提示报错的信息里面有个无法被覆盖(overwrite)
解决方法:
```bash
cd /var/cache/apt/archives 
sudo dpkg -i --force-overwrite libnvidia-compute-430_430.26-0ubuntu0.18.04.2_amd64.deb # 对应出问题的那个包(将不会被安装提示的那个包)
#之后再卸载即可
```
