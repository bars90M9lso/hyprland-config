# hyprland-config
Конфиги для Arch

------------------------------------------------------------------------------------

Установка light для управления яркостью экрана
1) yay -S light
2) sudo chmod +s /usr/bin/light (даём разрешение на изменение)

------------------------------------------------------------------------------------

Установка yay
1) git clone https://aur.archlinux.org/yay.git
2) cd yay
3) makepkg -si

------------------------------------------------------------------------------------

Установка NormCap - утилита для захвата текста с экрана + OCR + копирование в буфер
1) yay -S normcap
2) sudo pacman -S tesseract tesseract-data-eng tesseract-data-rus
4) tesseract --list-langs (проверка установочных пакетов языка)

------------------------------------------------------------------------------------

Установка диспечера задачь Mission Center
1) yay -S mission-center

------------------------------------------------------------------------------------

Управления подсветкой квавиатуры для ПК от Clevo
https://novacustom.com/clevo-keyboard-backlight-control-for-linux/

1) sudo pacman -S linux-headers (если не установлен)
2) wget https://github.com/wessel-novacustom/clevo-keyboard/raw/master/kb.sh && chmod +x kb.sh && sudo ./kb.sh
