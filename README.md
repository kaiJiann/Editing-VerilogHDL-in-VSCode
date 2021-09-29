# Editing VerilogHDL in VSCode 配置 VS Code 的 Verilog 开发环境

## 安装与配置的插件
- [Vrilog HDL](https://link.zhihu.com/?target=https%3A//marketplace.visualstudio.com/) 实现语法高亮等，并且是安装其他拓展的基础。
- [ctags](https://github.com/universal-ctags/ctags-win32) 安装CTAGS，实现定义的跳转等。
- xvlog 实现代码的编译、检错功能。这是vivado自带的编译器，不用下载，只需配置即可。

## 具体步骤
- Vrilog HDL 直接在VScode拓展商店中安装就好。
- ctags的安装与配置
    -去上文给的gitHub中的地址下载 *tags-p5.9.20210926.0-x64.zip* 文件
    - 解压该文件，并将所有得到的文件放入一个自己新建的文件夹
    - 将上一步新建的文件夹的地址添加到全局环境变量。
    -**验证**: 在代码中将光标停在变量上，观察是否有*转到定义*的选项。以此验证ctags是否安装完成。
- xvlog的配置
    - 将**xvlog.bin**文件的绝对地址添加到环境变量，其为*Vivado的安装地址\Vivado\2021.1\bin*，比如，我的为：*C:\Xilinx\Vivado\2021.1\bin*.
    - 在cmd命令行窗口中输入*xvlog --version*得到*Vivado Simulator 2019.2*   即可验证环境变量添加成功。
    - 在第一个安装的基础插件，即*Vrilog HDL*的拓展设置中，将Linter 选择为xvlog。Linter是编译器的意思
    - **验证** 
        - 保存（*可Ctrl+S*)某个.v文件后，会自动进行编译，如果出现划出语法错误的红色波浪线，证明编译器正常运行。
        - 也可在VS code 中 按 *Ctrl + Shift + P*打开命令行，输入*verilog:Rerun lint tool*,选择*xvlog*，即可启动编译。





***
## 参考与引用
- [HDL 的现代代码编辑体验——配置 VS Code 的 Verilog 开发环境](https://blog.fkynjyq.com/write-verilog-with-vscode/)

- [用VSCode编辑verilog代码、iverilog编译、自动例化、自动补全、自动格式化等常用插件](https://zhuanlan.zhihu.com/p/338497672)
