# Legion Slim 7 16APH8 on Fedora 40

## Specs

- Operating System: Fedora Linux 40

- KDE Plasma Version: 6.0.4

- KDE Frameworks Version: 6.1.0

- Qt Version: 6.7.0

- Kernel Version: 6.8.7-300.fc40.x86_64 (64-bit)

- Graphics Platform: Wayland

- Processors: 16 × AMD Ryzen 7 7840HS w/ Radeon 780M Graphics

- Memory: 30.5 GiB of RAM

- Graphics Processor: AMD Radeon Graphics

- Manufacturer: LENOVO

- Product Name: 82Y4

- System Version: Legion Slim 7 16APH8

- Neofetch:
  
  ```shell
  prnice@fedora ~> neofetch
               .',;::::;,'.                prnice@fedora 
           .';:cccccccccccc:;,.            ------------- 
        .;cccccccccccccccccccccc;.         OS: Fedora Linux 40 (KDE Plasma) x86_64 
      .:cccccccccccccccccccccccccc:.       Host: 82Y4 Legion Slim 7 16APH8 
    .;ccccccccccccc;.:dddl:.;ccccccc;.     Kernel: 6.8.7-300.fc40.x86_64 
   .:ccccccccccccc;OWMKOOXMWd;ccccccc:.    Uptime: 19 mins 
  .:ccccccccccccc;KMMc;cc;xMMc:ccccccc:.   Packages: 2602 (rpm), 7 (flatpak) 
  ,cccccccccccccc;MMM.;cc;;WW::cccccccc,   Shell: fish 3.7.0 
  :cccccccccccccc;MMM.;cccccccccccccccc:   Resolution: 3200x2000 
  :ccccccc;oxOOOo;MMM0OOk.;cccccccccccc:   DE: Plasma 6.0.4 
  cccccc:0MMKxdd:;MMMkddc.;cccccccccccc;   WM: kwin 
  ccccc:XM0';cccc;MMM.;cccccccccccccccc'   Theme: Breeze-Dark [GTK2], Breeze [GTK3] 
  ccccc;MMo;ccccc;MMW.;ccccccccccccccc;    Icons: breeze-dark [GTK2/3] 
  ccccc;0MNc.ccc.xMMd:ccccccccccccccc;     Terminal: konsole 
  cccccc;dNMWXXXWM0::cccccccccccccc:,      CPU: AMD Ryzen 7 7840HS w/ Radeon 780M Graphics (16) @ 5.137GHz 
  cccccccc;.:odl:.;cccccccccccccc:,.       GPU: NVIDIA GeForce RTX 4060 Max-Q / Mobile 
  :cccccccccccccccccccccccccccc:'.         GPU: AMD ATI 65:00.0 Phoenix1 
  .:cccccccccccccccccccccc:;,..            Memory: 4489MiB / 31269MiB 
    '::cccccccccccccc::;,.
  ```

## Notes

- Most features worked out of the box, e.g brightness control, normal power consumption etc

- Only one speaker worked after initial install, both worked after updates

- System idles at around 7 - 9w

- Playing [this](https://www.youtube.com/watch?v=gXpwbIy3FT4) video @480p 165hz increases power consumption to around 11 - 12w

- Keyboard deck stays warm-cool most of the time for basic tasks

- AMD p-state seems to be enabled by default
  
  ```shell
  prnice@fedora ~> cpupower frequency-info
  analyzing CPU 10:
  driver: amd-pstate-epp
  CPUs which run at the same hardware frequency: 10
  CPUs which need to have their frequency coordinated by software: 10
  maximum transition latency: Cannot determine or is not supported.
  hardware limits: 400 MHz - 6.08 GHz
  available cpufreq governors: performance powersave
  current policy: frequency should be within 400 MHz and 6.08 GHz.
   The governor "powersave" may decide which speed to use
   within this range.
  current CPU frequency: Unable to call hardware
  current CPU frequency: 1.40 GHz (asserted by call to kernel)
  boost state support:
   Supported: yes
   Active: yes
   AMD PSTATE Highest Performance: 232. Maximum Frequency: 6.08 GHz.
   AMD PSTATE Nominal Performance: 145. Nominal Frequency: 3.80 GHz.
   AMD PSTATE Lowest Non-linear Performance: 42. Lowest Non-linear Frequency: 1.10 GHz.
   AMD PSTATE Lowest Performance: 16. Lowest Frequency: 400 MHz.
  ```

- Fingerprint scanner is detected but enrollment fails

- Installing Nvidia drivers causes the PC to heat up and increases idle power consumption to around 30w
  
  > When the Nvidia drivers are installed, `nvidia-powerd` reports an error setting GPU power limits. One speaker stopped working again after the Nvidia issues. 



## **[LenovoLegionLinux](https://github.com/johnfanv2/LenovoLegionLinux)**

Gives me some of the options from Lenovo vantage on Linux. Includes but not limited to:

- Fan control

- Switching `power-profile-daemon` power mode based on `Fn+Q` power mode

- Switches fan curve based on power mode

- Control IO port lighting

- Enable conservation mode

### Notes

- A `copyr` repository exists but installing the python app directly does not seem to work

- The instructions on the git repo indicate it should be built from source

- Getting a lot of this error `[31685.183777] i2c_designware AMDI0010:03: i2c_dw_handle_tx_abort: lost arbitration`. 
  
  > After some investigation, this error is related to audio. More info [TAS2781: Can&#39;t control volume on TAS2781 - Audio forum - Audio - TI E2E support forums](https://e2e.ti.com/support/audio-group/audio/f/audio-forum/1282425/tas2781-can-t-control-volume-on-tas2781)

- Only `power-profile-daemon` switching and some toggles work at the moment



## **[auto-cpufreq](https://github.com/AdnanHodzic/auto-cpufreq)**

Functions similarly to TLP, main objective is to improve battery life by reducing performance on battery.

With the AMD P-STATE driver, not  sure tools like this are still necessary.

### Notes

- Playing [this](https://www.youtube.com/watch?v=gXpwbIy3FT4) video @480p 165hz with `power-profiles-daemon` disabled and `auto-cpufreq` enabled, power consumption is around 12 - 13w

- Idle power consumption is around 8 - 9w
