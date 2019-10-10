# 【shell操作】用户权限

### 免密码操作

```
vim /etc/sudoer
# 在末尾添加 账户名     ALL=(ALL)       NOPASSWD: ALL
```

### 将root账户目录改成自己账户

目的：在该目录下使用自己的账户名操作时，可以不加sudo

```
chgrp -R ly lyl
chown -R ly ly
```

### 切换到root权限下

```
sudo -s
```



