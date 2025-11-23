# hyprland-config
Конфиги для Arch

Установка yay
1) git clone https://aur.archlinux.org/yay.git
2) cd yay
3) makepkg -si


Установка диспечера задачь Mission Center
1) yay -S mission-center


Управления подсветкой квавиатуры для ПК от Clevo
https://novacustom.com/clevo-keyboard-backlight-control-for-linux/

1) sudo pacman -S linux-headers (если не установлен)
2) wget https://github.com/wessel-novacustom/clevo-keyboard/raw/master/kb.sh && chmod +x kb.sh && sudo ./kb.sh
