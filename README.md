# ArchLinux-hyprland-config
Конфиги для Arch

------------------------------------------------------------------------------------

Предустановка программ в Archinstall: git, fifefox, blueman, thunar, brightnessctl, hyprlock, hyprpaper, waybar, telegram-desktop, fish, p7zip

Доп.пакеты: nwg-look papirus-icon-theme fastfetch, 

Замена Shell:
0.5) sudo pacman -S pkgfile ttf-dejavu powerline-fonts inetutils
1) chsh
2) /bin/fish

Установка тем (меняется через gui-приложение):
1) git clone https://github.com/vinceliuice/Graphite-gtk-theme
2) cd Graphite-gtk-theme/
3) ./install.sh

Скачивание конфигов: git clone https://github.com/bars90M9lso/hyprland-config/

Скачивание шрифтов: sudo pacman -S ttf-font-awesome otf-font-awesome ttf-jetbrains-mono
 
Копируем конфиги из репазитория в свои папки

------------------------------------------------------------------------------------

# Установка wlogout - панелька выхода/завершение систему
1) sudo pacman -S meson
2) https://github.com/ArtsyMacaw/wlogout.git
3) cd wlogout/
4) meson build
5) ninja -C build
6) sudo ninja -C build install

---------------------------------

# Установка vs code
1) sudo pacman -S code
   
------------------------------------------------------------------------------------

# Установка yay
1) git clone https://aur.archlinux.org/yay.git
2) cd yay
3) makepkg -si

------------------------------------------------------------------------------------

# Установка руского языка в системе
1) sudo vim /etc/locale.gen 
   ищем и ракомен. ru_RU.UTF-8 UTF-8
2) sudo locale-gen
3) sudo vim /etc/locale.conf
   добавляем LANG=ru_RU.UTF-8
4) set -x LANG ru_RU.UTF-8
   set -x LC_ALL ru_RU.UTF-8
5) проверка локали - locale

------------------------------------------------------------------------------------

https://release-assets.githubusercontent.com/github-production-release-asset/199570071/235deaf4-c280-4884-b9fd-833c1d7e8cba?sp=r&sv=2018-11-09&sr=b&spr=https&se=2025-12-01T07%3A47%3A12Z&rscd=attachment%3B+filename%3Dv2rayN-linux-64.zip&rsct=application%2Foctet-stream&skoid=96c2d410-5711-43a1-aedd-ab1947aa7ab0&sktid=398a6654-997b-47e9-b12b-9515b896b4de&skt=2025-12-01T06%3A46%3A59Z&ske=2025-12-01T07%3A47%3A12Z&sks=b&skv=2018-11-09&sig=jQdIUPpuFIoRW2SurEKgwGcm8gdVGOngiUvpkH0fQow%3D&jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmVsZWFzZS1hc3NldHMuZ2l0aHVidXNlcmNvbnRlbnQuY29tIiwia2V5Ijoia2V5MSIsImV4cCI6MTc2NDU3NTM1MywibmJmIjoxNzY0NTcxNzUzLCJwYXRoIjoicmVsZWFzZWFzc2V0cHJvZHVjdGlvbi5ibG9iLmNvcmUud2luZG93cy5uZXQifQ.6mDKPYSKa0gURvVKw5I3V_ncgWfqMGE2X7bP3Lloc4k&response-content-disposition=attachment%3B%20filename%3Dv2rayN-linux-64.zip&response-content-type=application%2Foctet-stream

# Установка анлог запретов 
https://github.com/Sergeydigl3/zapret-discord-youtube-linux
1) git clone https://github.com/Sergeydigl3/zapret-discord-youtube-linux.git
2) cd zapret-discord-youtube-linux
3) sudo bash main_script.sh
4) sudo bash service.sh

------------------------------------------------------------------------------------

# Дополнение для файлового менеджера Thunar
1) sudo pacman -S thunar thunar-volman gvfs gvfs-mtp gvfs-gphoto2 udisks2 thunar-archive-plugin file-roller unrar unzip tar
   
    thunar-volman – плагин для автоподключения съёмных носителей.
    
    gvfs – обеспечивает доступ к виртуальным файловым системам (MTP, SMB, FTP и т.д.).
    
    gvfs-mtp/gvfs-gphoto2 – для работы с телефонами и камерами.
    
    udisks2 – система для управления дисками.

    thunar-archive-plugin - Добавляет в контекстное меню пункты для работы с архивами

    file-roller - Графический архиватор

    unrar - Утилита для распаковки RAR архивов
   
    unzip - Утилита для распаковки ZIP архивов

    tar - Утилита для работы с архивами
    
------------------------------------------------------------------------------------

# Установка Вирт.машины QEMU/KVM
1) Установка

   sudo pacman -S qemu-full virt-manager virt-viewer dnsmasq bridge-utils ebtables iptables

2) Включение служб
  
   sudo systemctl enable --now libvirtd.service

   sudo usermod -a -G libvirt $USER

3) Для Intel CPU

   sudo pacman -S intel-ucode

4) Настройка вирт.сети
   
  sudo nmcli connection add type bridge autoconnect yes con-name virbr0 ifname virbr0
  
  sudo nmcli connection modify virbr0 ipv4.method shared
  
  sudo nmcli connection up virbr0
  
  reboot

------------------------------------------------------------------------------------

echo 1 | sudo tee /sys/devices/system/cpu/intel_pstate/no_turbo

------------------------------------------------------------------------------------

# Установка MangoHud
1) sudo pacman -S mangohud
2) sudo vim ~/.config/MangoHud/MangoHud.conf (изменения конфига)(есть репозитории)

------------------------------------------------------------------------------------



------------------------------------------------------------------------------------
# Установка hyprshot - для скриншотов
1) yay -S hyprshot
Бинд есть в hyprland.conf

# Установка NormCap - утилита для захвата текста с экрана + OCR + копирование в буфер
1) yay -S normcap
2) sudo pacman -S tesseract tesseract-data-eng tesseract-data-rus
4) tesseract --list-langs (проверка установочных пакетов языка)

------------------------------------------------------------------------------------

# Установка диспечера задачь Mission Center
1) yay -S mission-center
Бинд есть в hyprland.conf

------------------------------------------------------------------------------------



------------------------------------------------------------------------------------

# Установка темы SDDM 
https://github.com/Keyitdev/sddm-astronaut-theme/tree/master
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
