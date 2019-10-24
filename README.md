# WireGuard-TunSafe
## TunSafe安装
### 步骤
   1. fan'qiang后，登陆https://tunsafe.com/download
   2. 打开go to User Guide（Mac OS X, Linux or FreeBSD）链接.  
      -->https://tunsafe.com/user-guide/linux :point_left:	
   3. Using TunSafe on POSIX compatible systems（Mac OS)
      * 步骤：
         1. Download the TunSafe source code：（注：源码地址在： https://github.com/TunSafe/TunSafe :point_left:	）
            >$ git clone https://github.com/TunSafe/TunSafe.git<br>
            >$ cd TunSafe
         2. Install compiler environment（Mac OS略过）
         3. Build and install TunSafe
            >$ make<br>
            >$ sudo make install
         - If everything went well, you now have a tunsafe tool in the /usr/bin directory.
         4. Run TunSafe
         - To use TunSafe you need a WireGuard configuration file from a VPN provider. You can also use the free TunSafe VPN servers. Assuming it's named TunSafe.conf, do the following to start TunSafe:（注：这个文件由爸爸传给你，也可以网上生成。）
            >$ sudo tunsafe start -d TunSafe.conf（注：这个文件由爸爸传给你。如何得到，后续揭秘）:eye_speech_bubble:
         - If everything went well, TunSafe daemonizes and continues running in the background. To instead run in the foreground, omit the ***`-d`*** flag.
         - You can verify that TunSafe is running with the tunsafe show command. It should look similar to this.
         `bash
            $ sudo tunsafe show
            interface: tun0
            public key: 8q1SiKy7hKDTPXltp2iimxLjWpL53lRnQzms9f8LXU0=
            private key: (hidden)
            listening port: 8040

            peer: T/DjhrM8hkbqYnOYQvHExF0HI/Csi6DktQth5ijcpDI=
            allowed ips: 192.168.2.0/24
         `
         - Stop TunSafe by using `tunsafe stop`.
         `bash
            $ sudo tunsafe stop tun0
         `
