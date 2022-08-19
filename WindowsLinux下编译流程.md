# WindowsLinux下编译流程

---

[toc]



---

+ Windows
  + obj：目标文件
  + lib：静态链接库文件
    + 静态lib文件（静态库）：（staticlib目录）（多个obj文件静态链接生成）
    + 动态lib文件（导入库）：（lib目录）（生成dll文件时伴随生成）
  + dll：动态链接库文件（bin目录）
  + exe：可执行文件（多个obj文件生成、多个obj文件和lib文件生成、多个lib文件生成）



+ Linux
  + o：目标文件
  + a：静态链接库文件
  + so：动态链接库文件
  + out：可执行文件