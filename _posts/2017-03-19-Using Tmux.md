---
layout:     post
title:      "tmux的使用"
subtitle:   "提升命令行效率"
date:       2017-03-19
author:     "Xiaven"
tags:
    - tools
---

## tmux

### 1.编译安装

源码版本libevent-2.0.21-stable.tar.gz tmux-1.8.tar.gz

链接：http://pan.baidu.com/s/1mhEy3SO 密码：cwyq

#### 1.1 编译libevent
```
   
./configure  --prefix=/home/xiaven/libs/libevent

make

make install
```

#### 1.2 编译tmux

设置编译、链接路径
```
export LDFLAGS="-L /home/xiaven/libs/libevent/lib"

export CFLAGS="-I /home/xiaven/libs/libevent/include/"

./configure --prefix=/home/xiaven/apps/tmux

make

make install
```

设置运行时链接库路径
```

export LD_LIBRARY_PATH=~/libs/libevent/lib

export PATH=~/apps/tmux/bin/:$PATH
```


ps: configure指定路径时需要使用绝对路径

or simply： `sudo apt-get install tmux`


### 2.基本命令

```
tmux                                    # 运行 tmux -2 以256终端运行
tmux a                                  # 接入第一个可用session
C-b d                                   # detach tmux
tmux ls                                 # 显示已有tmux会话（C-b s）
tmux attach-session -t 数字             # attach到某个tmux session


Ctrl-b 空格键  //采用下一个内置布局
Ctrl-b p       // 选择前一个窗口
Ctrl-b n       // 选择下一个窗口
Ctrl-b c       // 创建新窗口
Ctrl-b x       // 关闭当前窗口
Ctrl-b 0~9     //选择几号窗口
Ctrl + b ,     //重命名当前窗口
Ctrl-b z       //最大化当前窗口
Ctrl-b [       //操作缓冲区
Ctrl + b ]     //粘贴缓存buff
```

### 3.配置

~/.tmux.conf

``` 
主要修改
set -g history-limit 65535  #缓冲区行数

#-- base settings --#
set -g default-terminal "screen-256color"
set -g display-time 3000
set -g escape-time 0
set -g history-limit 65535
set -g base-index 1
set -g pane-base-index 1

# vim style
set-window-option -g mode-keys vi

# start selecting text typing 'v' key (once you are in copy mode)
bind-key -t vi-copy v begin-selection
# copy selected text to the system's clipboard
bind-key -t vi-copy y copy-pipe "reattach-to-user-namespace pbcopy"

bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# split window
unbind '"'
unbind '%' 
bind - splitw -v # split window vertically
unbind %
bind | splitw -h # split window horizontally

# status bar
# color 
set -g status-bg black
set -g status-fg white

# align
set-option -g status-justify centre

# left corner
set-option -g status-left '#[bg=black,fg=green][#[fg=cyan]#S#[fg=green]]'
set-option -g status-left-length 20

# window list
setw -g automatic-rename on
set-window-option -g window-status-format '#[dim]#I:#[default]#W#[fg=grey,dim]'
set-window-option -g window-status-current-format '#[fg=cyan,bold]#I#[fg=blue]:#[fg=cyan]#W#[fg=dim]'

# right corner
set -g status-right '#[fg=green][#[fg=cyan]%Y-%m-%d %H:%M#[fg=green]]':

# easy config reload
bind r source-file ~/.tmux.conf \; display "conf_reloaded!"
``` 













