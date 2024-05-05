# Legion Slim 7 16APH8 on EndeavorOS

![Image of Legion Slim 7 16APH8 on desk.](./images/hero.jpg)



## Neofetch

```shell
prnice@legion-S7 ~> neofetch
                     ./o.                  prnice@legion-S7 
                   ./sssso-                ---------------- 
                 `:osssssss+-              OS: EndeavourOS Linux x86_64 
               `:+sssssssssso/.            Host: 82Y4 Legion Slim 7 16APH8 
             `-/ossssssssssssso/.          Kernel: 6.8.9-arch1-1 
           `-/+sssssssssssssssso+:`        Uptime: 1 hour, 14 mins 
         `-:/+sssssssssssssssssso+/.       Packages: 1138 (pacman) 
       `.://osssssssssssssssssssso++-      Shell: fish 3.7.1 
      .://+ssssssssssssssssssssssso++:     Resolution: 3200x2000 
    .:///ossssssssssssssssssssssssso++:    DE: Plasma 6.0.4 
  `:////ssssssssssssssssssssssssssso+++.   WM: kwin 
`-////+ssssssssssssssssssssssssssso++++-   Theme: Breeze-Dark [GTK2], Breeze [GTK3] 
 `..-+oosssssssssssssssssssssssso+++++/`   Icons: breeze-dark [GTK2/3] 
   ./++++++++++++++++++++++++++++++/:.     Terminal: yakuake 
  `:::::::::::::::::::::::::------``       CPU: AMD Ryzen 7 7840HS w/ Radeon 780M Graphics (16) @ 5.137GHz 
                                           GPU: AMD ATI 65:00.0 Phoenix1 
                                           Memory: 4224MiB / 31278MiB 

                                                                   
                                                                   
```





## Working

- Similar to Fedora
- Nvidia with beta drivers does not cause the laptop to overheat and power draw is reasonable
- [LenovoLegionLinux](https://github.com/johnfanv2/LenovoLegionLinux) is available and easy to install on the aur



## Not Working

- Close lid issue persists
- Speaker issue is worse
- SDDM Login screen has wrong scaling
- Deep sleep



## Workarounds

- ~~Close lid: No good workaround but closing the lid while the laptop is asleep is the core issue as the laptop will immediately shutdown. Closing the lid when the laptop is awake and unlocked works as expected~~

- Close lid: Blacklist the `ideapad_laptop` kernel module. [source](https://www.reddit.com/r/LenovoLegion/comments/17ohg2s/comment/kf97aht/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

- Speaker issue: Installing [this](https://aur.archlinux.org/packages/legion-y9000x-2022-iah7-sound-fix-dkms) package seems to fix or at least reduce the issue

- SDDM: SDDM works in X11 mode by default, enable wayland support to fix the issue https://wiki.archlinux.org/title/SDDM#Wayland

- ~~Deep sleep: Follow instructions [here](https://forum.manjaro.org/t/weird-sleep-issue-laptop-powers-off-if-lid-is-close-when-sleeping/154144) to enable deep sleep option in bios~~

  > 1. restart and enter bios with F2
  > 2. Pres Ctrl+Alt+Del
  > 3. (You need two hands for this one ) Immediately after start pressing  Fn+R+N in equal intervals not very fast and with the other hand press F2 between that intervals. This will boot to BIOS but when you click on  the More (Advanced options) button in the lower right corner there will  be a lot more options for settings.
  > 4. You need to navigate then to the first of three options with 3  letters PBS or something like that. Under that there is an option for  Power Saving and there is the Modern StandBy setting.
- Deep sleep: The fix above enables the `deep` sleep option, but the system fails to resume from suspend with deep sleep enabled

## **[optimus-manager](https://github.com/Askannz/optimus-manager)**  

Package that helps control Nvidia GPU power mode. Could not fully get it working especially with the beta drivers.



## **[envycontrol](https://github.com/bayasdev/envycontrol)**

Similar to **[optimus-manager](https://github.com/Askannz/optimus-manager)** but this one works.

>  Use https://github.com/enielrodriguez/optimus-gpu-switcher for a KDE widget