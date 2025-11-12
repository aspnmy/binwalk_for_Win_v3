# binwalk_for_Win_v3
适配在Win10/Win11中的Binwalk v3.x以上版本

## 版本说明
binwalk v3 rust重构版完美运行于linux环境，也可以docker部署，但是仍然有部分客户只会使用exe文件双击运行，故此重新适配编译了这个版本

## binwalk_for_Win_v3 可能遇到的几个问题

-  Extraction of squashfs data at offset 0x1174A4 failed! 报错
-  这个是由于squashfs-tools工具链在win系统下不理想造成的解压失败
-  所以我这个适配版本中使用的是外部工具包“sqfs_for_win”
-  使用的时候把sqfs_for_win.zip 解压缩到binwalk.exe同级目录下的sqfs_for_win路径下即可
  <img width="1092" height="507" alt="image" src="https://github.com/user-attachments/assets/210d13f3-9ce1-44fc-851f-8d2126fe646d" />
<img width="664" height="311" alt="image" src="https://github.com/user-attachments/assets/e8e62233-442c-44a8-b3e9-b28970aee28f" />


## binwalk_for_WinGUI的问题

- 考虑到部分用户只会双击exe 不会使用python脚本运行GUI交互界面，所以binwalk_gui.exe,使用pyinstaller进行编译后的独立exe GUI文件，使用binwalk_gui.exe的时候，需要和binwalk.exe在同级目录下，才能正确调用
  <img width="894" height="689" alt="image" src="https://github.com/user-attachments/assets/d71eae04-fe19-4e67-b076-9d3a52726f4a" />
