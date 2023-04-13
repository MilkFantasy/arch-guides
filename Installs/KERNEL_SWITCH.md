#### 1. Enable multi-threading flag
Run `nano /etc/makepkg.conf` and uncomment line: 
```sh
MAKEFLAGS="-j2"
```
>To uncomment, delete `#` on specified line like previous times, then save and exit. <ins>Change the number "2" to how many threads you have on your cpu</ins>, you can check with `nproc`

#### 2. Install your desired kernel and kernel headers
```sh
yay -S linux-lqx linux-lqx-headers
```
>Install `nvidia-dkms` if you use nvidia gpu.

#### 3. Create initial ramdisk with mkinitcpio
```sh
sudo mkinitcpio -p linux-lqx
```

#### 4. Create new GRUB config
```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

#### 5. Reboot
```sh
reboot
```