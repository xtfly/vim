Vim
======

自用的一个vim配置文件，适用于`Go`语言环境。

适用版本：
linux下只通过vim7.4的测试。
mac osx下vim7.4或是对应版本的macvim。

## 快捷键

自定义的快捷键:

 快捷键        | 对应操作
 ------------- | :---------
 `<F7>`        | 打开文件浏览窗口(NERDTree)
 `<F8>`        | 打开类/函数视图(tagbar)
 `<C-j>`       | 窗口上移
 `<C-k>`       | 窗口下移
 `<C-h>`       | 窗口左移
 `<C-l>`       | 窗口右移
 `<C-Tab>`     | 切换到下一个Buffer/ `<C-S-Tab>`   | 切换到上一个Buffer
 `jj`          | ESC
 `<C-g>`       | ESC

## 依赖的软件

### vim-go
- Vundle：依赖git从服务器上下载插件；
- vim-go：中的`:GoInstallBinaries`命令依赖`go get`，而`go get`依赖git和mercurial；

### ctags
majutsushi/tagbar插件依赖ctags来解析。可以从以下地址下载：
[ctags](http://ctags.sourceforge.net/)

若是ArchLinux，可以直接安装
```shell
sudo pacman -S ctags
```

若是osx，可采用brew安装
```shell
brew install ctags
```

### vim-go
vim-go插件依赖一大堆go程序，可以通过运行`:GoInstallBinaries`来自行安装，
前提是你已经正确安装go、git和mercurial。而且有一部分go程序源代码处在墙外面。

### powerline-fonts
airline需要使用到这些字体，用于美化状态栏。

linux/osx：
```shell
cd ~
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```

## 安装

### linux & osx
```shell
# 下载xvim
cd ~
git clone https://github.com/xtfly/xvim .xvim

unlink  ~/.vimrc
ln -s ~/.xvim/vimrc.vim  ~/.vimrc

# 安装Vundle
mkdir -p ~/.vim/bundle/
cd ~/.vim/bundle/
git clone https://github.com/gmarik/Vundle.vim

# 链接ultisnippets到rtp
ln -s ~/.xvim/ultisnippets  ./ultisnippets

# 安装所有的插件
vim +PluginIntall
```

## 版权

本项目采用[MIT](http://opensource.org/licenses/MIT)开源授权许可证，完整的授权说明可在[LICENSE](LICENSE)文件中找到。
