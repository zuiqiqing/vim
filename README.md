![Vim pic by Ruchee](https://raw.github.com/ruchee/mysite/master/public/images/vim.png "Vim pic by Ruchee")

----

## 本配置文件使用指南

----

### 注意事项

1. `Windows` 下需要的软件：`gvim`、`ctags`
2. `Linux` 下需要的包文件：`vim-gnome`、`exuberant-ctags`
3. `Linux` 下必须使用 `GUI` 界面，否则 `Meta` 系按键将失效，可在 `.bashrc` 文件里面写入以下一行 `alias vim='gvim'`
4. 配置文件前面部分的 `tags`、`path` 路径是我本人开发所用，你可以将其删除，也可以替换成自己的工程路径 [你需要先用 `ctags` 生成 `tags` 文件]
5. 可使用这两条命令使 `Linux`、`Cygwin` 以及 `Windows` 共用同一套配置 [当然，这儿假设你安装的是双系统] `ln -s your_gvim_path/vimfiles ~/.vim`、`ln -s your_gvim_path/_vimrc ~/.vimrc`
6. 本项目的 `snippets` 补全文件只包含了我自己使用的那一部分，更多补全可上这下载： `https://github.com/ruchee/backup2/tree/master/snippets`
7. 如出现快捷键不响应的情况，请检查你是否开启了其他软件（比如 `金山词霸` 等），某些软件的快捷键有可能和 `Vim` 相冲突，只需修改或禁用这些软件的快捷键即可

----

### 使用方法

#### Windows

1. 访问 `http://www.vim.org/download.php#pc` 下载最新的 `gVim` [如无法访问该网站，可上 `https://code.google.com/p/unix-cmd-win32/downloads/list` 下载]
2. 安装 `gVim` 到任意目录，这儿为方便讲解，我假定你安装到了 `D:\Apps\Vim`
3. 将 `D:\Apps\Vim\vim7*` 目录加入环境变量 [不知何为环境变量者，请 `Google`]
4. 删除 `Vim` 安装目录下的 `vimfiles` 目录以及 `_vimrc` 文件 [如果有的话请先备份]
5. 使用 `Git` 将本项目拷贝到 `Vim` 安装目录下，取代已删文件的位置 [命令为 `git clone https://github.com/ruchee/vim.git`]
6. 访问 `ctags.sourceforge.net` 下载最新的 `ctags`，将 `ctags.exe` 复制到 `Vim/vim7*` 目录 [如无法访问该网站，可上 `https://code.google.com/p/unix-cmd-win32/downloads/list` 下载]
7. 推荐安装 `Monaco` 字体，因为本配置默认使用该字体，可上 `https://github.com/ruchee/backup/blob/master/download/MONACO.TTF?raw=true` 下载，下载后丢到 `C:\WINDOWS\Fonts` 目录即可
8. 使用任意文本编辑器打开 `_vimrc`，将名字、邮箱、网址等全部替换为你自己的信息，如遇路径不同也全部替换为你本机的实际路径
9. 然后。。。然后就大功告成了，接下只需学习如何使用而已，使用说明全部集中在了 `_vimrc` 文件的头部，配置的后半部分全是各插件的具体配置项，初学无需理会

#### Linux [具体指Ubuntu及其各衍生版，譬如Mint、Xubuntu等]

1. `sudo apt-get install vim-gnome exuberant-ctags` [其他非 `Debian` 系的 `Linux` 请使用其自己的包管理器进行安装]
2. 删除个人主目录下的 `.vim` 文件夹和 `.vimrc` 文件，如果没有则不需要执行删除动作 [使用命令 `rm -rf .vim .vimrc`，请注意备份]
3. 使用 `Git` 将本项目拷贝到个人主目录下，取代已删文件的位置，然后将 `vimfiles`、`_vimrc` 改名为 `.vim`、`.vimrc` [命令为 `git clone https://github.com/ruchee/vim.git`、`mv vimfiles .vim`、`mv _vimrc .vimrc`]
4. 可上 `https://github.com/ruchee/backup/blob/master/download/MONACO.TTF?raw=true` 下载 `Monaco` 字体，下载后使用命令 `mv MONACO.TTF ~/.fonts` 将其丢到 `~/.fonts` 目录即可
5. 使用任意文本编辑器打开 `.vimrc`，将名字、邮箱、网址等全部替换为你自己的信息，如遇路径不同也全部替换为你本机的实际路径
6. 如此这般就配置好了，尽情享受编码的乐趣吧，使用说明全部集中在 `.vimrc` 文件的头部，配置的后半部分全是各插件的具体配置项，初学无需理会

#### Cygwin

1. `Cygwin` 的使用和 `Linux` 大同小异，你只需确保安装时选择了 `vim`、`git` 等包即可，这儿就不再赘述了

----

### ctags简易的使用说明，这儿以Windows下的MinGW为例

1. 首先确保系统能够找到 `ctags.exe`，也就是 `ctags.exe` 添加到了系统环境变量
2. 以 `MinGW` 为例，到编译器安装目录的 `include` 目录上（譬如 `D:\MinGW\include` ）执行命令 `ctags -R --languages=c,c++`
3. 在 `_vimrc` 文件中添加两行 `set tags+=D:/MinGW/include/tags`、`set path+=D:/MinGW/include`
4. 以后编辑 `C/C++` 源文件时，键入一小部分字符，然后按 `Ctrl+P` 即可拥有 `C/C++` 的代码补全
5. 将光标移到某个函数名上，按 `Ctrl+]`，`Vim` 将自动跳转到该函数的定义，按 `Ctrl+T` 可返回跳转之前的位置

以上只是 `ctags` 简单的用法，更专业的介绍请 `Google`

----

本配置文件的更新以我本机的实际使用为准，有安装和使用上的疑问，可访问这个地址 [`https://github.com/ruchee/vim/issues`] 提交反馈

祝使用愉快，Thanks!

by Ruchee
