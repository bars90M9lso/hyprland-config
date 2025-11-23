# hyprland-config
Конфиги для Arch

------------------------------------------------------------------------------------

Дополнение для файлового менеджера Thunar
sudo pacman -S thunar thunar-volman gvfs gvfs-mtp gvfs-gphoto2 udisks2
    thunar-volman – плагин для автоподключения съёмных носителей.
    gvfs – обеспечивает доступ к виртуальным файловым системам (MTP, SMB, FTP и т.д.).
    gvfs-mtp/gvfs-gphoto2 – для работы с телефонами и камерами.
    udisks2 – система для управления дисками.

------------------------------------------------------------------------------------

Установка yay
1) git clone https://aur.archlinux.org/yay.git
2) cd yay
3) makepkg -si

------------------------------------------------------------------------------------



------------------------------------------------------------------------------------

Установка light для управления яркостью экрана
1) yay -S light
2) sudo chmod +s /usr/bin/light (даём разрешение на изменение)

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
