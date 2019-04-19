# Powerline

## Install
```shell
~: sudo apt-get install powerline
~: sudo apt-get install fonts-powerline
```
Configuration of `~/.bashrc`
```
# Powerline
if [ -f /usr/share/powerline/bindings/bash/powerline.sh ]; then
    source /usr/share/powerline/bindings/bash/powerline.sh
fi
```

Configuration of `~/.zshrc`
```
# Powerline
if [[ -r /usr/share/powerline/bindings/zsh/powerline.zsh ]]; then
    source /usr/share/powerline/bindings/zsh/powerline.zsh
fi
```

Configuration of `~/.vimrc`
```
" Powerline
set rtp+=/usr/share/powerline/bindings/vim/

" Always show statusline
set laststatus=2

" Use 256 colours (Use this setting only if your terminal supports 256 colours)
set t_Co=256
```

Configuration of `~/.tmux.conf` 
```
# Powerline
source /usr.share/powerline/bindings/tmux/powerline.conf
set-option -g default-terminal "screen-256color"
```


source: https://ubuntu-mate.community/t/installing-powerline-as-quickly-as-possible/5381
