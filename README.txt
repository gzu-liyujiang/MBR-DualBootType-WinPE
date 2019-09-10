##############################################
MBR-DualBootType-WinPE
By gzu-liyujiang on 2016.8.22
Last Modified on 2019.9.2
##############################################
利用bootmgr及bootmgfw.efi(即bootx64.efi)实现同时支持Legacy及EFI启动类型的PE系统盘。
##############################################

制作说明
1、解压MBR-DualBootType-WinPE.zip到MBR-DualBootType-WinPE。
2、准备优盘或移动硬盘，通过DiskGenius确保磁盘分区表为MBR格式，且有一个FAT32分区，下面假设该分区盘符为X。
3、通过BOOTICE，为X盘安装WindowsNT6主引导记录及BOOTMGR分区引导记录，并设置X盘为活动分区。
4、将MBR-DualBootType-WinPE下的所有文件复制到X盘根目录下。
5、打开QemuBootTester开始测试X盘在Legacy、EFI-x64及EFI-ia32三种模式下是否可以正常启动。

启动过程
1、开机=>Legacy BIOS=>NT5/6 MBR=>/bootmgr=>/boot/bcd=>/windows/system32/boot/winload.exe=>进入系统
2、开机=>EFI BIOS=>EFI-ia32=>/efi/boot/bootia32.efi=>/efi/microsoft/bootia32/bcd=>/windows/system32/boot/winload.efi=>进入系统
3、开机=>EFI BIOS=>EFI-x64=>/efi/boot/bootx64.efi=>/efi/microsoft/boot/bcd=>/windows/system32/boot/winload.efi=>进入系统
