# hyprland-config
Конфиги для Arch

------------------------------------------------------------------------------------

Дополнение для файлового менеджера Thunar
1) sudo pacman -S thunar thunar-volman gvfs gvfs-mtp gvfs-gphoto2 udisks2
   
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

chmod +x ~/.config/hypr/toggle_kbd_backlight.sh
echo 1 | sudo tee /sys/devices/system/cpu/intel_pstate/no_turbo


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

------------------------------------------------------------------------------------

Установка темы SDDM https://github.com/Keyitdev/sddm-astronaut-theme/tree/master
1) sudo pacman -S sddm qt6-svg qt6-virtualkeyboard qt6-multimedia-ffmpeg
2) sudo git clone -b master --depth 1 https://github.com/Keyitdev/sddm-astronaut-theme.git /usr/share/sddm/themes/sddm-astronaut-theme
3) sudo cp -r /usr/share/sddm/themes/sddm-astronaut-theme/Fonts/* /usr/share/fonts/
4) создаём файл в /etc/sddm.conf
   [Theme]
   Current=sddm-astronaut-theme
5) создаем файл /etc/sddm.conf.d/virtualkbd.conf (ломает сиситему)
   [General]
   InputMethod=qtvirtualkeyboard
6) заходи usr/share/sddm/themes/sddm-astronaut-theme/metadata.desktop и редактируем ConfigFile=Themes/cyberpunk.conf 
                                                                  (вариация тем находиться в тойже папке)

sddm-greeter-qt6 --test-mode --theme /usr/share/sddm/themes/sddm-astronaut-theme/ (тестирование)
