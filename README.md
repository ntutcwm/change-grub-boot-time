# 改變雙系統開機時grub的預設選項以及自動選擇秒數
進入ubuntu的/etc/default資料夾，然後編輯grub。

你需要注意這幾個地方
GRUB_DEFAULT=4
GRUB_TIMEOUT_STYLE=menu
GRUB_TIMEOUT=-1
.
.
.
.
以下一一介紹
GRUB_DEFAULT=4：
    當你開機會看到各個系統列成表，他們的順序就是這裡的0~5看你有幾個系統可以選
而我電腦的ubuntu是0 windows是4，所以我把0 改 4。

GRUB_TIMEOUT_STYLE=menu：
    這裡改動預選的執行模式
    menu:是設定打開界面得時間GRUB_TIMEOUT的秒數後才自動選擇預選的項目，也就是GRUB_DEFAULT)
    hidden/countdown:是會在執行GRUB_TIMEOUT的秒數後才打開選擇界面
    所以正常前況選：menu就對了

GRUB_TIMEOUT=-1：
    這是更改GRUB選單的自選前等待時間長度
    -1:是關閉自選功能 等你自己選擇後按enter才會打開你選的系統
    0:是直接馬上自選，相當於沒給你機會選，就執行預設選項GRUB_DEFAULT
    ：其他數值就是代表其秒數了

改好存檔應該就ok了
～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～～
以下 我改的檔案給大家留存一個原檔以防改錯

.
.
.
.
.
.
.
.
# If you change this file, run 'update-grub' afterwards to update
# /boot/grub/grub.cfg.
# For full documentation of the options in this file, see:
#   info -f grub -n 'Simple configuration'

GRUB_DEFAULT=4
GRUB_TIMEOUT_STYLE=menu
GRUB_TIMEOUT=-1
GRUB_DISTRIBUTOR=`( . /etc/os-release; echo ${NAME:-Ubuntu} ) 2>/dev/null || echo Ubuntu`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""

# If your computer has multiple operating systems installed, then you
# probably want to run os-prober. However, if your computer is a host
# for guest OSes installed via LVM or raw disk devices, running
# os-prober can cause damage to those guest OSes as it mounts
# filesystems to look for things.
#GRUB_DISABLE_OS_PROBER=false

# Uncomment to enable BadRAM filtering, modify to suit your needs
# This works with Linux (no patch required) and with any kernel that obtains
# the memory map information from GRUB (GNU Mach, kernel of FreeBSD ...)
#GRUB_BADRAM="0x01234567,0xfefefefe,0x89abcdef,0xefefefef"

# Uncomment to disable graphical terminal
#GRUB_TERMINAL=console

# The resolution used on graphical terminal
# note that you can use only modes which your graphic card supports via VBE
# you can see them in real GRUB with the command `vbeinfo'
#GRUB_GFXMODE=640x480

# Uncomment if you don't want GRUB to pass "root=UUID=xxx" parameter to Linux
#GRUB_DISABLE_LINUX_UUID=true

# Uncomment to disable generation of recovery mode menu entries
#GRUB_DISABLE_RECOVERY="true"

# Uncomment to get a beep at grub start
#GRUB_INIT_TUNE="480 440 1"
