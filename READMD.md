# 1 使用
  - git clone https://github.com/MaJinjie/tmux.git ~/.config/
  - git clone git@github.com:MaJinjie/tmux.git ~/.config/

# 2 插件说明
  1. tmux-plugins/tmux-resurrect
  2. tmux-plugins/tmux-continuum
  3. catppuccin/tmux
  4. aserowy/tmux.nvim
## 1 catppuccin
一款tmux主题

## 2 tmux-continuum

### 介绍
  1. 持续保存tmux环境。通常是15分钟后台保存一次，不影响使用
  2. 计算机或服务器打开时，会自动启动tmux
  3. 启动tmux时，自动恢复上次的环境（仅在服务器或计算机启动时发生）

### 必要条件
  1. set -g status on 开启状态栏 

### 设置
  1. @continuum-boot 当它为on时，会自动生成${HOME}/.config/systemd/user/tmux.service文件，并启用他。
     之后，启动终端会话，systemd都会自动启动tmux
     启动的流程是 打开终端窗口 -> 执行tmux命令 
  2. @continuum-systemd-start-cmd 设置启动tmux服务器的命令，默认为new-session -d。
  3. set -g @continuum-boot-options 'alacritty,fullscreen'，可以用来设置启动的终端仿真器
  4. set -g @continuum-save-interval '60' 设置保存的间隔
  5. set -g @continuum-save-interval '0'  禁止自动保存
  6. set -g @continuum-restore 'on/off' 打开或禁用自动恢复
  7. 如何要确保不会发生自动还原，请创建一个 ~/tmux_no_auto_restore文件

### 支持 
  1. 该插件会优先于首次启动的tmux服务器来处理多服务器场景。也就是说，在启动第一台tmux服务器下，启动了第二台服务器，插件会优先处理第一台tmux服务器。
  2. 


## 3 tmux-resurrect

### 介绍
  1. 服务器或计算启动时自动恢复tmux环境

### 设置
  1. 默认不会恢复窗格的shell历史记录，需要额外设置 https://github.com/tmux-plugins/tmux-resurrect/blob/master/docs/restoring_bash_history.md
  2. set -g @resurrect-capture-pane-contents 'on' 可以保存和恢复tmux窗格的内容
  3. 以前的存档默认不会删除，都会被保存在~/.tmux/resurrect/目录中
### 支持
  1. 支持快捷键的重新绑定
  2. 支持一些钩子
  3. 
