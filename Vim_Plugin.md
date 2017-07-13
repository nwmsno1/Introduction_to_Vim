# Vim 使用笔记（优化插件）
-------
## 插件管理器：vundle
vim中很多软件可以通过vundle安装，简化了插件的安装过程，vundle的安装也十分简单。</br>
项目主页：<https://github.com/VundleVim/Vundle.vim>
### 安装vundle
在命令行中输入
```
$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
### 配置vundle
在`~/.vimrc`文件顶部输入一下代码，配置vundle
```vim
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'

" Put plugin here

call vundle#end()            " required
filetype plugin indent on    " required
```
### 安装插件
- 在刚才输入的代码段`call vundle#begin()`和`call vundle#end() `之间放置插件，插入以下代码。
```vim
Plugin 'git_name/plugin_name'
```
> Note: `git_name`是该插件github的用户名，`plugin_name`是该插件github的项目名，通常就是插件的名字。
如果这里不写`git_name`，vundle默认在[vim-scripts](https://github.com/vim-scripts)用户中搜索插件。

- 进入Command Mode输入
```vim
:PluginInstall
```
vundle会自动下载安装之前写在`~/.vimrc`中的插件。

## 文件树形结构插件：NERDTree
NERDTree可以让Vim想大多数IDLE一样在窗口一侧显示文件树形结构。Vim中使用窗口分割的方式实现的。分割窗口的切换可以通过`<Ctrl-ww>`完成。
项目主页: <https://github.com/scrooloose/nerdtree>
### 安装插件
- 在`~/.vimrc`的`vundle`段中添加
```vim
Plugin 'scrooloose/nerdtree'
```
- 在command mode下输入
```vim
:PluginInstall
```

### 配置NERDTree
在`~/.vimrc`中添加语句可以配置NERDTree。这些语句请根据个人喜好选择性添加
```vim
" 打开NERDTree快捷键，设置为<F2>
map <F2> :NERDTreeToggle<CR>

" 显示行号
let NERDTreeShowLineNumbers=1
let NERDTreeAutoCenter=1
" 是否显示隐藏文件
let NERDTreeShowHidden=1
" 设置宽度
let NERDTreeWinSize=30
" 在终端启动vim时，共享NERDTree
let g:nerdtree_tabs_open_on_console_startup=1
" 忽略以下文件的显示
let NERDTreeIgnore=['\.pyc','\~$','\.swp']
" 显示书签列表
let NERDTreeShowBookmarks=1

" 当vim中没有其他文件，值剩下nerdtree的时候，自动关闭窗口
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
```
### 使用NERDTree
将窗口切换至NERDTree，可以通过快捷键对文件树进行操作。

|   命令  |  功能  |
|--------|:-------:|
|o |打开关闭文件或者目录
|t |在标签页中打开
|T |在后台标签页中打开
|! |执行此文件
|p |到上层目录
|P |到根目录
|K |到第一个节点
|J |到最后一个节点
|u |打开上层目录
|m |显示文件系统菜单（添加、删除、移动操作）
|? |帮助
|q |关闭

## 状态栏插件：vim-airline
这是一个界面美化插件，先看看效果。
![](https://github.com/xumi1993/Introduction_to_Vim/blob/master/image/vim_demo.png)


## 未完待续
