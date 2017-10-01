# Настройка красивого терминала
Окончательный вид терминала:

![terminal](https://rawgit.com/DmitryGaranin/zsh-beautiful/master/images/zsh_powerleve9k.png)

## Zsh

```
sudo apt-get install zsh
```

## Oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Powerlevel9k

```
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

После установки, в `~/.zshrc` вместо строки с началом `ZSH_THEME=` вставить:
```
POWERLEVEL9K_MODE='awesome-fontconfig'
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(root_indicator context dir vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(time)

POWERLEVEL9K_PROMPT_ON_NEWLINE=true

# `git hub colors`
POWERLEVEL9K_VCS_CLEAN_BACKGROUND='042'
POWERLEVEL9K_VCS_UNTRACKED_BACKGROUND='100'
POWERLEVEL9K_VCS_MODIFIED_BACKGROUND='red'

POWERLEVEL9K_STATUS_VERBOSE=false
POWERLEVEL9K_TIME_FORMAT="%D{%H:%M:%S}"
export DEFAULT_USER="$USER"

# `theme`
ZSH_THEME="powerlevel9k/powerlevel9k"
```

В терминале выполняем: `sudo chsh -s /bin/zsh` и перезапускаем сеанс пользователя


Дополнительная информация:
* [Powerlevel9k](https://github.com/bhilburn/powerlevel9k)
* [Много готовых конфигураций](https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config)


## Font Awesome (добавляем красивые иконки)

1. Скачиваем репозиторий и следуем инструкции по установке из его readme:
```
https://github.com/gabrielelana/awesome-terminal-fonts
```
2. __Либо__ выбираем в папке `./fonts/fontawesome-regular.ttf`
3. Двойной клик > Установить
4. `fc-cache -fv ~/.fonts`
5. `source ~/.zshrc` либо перезапустить терминал

## Zsh-Autosuggestions (через oh-my-zsh)
Оригинал установки: [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)

1. Склонировать репозиторий в `$ZSH_CUSTOM/plugins` (по умолчанию `~/.oh-my-zsh/custom/plugins`)
```
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
2. В `~/.zshrc` добавить плагин
```
plugins=(zsh-autosuggestions)
```
3. А также в конце добавить
```
# set orange color
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=3"
# if color is not set, add this line (uncomment) to the end of the file ~/.zshrc
# export ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=3"

ZSH_AUTOSUGGEST_BUFFER_MAX_SIZE='15'
# bind shortcut: ctrl + space
bindkey '^ ' autosuggest-accept
```
4. Запустить команду `source ~/.zshrc` либо перезапустить терминал
