# change-grub-boot-time
when you start your computer with windows and ubuntu, you'll get in the grub system, i want to help  every one to change the system's auto select time or change the recommand first system to select

1. go to /etc/default open grub
2. You'll see

GRUB_DEFAULT=0
GRUB_TIMEOUT_STYLE=menu
GRUB_TIMEOUT=-1
GRUB_DISTRIBUTOR=`( . /etc/os-release; echo ${NAME:-Ubuntu} ) 2>/dev/null || echo Ubuntu`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""



3.we change
GRUB_DEFAULT=0 
{
it identifies the Nth entry in the generated menu counted from zero,change the default system on grub start up page 
my computer's ubuntu=0 windows=4. so i change 0 to 4, then it will select windows when auto
}


GRUB_TIMEOUT_STYLE=menu
{ 
If this option is unset or set to ‘menu’, then GRUB will display the menu and then wait for the timeout set by ‘GRUB_TIMEOUT’ to expire before booting the default entry. Pressing a key interrupts the timeout.

    If this option is set to ‘countdown’ or ‘hidden’, then, before displaying the menu, GRUB will wait for the timeout set by ‘GRUB_TIMEOUT’ to expire. If ESC or F4 are pressed, or SHIFT is held down during that time, it will display the menu and wait for input. If a hotkey associated with a menu entry is pressed, it will boot the associated menu entry immediately. If the timeout expires before either of these happens, it will boot the default entry. In the ‘countdown’ case, it will show a one-line indication of the remaining time.
}

GRUB_TIMEOUT=-1
{
    Boot the default entry this many seconds after the menu is displayed, unless a key is pressed. The default is ‘5’. Set to ‘0’ to boot immediately without displaying the menu, or to ‘-1’ to wait indefinitely.

    If ‘GRUB_TIMEOUT_STYLE’ is set to ‘countdown’ or ‘hidden’, the timeout is instead counted before the menu is displayed.
}

4. save and shutdown restart again
