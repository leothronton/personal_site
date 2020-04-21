---
title: '【转】史上最强的休眠方法uswsusp(swap可以远小于内存且完美支持笔记本)[更新]'
author: leo_thronton
type: post
date: 2010-06-08T15:51:41+00:00
url: /2010/06/08/【转】史上最强的休眠方法uswsuspswap可以远小于内存且/
spaces_8463b8dc4e3731ca3ab992902cf3f8b8_permalink:
  - "http://cid-8f6a31fabb4cd362.users.api.live.net/Users(-8112616825800567966)/Blogs('8F6A31FABB4CD362!102')/Entries('8F6A31FABB4CD362!1079')?authkey=yuBuArwciRo%24"
categories:
  - 未分类

---
<div id="msgcns!8F6A31FABB4CD362!1079" class="bvMsg">
  <div>
    <div>
      <span style="line-height:normal;font-size:150%;">安装uswsusp</span></p> 
      
      <p>
        Ubuntu gnu/linux只需
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo aptitude install uswsusp
      </div>
      
      <p>
        Arch gnu/linux系统
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo pacman -S uswsusp
      </div>
      
      <p>
        <span style="color:rgb(128,0,255);"><span style="line-height:normal;font-size:150%;">下面两段Ubuntu跳过, 直接看最后的让gnome(或者Hal)改用uswsusp方式休眠</span></span>
      </p>
      
      <p>
        <span style="line-height:normal;font-size:150%;">修改配置/etc/suspend.conf</span>(Ubuntu 已经自动配置好了且Ubuntu下的文件是/etc/uswsusp.conf)<br /> 把
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        resume device =
      </div>
      
      <p>
        中的改成你的swap分区如
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        resume device = /dev/sda2
      </div>
      
      <p>
        uswsusp 还可以压缩内存镜像, 不仅能使swape分区大大小于内存, 更能加快恢复的过程(因为读硬盘的时间减少了).<br /> 去掉compress前面的注释, 即
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        compress = y
      </div>
      
      <p>
        在文件最后添加一行, 清楚设置系统关闭而不是重启.
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        shutdown method = shutdown
      </div>
      
      <p>
        <span style="line-height:normal;font-size:150%;"><br /> 重新创建intramfs(Ubuntu已经自动重建了)</span><br /> 修改/etc/mkinitcpio.conf<br /> 在hook行filesystems前加入uresume(如果有resume, 去掉resume)<br /> 如
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        HOOKS="base udev autodetect pata scsi sata uresume filesystems"
      </div>
      
      <p>
        然后重建intramfs
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo mkinitcpio -p kernel26
      </div>
      
      <p>
        现在先在终端中测试一下<br /> 休眠
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo s2disk
      </div>
      
      <p>
        挂起
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo s2ram
      </div>
      
      <p>
        或者
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo s2ram &#8211;force
      </div>
      
      <p>
        <span style="line-height:normal;font-size:150%;">使 Gnome(或者说Hal)改用uswsusp方法休眠</span>
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sudo su<br /> echo "SLEEP_MODULE=uswsusp">/etc/pm/config.d/module
      </div>
      
      <p>
        然后就有近乎完美的休眠, 挂起了.<br /> 我的笔记本内存为被显卡用了128MB的1G内存<br /> sawp只有500多MB<br /> 挂起和休眠不会像以前那样老是死掉.<br /> 休眠后恢复从grub开始计时只需12秒(而用原来的方法需要15秒, 可能内存大优势优势会更明显)<br /> <span style="font-weight:bold;">快! 人能感觉到的快!</span>
      </p>
      
      <p>
        <span style="line-height:normal;font-size:200%;">解决休眠后屏幕黑屏</span><br /> 发现其原因是休眠时启动的锁定屏幕的进程和s2disk冲突.<br /> 所以解决方法就是让s2disk先sleep几秒钟等锁定屏幕完成后再运行.<br /> 编辑<br /> /usr/sbin/pm-hibernate<br /> 在
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        #!/bin/sh
      </div>
      
      <p>
        下面添加一行
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        sleep 5
      </div>
      
      <p>
        同理可用修改/usr/sbin/pm-suspend
      </p>
      
      <p>
        和ati的兼容(这里用的是 radeon驱动:xf86-video-ati)<br /> 我最开始用休眠时发现和compiz有冲突<br /> 后来在/etc/X11 /xorg.conf里的Section "Device"段添加
      </p>
      
      <div>
        <strong>代码:</strong>
      </div>
      
      <div>
        Option     "AccelMethod"       "EXA"
      </div>
      
      <p>
        后就正常了
      </p>
      
      <p>
        唯一的不足是当笔记本用盖上盖子的方式挂起, 会出现两次挂起过程. 不过不影响使用
      </p>
      
      <p>
        参考:<br /> <a href="http://wiki.archlinux.org/index.php/Suspending_to_Disk_with_hibernate-script">http://wiki.archlinux.org/index.php/Suspending_to_Disk_with_hibernate-script</a><br /> <a href="http://wiki.archlinux.org/index.php/Pm-utils">http://wiki.archlinux.org/index.php/Pm-utils</a><br /> <a href="http://forum.ubuntu.org.cn/viewtopic.php?f=86&t=83263&start=15">viewtopic.php?f=86&t=83263&start=15</a></div> 
        
        <p>
          <span><br /></span>
        </p>
        
        <div>
          <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.webstory.my/WebStoryLogo32.png" /></a> 本文用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>发布
        </div></div> </div>