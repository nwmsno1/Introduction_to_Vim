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

## 状态栏插件：vim-airline
这是一个界面美化插件，先看看效果。
![](https://github.com/xumi1993/Introduction_to_Vim/blob/master/image/vim_demo.png)
