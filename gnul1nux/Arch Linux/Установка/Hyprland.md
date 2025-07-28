Автозапуск `Hyprland` прописываем в `.bash_profile`

```bash
# Автозапуск Hyprland на tty1
if [[ -z $DISPLAY ]] && [[ $(tty) = /dev/tty1 ]]; then
    exec Hyprland > ~/.hyprland.log 2>&1
fi
```

Если вылезает ошибка с монтированием

```
# Static information about the filesystems.
# See fstab(5) for details.

# <file system> <dir> <type> <options> <dump> <pass>

# Закомментированные UUID (это просто справочная информация)
# UUID=4cb790bf-63fb-4adf-a3af-89bb86594f7c
# UUID=7814-D94B
# UUID=0a3e36e3-1c39-4764-bd46-926a1773e61a

# Активные правила монтирования (БЕЗ # в начале!)
UUID=4cb790bf-63fb-4adf-a3af-89bb86594f7c  /     ext4  rw,relatime  0 1
UUID=7814-D94B                               /boot vfat  rw,relatime,fmask=0022,dmask=0022,codepage=437,iocharset=ascii,shortname=mixed,utf8,errors=remount-ro  0 2
UUID=0a3e36e3-1c39-4764-bd46-926a1773e61a  /home ext4  rw,relatime  0 2
```

