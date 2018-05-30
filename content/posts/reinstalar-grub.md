---
title: "Reinstalar GRUB"
date: 2013-07-12T21:03:07-04:00
draft: false
---

Si somos descuidados al instalar otro sistema operativo en nuestro sistema con Linux puede que este
borre el gestor de arranque previo, haciendo imposible ingresar al sistema operativo anterior.

Una solución consiste en reinstalar GRUB, para esto arrancamos el computador con un Live CD
de [Ubuntu](https://www.ubuntu.com/download/desktop).

Lo siguiente es montar la partición que contiene el gestor de arranque, para saber con certeza
cual es ejecutamos en una terminal `sudo fdisk -l` obteniendo una salida como esta:

```
Device    Boot      Start      End        Blocks    Id  System
/dev/sda1            2048    31459327    15728640   27  Hidden NTFS WinRE
/dev/sda2   *    31459328    31664127      102400    7  HPFS/NTFS/exFAT
/dev/sda3        31664128   150304139    59320006    7  HPFS/NTFS/exFAT
/dev/sda4       150306814   625142447   237417817    f  W95 Ext'd (LBA)
/dev/sda5       150306816   574607359   212150272    7  HPFS/NTFS/exFAT
/dev/sda6       574609408   579092479     2241536   82  Linux swap / Solaris
/dev/sda7       579094528   625141759    23023616   83  Linux
```


Fijándonos en la última columna que indica el tipo de partición sabremos que `/dev/sda7` es la que
buscamos, ya que es de tipo **Linux**.


Procedemos a montar la partición:

```
sudo mount /dev/sda7 /mnt
```

Instalamos GRUB especificando el identificador del disco, el que va sin número ya que no
nos referimos a una partición en particular. Escribimos:

```
sudo grub-install --root-directory=/mnt /dev/sda
```

Se demora unos pocos segundos en terminar. Antes de reiniciar desmontamos la partición:

```
sudo umount /mnt
```

Suerte.