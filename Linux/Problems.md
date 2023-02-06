# 重启指令

```sh
sync;sync;sync;reboot
```

- reboot：重启
- halt：系统停止，屏幕可能会保留系统已经停止的信息；实测就是只显示一句话，像卡死了一样
- poweroff：系统关机

更多的选项功能，请务必使用 man 去查询

# 关机指令

```sh
# 立刻关机，now 相当于 0 的状态
shutdown -h now
# 系统在今天的 20:25 分关机，若在 20：27 分才下单此指令，则隔天关机
shutdown -h 20:25
# 十分钟后关机
shutdown -h +10
# 立刻重启
shutdown -r now
# 30 分钟后重启，并显示后面信息给所有在线的使用者
shutdown -r +30 '要关机了'
# 只发送信息，而不关机，笔者实测这个没有看到效果，上面的都有效果
shutdown -k noew '吓唬你的'

```

```markdown
systemctl [指令]

halt ：系统停止，屏幕显示一句话，假死的样子
poweroff：进入关机模式
reboot：直接重新启动
suspend：进入休眠模式

```

# Linux从一般用户切换root用户

```markdown
默认安装完成之后并不知道root用户的密码，那么如何应用root权限呢？
(1)sudo 命令  
这样输入当前管理员用户密码就可以得到超级用户的权限。但默认的情况下5分钟root权限就失效了。
(2)sudo -i
通过这种方法输入当前管理员用户的密码就可以进到root用户。
(3)如果想一直使用root权限，要通过su切换到root用户。
那我们首先要重设置root用户的密码：
sudo passwd root
这样就可以设置root用户的密码了。

之后就可以自由的切换到root用户了
su
输入root用户的密码即可。

当然，如果想从root用户切换回一般用户，则可使用  su -val(一般用户名)

而当你再次切回到root用户，则只需要键入exit,再次输入exit则回到最初的用户下
```

# ls命令

- `ls -al`： list 的意思
  - a：当前目录下的所有文件，包括隐藏文件
  - l：显示详细信息，包括大小，属组，创建时间

![image-20230206121658063](C:\Users\mark\AppData\Roaming\Typora\typora-user-images\image-20230206121658063.png)

