# Legion Slim 7 16APH8 on NixOS

![Image of Legion Slim 7 16APH8 on desk.](./images/hero.jpg)

## Neofetch

```shell
~ took 1m3s › neofetch 
          ▗▄▄▄       ▗▄▄▄▄    ▄▄▄▖            prnice@nixos 
          ▜███▙       ▜███▙  ▟███▛            ------------ 
           ▜███▙       ▜███▙▟███▛             OS: NixOS 24.11.20240527.9ca3f64 (Vicuña) x86_64 
            ▜███▙       ▜██████▛              Host: LENOVO LNVNB161216 
     ▟█████████████████▙ ▜████▛     ▟▙        Kernel: 6.9.2 
    ▟███████████████████▙ ▜███▙    ▟██▙       Uptime: 23 mins 
           ▄▄▄▄▖           ▜███▙  ▟███▛       Packages: 1289 (nix-system), 1506 (nix-user) 
          ▟███▛             ▜██▛ ▟███▛        Shell: fish 3.7.1 
         ▟███▛               ▜▛ ▟███▛         Resolution: 3200x2000 
▟███████████▛                  ▟██████████▙   DE: Plasma 6.0.5 (Wayland) 
▜██████████▛                  ▟███████████▛   WM: .kwin_wayland_w 
      ▟███▛ ▟▙               ▟███▛            Icons: breeze-dark [GTK2/3] 
     ▟███▛ ▟██▙             ▟███▛             Terminal: .yakuake-wrappe 
    ▟███▛  ▜███▙           ▝▀▀▀▀              CPU: AMD Ryzen 7 7840HS w/ Radeon 780M Graphics (16) @ 5.137GHz 
    ▜██▛    ▜███▙ ▜██████████████████▛        GPU: AMD ATI Phoenix1 
     ▜▛     ▟████▙ ▜████████████████▛         Memory: 5808MiB / 31278MiB 
           ▟██████▙       ▜███▙
          ▟███▛▜███▙       ▜███▙                                      
         ▟███▛  ▜███▙       ▜███▙                                     
         ▝▀▀▀    ▀▀▀▀▘       ▀▀▀▘

~ › 
```



## Installation

1. Fetch ISO from https://nixos.org/download/

2. Choose the same desktop as the one in `nix` config. If desktop is not available, maybe install without desktop

3. If install without desktop, you can increase terminal font size with `setfont -d`

4. For initial on-boarding, make sure to set sane user-name as the one in `nix` config

5. Update default configuration generated after installation; Add `git` and `vim`

6. Clone `nix` config from `git` to somewhere in home directory for example `/home/prnice/Dotfiles/nixos-flaky-tests/`

7. Backup default config in `/etc/nixos` to `~/Documents`

8. Update `hardware-configuration` with data from newly generated one if necessary

9. Link cloned config to `/etc/nixos` for example

   > ```shell
   > sudo ln -s /home/prnice/Dotfiles/nixos-flaky-tests/* /etc/nixos/
   > ```

10. Run build command 

11. Handle bugs



## Working

- Similar to Arch
- Have boot options for running with nvidia graphics, nvidia is disabled by default
- Have boot option for running with `ideapad_laptop` for enabling settings in `LegionLinux`
- `OpenRGB` does not display `i2c` error but keyboard is still undetected
- No `Korners` or usual KDE artifacts
- Copied color profiles from `/run/media/prnice/Windows-SSD/Windows/System32/spool/drivers/color/` into `~/Documents` and use the color profiles in display settings. sRGB profile looks darkest
- Switched from `systemd-boot` to grub because grub supports sub-menus that I can use to hide nixos configurations



## Not Working

- Similar to Arch
- Audio is more flaky
- Setting SDDM wallpap
