芒果派是一款基于全志V3S Soc的高性能，功能全，性价比高，可任意放飞想法，实现各种DIY产品的开发板
特性

CPU:    ARM Cortex-A7, 最大频率 1.2G
DRR2:   Soc 集成 512Mbit DDR2
ROM:    板载 128Mbit SPI Nor Flash
LCD:    板载 480x272 LCD ,通用 40pin 接口
        
WIFI:   板载 ESP8909 wifi soc
接口:  
        SDIO
        I2C 
        板载 USB TO UART 调试接口 
        100M Ethernet (contain EPHY)
        OTG USB
        MIPI CSI
        Headset + Mic
        

芒果派支持原厂bsp版本linux-3.4内核，基于全志fex内核配置适配板上所有接口,开发板demo支持1080p 摄像头录像,拍照,回放
编译

基于ubuntu 16.04, 每个系统版本不一样编译环境依赖可能有所差异请自行解决,先安装camdroid 需要的依赖工具和包
sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev libc6-dev lib32ncurses5-dev ia32-libs x11proto-core-dev libx11-dev lib32readline-gplv2-dev lib32z1-dev libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown libxml2-utils xsltproc
如果提示没有该包可先删除该包安装其它的.

cd camdroid/camdriod
source build/envsetup.sh
lunch
mklichee
extract-bsp
make -j8
pack

sudo apt-get install dkms
sudo dpkg -i awdev-dkms_0.5_all.deb
cd camdroid/tools/LiveSuit
sudo ./LiveSuit.sh

按住板上FLASH烧录按钮，插入USB线.
资料
如需购买开发板 欢迎光临 https://item.taobao.com/item.htm?spm=a230r.1.14.38.6d246571W3bJLr&id=566707014983&ns=1&abbucket=16#detail

原理图,摄像头规书,配置文档请参考 camdroid/AWDocument
有任何疑问欢迎联系本人 QQ:252915145  进行更多有意思的讨论
