# hyprland-config
Конфиги для Arch

------------------------------------------------------------------------------------

Предустановка программ в Archinstall: git, fifefox, blueman, thunar, hyprlock, hyprpaper, waybar, telegram-desktop, fish(доп.пакеты:pkgfile ttf-dejavu powerline-fonts inetutils), 

Доп.пакеты: nwg-look papirus-icon-theme fastfetch, 

Замена Shell:
1) chsh
2) /bin/fish
Установка тем (меняется через gui-приложение):
1) git clone https://github.com/vinceliuice/Graphite-gtk-theme
2) cd Graphite-gtk-theme/
3) ./install.sh

Скачивание конфигов: git clone https://github.com/bars90M9lso/hyprland-config/
Скачивание шрифтов: sudo pacman -5 ttf-font-awesome otf-font-awesome ttf-jetbrains-mono
 
Копируем конфиги из репазитория в свои папки

------------------------------------------------------------------------------------

Установка wlogout - панелька выхода/завершение систему
1) sudo pacman -S meson
2) https://github.com/ArtsyMacaw/wlogout.git
3) cd wlogout/
4) meson build
5) ninja -C build
6) sudo ninja -C build install

------------------------------------------------------------------------------------

Установка yay
1) git clone https://aur.archlinux.org/yay.git
2) cd yay
3) makepkg -si

------------------------------------------------------------------------------------

Установка руского языка в системе
1) sudo vim /etc/locale.gen 
   ищем и ракомен. ru_RU.UTF-8 UTF-8
2) sudo locale-gen
3) sudo vim /etc/locale.conf
   добавляем LANG=ru_RU.UTF-8
4) set -x LANG ru_RU.UTF-8
   set -x LC_ALL ru_RU.UTF-8
5) проверка локами - locale

------------------------------------------------------------------------------------

Установка анлог запретов https://github.com/Sergeydigl3/zapret-discord-youtube-linux
1) git clone https://github.com/Sergeydigl3/zapret-discord-youtube-linux.git
2) cd zapret-discord-youtube-linux
3) sudo bash main_script.sh
4) sudo bash service.sh

------------------------------------------------------------------------------------

Дополнение для файлового менеджера Thunar
1) sudo pacman -S thunar thunar-volman gvfs gvfs-mtp gvfs-gphoto2 udisks2
   
    thunar-volman – плагин для автоподключения съёмных носителей.
    gvfs – обеспечивает доступ к виртуальным файловым системам (MTP, SMB, FTP и т.д.).
    gvfs-mtp/gvfs-gphoto2 – для работы с телефонами и камерами.
    udisks2 – система для управления дисками.

------------------------------------------------------------------------------------



------------------------------------------------------------------------------------

chmod +x ~/.config/hypr/toggle_kbd_backlight.sh
echo 1 | sudo tee /sys/devices/system/cpu/intel_pstate/no_turbo

------------------------------------------------------------------------------------

Установка MangoHud
1) sudo pacman -S mangohud
2) sudo vim ~/.config/MangoHud/MangoHud.conf (изменения конфига)(есть репозитории)

------------------------------------------------------------------------------------

Установка light для управления яркостью экрана
1) yay -S light
2) sudo chmod +s /usr/bin/light (даём разрешение на изменение)
Бинд есть в hyprland.conf

------------------------------------------------------------------------------------
Установка hyprshot - для скриншотов
1) yay -S hyprshot
Бинд есть в hyprland.conf

Установка NormCap - утилита для захвата текста с экрана + OCR + копирование в буфер
1) yay -S normcap
2) sudo pacman -S tesseract tesseract-data-eng tesseract-data-rus
4) tesseract --list-langs (проверка установочных пакетов языка)

------------------------------------------------------------------------------------

Установка диспечера задачь Mission Center
1) yay -S mission-center
Бинд есть в hyprland.conf

------------------------------------------------------------------------------------

Управление охлаждением и цп и гп (работает неполностью)
1) yay -S tuxedo-control-center

подсветкой можно управлять или ↑ или ↓

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
