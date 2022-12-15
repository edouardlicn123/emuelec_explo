#方法一：

这里推荐使用一个脚本文件

https://github.com/Drewsif/PiShrink

##安装

wget https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh
chmod +x pishrink.sh
sudo mv pishrink.sh /usr/local/bin

##使用

sudo pishrink.sh ./original(large).img ./small(target).img

#方法二：

该方法适合使用在有微软系列分区（如NTFS）的镜像

fdisk -l '你的镜像文件' 

Disk 你的镜像文件: 53.34 GiB, 57269026816 bytes, 111853568 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x4140bd41

Device                                                Boot    Start       End  Sectors  Size Id Type
/media/edo/软件2/viva_roms/viva64g_verB_20220923.img1 *        8192   4202495  4194304    2G  c W95 
/media/edo/软件2/viva_roms/viva64g_verB_20220923.img2       4202496  12593151  8390656    4G 83 Linu
/media/edo/软件2/viva_roms/viva64g_verB_20220923.img3      12595200 111853567 99258368 47.3G  7 HPFS

留意最后一个分区的end值，这里是“111853567”，将该值用到下面的命令中。

truncate --size=$[(111853567+1)*512] '你的镜像文件' 

这样会删除该位置以后的全部内容。


