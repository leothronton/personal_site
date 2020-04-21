---
title: Ubuntu 9.10 LiveCD修复grub2双系统的引导
author: leo_thronton
type: post
date: 2011-11-16T20:41:37+00:00
url: /2011/11/16/ubuntu-9-10-livecd修复grub2双系统的引导/
categories:
  - 未分类

---
<div class="PublishedByWebStory-[6]51_6DAB372812B748FFAF03B58EBD96E72D_AF252A070AEB443C85A8B864F2AAF5EB">
  前些天装了windows 7（本来是xp和ubuntu 9.10的双系统），为了找回ubuntu费了不少功夫。现将我在网上找到的方法分享一下。</p> 
  
  <p>
    ＊＊ ＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊
  </p>
  
  <p>
    之前在安装Ubuntu 9.10的时候，听说Ubuntu 9.10 采用了新的ext4文件系统，于是就在安装时选择了，结果大部分的grub4dos版本都比较老，并不支持这个文件系统，网上也有人说最新的0.4.4版本好像是支持，但是都太过于复杂，不太适合于大多数人，弄不好还有可能使Windows 7无法引导，网上也有使用这个的方法，喜欢研究的朋友可以搞一下，写出来大家也一起分享一下。在网上也找了一些关于Ubuntu 9.04以前版本和Windows 7共存的方法，但是Ubuntu 9.10采用的grub是新版本的grub2[启动时显示是1.97 beta]，所以之前的方法已经不适用了。
  </p>
  
  <p>
    相信安装过Ubuntu 9.10的朋友都有LiveCD的安装光盘，我们今天就用Ubuntu 9.10的LiveCD的来修复grub2的引导。启动Ubuntu 9.10光盘，选择LiveCD模式，进入之后选择进入终端，先在终端输入如下命令：sudo fdisk -l (注意是小写的L，不是数字的1，此步用于确定电脑中安装Ubuntu 9.10的所在分区的位置，输入以后会输出类似如下信息，找到ID为83的那行，记住/dev/sdaX的情况，比如本人的电脑是/dev/sda7，以下就以此为例，你自己的请加以更改)
  </p>
  
  <p>
    Disk /dev/sda: 80.0 GB, 80026361856 bytes
  </p>
  
  <p>
    255 heads, 63 sectors/track, 9729 cylinders
  </p>
  
  <p>
    Units = cylinders of 16065 * 512 = 8225280 bytes
  </p>
  
  <p>
    Disk identifier: 0x624aa2e0
  </p>
  
  <p>
    Device Boot Start End Blocks Id System
  </p>
  
  <p>
    /dev/sda1 * 1 1388 11149078+ 7 HPFS/NTFS
  </p>
  
  <p>
    /dev/sda2 1389 3825 19575202+ 7 HPFS/NTFS
  </p>
  
  <p>
    /dev/sda3 3826 9729 47423880 f W95 Ext&#8217;d (LBA)
  </p>
  
  <p>
    /dev/sda5 3826 5851 16273813+ b W95 FAT32
  </p>
  
  <p>
    /dev/sda6 5852 8323 19856308+ b W95 FAT32
  </p>
  
  <p>
    /dev/sda7 8324 9598 10241406 83 Linux
  </p>
  
  <p>
    /dev/sda8 9599 9729 1052226 82 Linux swap / Solaris
  </p>
  
  <p>
    然后再输入sudo -i （此步用于得到root权限，无需输入密码，方便以下操作）
  </p>
  
  <p>
    接着输入mkdir /media/tempdir （这里用于创建一个文件夹tempdir，用于挂载刚才的sda7，此文件夹名称你可以依个人爱好而定，没有太多要求）
  </p>
  
  <p>
    再输入 mount /dev/sda7 /media/tempdir （将sda7挂载于tempdir文件夹下）
  </p>
  
  <p>
    下面进入了本次恢复最为关键和激动人心的时刻，在终端输入以下命令：
  </p>
  
  <p>
    grub-install &#8211;root-directory=/media/tempdir /dev/sda （本步骤用于来重新安装grub2到硬盘的主引导记录【MBR】里面，十分关键！）
  </p>
  
  <p>
    输入以后如果出现“Installation finished.No Error Reported.”字符的时候，就表示操作成功了。但是现在只成功的一半，还有以下操作才能够完全成功。
  </p>
  
  <p>
    这时重新启动你的电脑，就能看到grub2的引导界面了，但是这时只能用来引导Ubuntu 9.10，还暂时无法引导Windows 7，这时选择进入Ubuntu 9.10，再找到并启动终端，在终端输入如下命令：
  </p>
  
  <p>
    sudo update-grub2
  </p>
  
  <p>
    按照提示输入密码，如果顺利的话，会出现如下类似语句，那就表示成功了。
  </p>
  
  <p>
    grub.cfg &#8230;
  </p>
  
  <p>
    Found Debian background: moreblue-orbit-grub.png
  </p>
  
  <p>
    Found linux image: /boot/vmlinuz-2.6.31-15-generic
  </p>
  
  <p>
    Found initrd image: /boot/initrd.img-2.6.31-15-generic
  </p>
  
  <p>
    Found memtest86+ image: /boot/memtest86+.bin
  </p>
  
  <p>
    Found Windows 7 (loader) on /dev/sda1
  </p>
  
  <p>
    done
  </p>
  
  <p>
    如果没有出现以上类似语句的话，那就在新立得里面搜索grub，可以安装带有Ubuntu标志的那个grub-pc，安装之后，再输入sudo update-grub2更新一下grub2就可以了。
  </p>
  
  <p>
    转载自：http://foolishken.blog.163.com/blog/static/2562766520091116112454744/
  </p>
  
  <div class="PoweredByWebStory" style="margin-top:15px;margin-bottom:10px;">
    <a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer"><img src="http://image.juziyue.com/WebStoryLogo24.png" alt="菊子曰" style="border:0;" /></a>&nbsp;我用<a target="_blank" href="http://sns.juziyue.com/webinvite.php?u=337" rel="noopener noreferrer">菊子曰</a>写博客，你呢？
  </div>
</div>