![image](https://github.com/user-attachments/assets/fd82225b-33fb-4dda-83a5-9f062cd51ae2)
![tux small](https://github.com/user-attachments/assets/5cec50e6-407c-4e91-b828-ba6c30355dcd)



--------------------------------------
![nvlogo_white-1538839930](https://github.com/user-attachments/assets/5e0ce5f1-d399-4262-a72f-994a55811854)


If you are on Nvidia please use the Nvidia driver that is provided by your Distro, If you experience heavy stuttering after shader compilation on rtx 40/50 series please use PROTON_HIDE_NVIDIA_GPU=1 %command% as the launch command, this will remove dlss and reflex low latency tho and wil behave like a amd gpu in the game.

If your on a Wayland Desktop or tiling manager like KDE Plasma, Gnome, Cosmic, Lxqt, Budgie, elementary os, sway, hyprland, wayfire, river, please use the latest nvidia driver like 555 or 560 or newer

--------------------------------------
![amd-logo-white-png-5773-1024x245-601490339](https://github.com/user-attachments/assets/57cea371-7a50-4b67-9d80-5b9457826bc9)


On AMD you have the AMDGPU driver in the Linux kernel and RADV in MESA which is the userspace driver which is the vulkan api for gaming on AMD, please use atleast kernel 6.12 or higher and mesa 23.1 or higher, If on rdna3 or 4 it is best be running the latest kernel and mesa for best compatibilty with gaming in general.

If you are using a newer Distro like Fedora, Arch, Opensuse tumbleweed, Bazzite, Fedora kinote, garuda, endeavour os, cachyos, pikaos, nobara, chimeraos, steamfork, Fedora silverblue, Nixos, or even Gentoo make sure you are using the newest kernel and mesa that is available for your distro

-----------------------------------
![image](https://github.com/user-attachments/assets/7401c332-fd00-416b-9428-b11cf9b0738c)


Intel, use the latest kernel and MESA aswell, Intel uses the i915 driver below anything Tiger Lake integrated graphics, or a discrete graphics card, If above you will use the XE kernel driver instead which is intel's new kernel driver.

-----------------------------------


![1922724614id24077gol](https://github.com/user-attachments/assets/ce86fddd-3424-4333-91c4-d0cfe301803a)



## PROTON

Please use Proton experimental, This has all of the latest patches from valve for THE FINALS, do NOT use experimental (bleeding edge) unless there is a major change that requires you to use it, You can also use Proton 10.

Valve will force proton hotfix sometimes on everyone for quick patches on games if they cant bring the patches into experimental, should NOT be used for daily use tho on every game.

![image](https://github.com/user-attachments/assets/aeddad67-382d-43bd-a2f5-401541fbd00c)


## YOU ALSO NEED PROTON EAC RUNTIME TO BE INSTALLED IN YOUR STEAMLIBRARY!
![image](https://github.com/user-attachments/assets/df3bb615-fc73-448c-b35b-61f9550dfe52)


--------------------------------------


## YOU CAN ALSO USE GE-PROTON BUT IT ISN'T REQUIRED

[Proton-ge](https://github.com/GloriousEggroll/proton-ge-custom) uses experimental(bleeding edge) and gets updated every couple of weeks with its own patches included like video codecs and specific fixes that valve can not do because of licenses or other issues, it is not recommended for the finals but it's your choice if you want to use it or not

## YOU CAN USE A APPLICATION LIKE PROTONPLUS OR PROTON-UP-QT TO GET GE-PROTON INSTALLED ON STEAM

[ProtonPlus](https://flathub.org/apps/com.vysp3r.ProtonPlus)

[Proton-Up-Qt](https://flathub.org/apps/net.davidotek.pupgui2)

--------------------------------------

## IF YOUR GAME CRASHES AFTER A HOUR OR SO

This usually indicates that your vm.max map_count is too low on the linux distro you are running

## What is vm max map count?

vm.max_map_count is a kernel parameter in Linux that limits the maximum number of memory mappings (also known as virtual memory areas or VMA) a process can have. This parameter is used to prevent excessive memory fragmentation and potential denial-of-service attacks.

## What is a memory mapping?

A memory mapping is a region of virtual memory that is mapped to a physical memory page or a file

Distros like linux mint 21, ubuntu 22.04, debian 12 will have too low of a value, so the game will crash as it tries to create more virtual memory in the game which it will run out of space in that virtual memory so you need to increase.

------------------------------------

## HOW TO INCREASE IT

To increase your vm.max_map_count do this 

Open your terminal

sudo nano /etc/sysctl.d/vm.max_map_count.conf

Add this value to this config 

vm.max_map_count=2147483642

Ctrl-x, y, enter to save the file

Reboot your system

--------------------------------------

## IF YOUR GAME STOPS WORKING

If the game for some reason stops working please clear your wine prefix, your wine prefix is the fake windows directory that proton uses, so when you clear it, the components it uses will be removed requiring the game to redo the setup instructions/recreate that wine prefix so it's clean to use

# THIS MAY RESET YOUR IN-GAME SETTINGS SO PLEASE REMEMBER WHAT YOU HAD BEFOREHAND⚠️⚠️

## HOW TO CLEAR YOUR WINE PREFIX

Each game has its own prefix that steam will create under /steamlibrary/compatdata

If your game is on the main drive then enable hidden files in your file manager and you'll find .steam 

Go to your steamlibrary and right click on the finals, properties, updates, and find the APPID for THE FINALS

![image](https://github.com/user-attachments/assets/8456b6a2-4005-451a-811e-426db77b9694)

Then go to the steamlibrary where you have the finals installed and go to compatdata, find the folder that has the same appid as THE FINALS

![image](https://github.com/user-attachments/assets/776e90f7-53b8-4ba9-be16-b6a2fa9c5a2a)

Delete that prefix and verify the game in steam

Use experimental or now latest Proton 9.0-4 and should be good to go

---------------------------------------

## EAC PROBLEMS

If you get any EAC problems please try clearing the prefix first then if you get the same issue use this launch command for the finals

`PROTON_USE_EAC_LINUX=1 %command%`

![image](https://github.com/user-attachments/assets/fe7447fb-1840-4889-a2f2-34ededeaebc0)

---------------------------------------

## IF YOU HAVE A MEMORY LEAK

If you are getting a memory leak in the finals after a while like 3 hours or so, please try flatpak steam, this has seemed to have solved the issue for me but this leak may still be present if your on a arch based system it seems

Also another fix might be that you dont have zram or "swap" we like to call it, enabled on your linux distro, please look up how to do this for your linux distro that you are using 

## IF YOU HAVE FURTHER PROBLEMS

Please go to the proton github THE FINALS issue page and report your problem

You can also do `PROTON_LOG=1 %command%` as your launch command for the finals to get a log of the game, this log will be in your home directory, which you can then upload to your github comment explaining the problem you are having

[THE FINALS PROTON ISSUE](https://github.com/ValveSoftware/Proton/issues/7317)

---------------------------------------


## IF THE GAME BREAKS FROM A UPDATE PLEASE TRY CLEARING THE PREFIX, IF THAT DOESNT WORK TRY BLEEDING EDGE BUILD OF PROTON

# WARNING THIS CAN OVERTIME DESTROY YOUR WINE PREFIX SO PLEASE USE WITH CAUTION ⚠️⚠️

Find experimental in your steam library

![image](https://github.com/user-attachments/assets/69d9cbdf-9655-4849-bf17-02d88c17214a)

Proprieties on experimental and go to beta, select bleeding edge, latest untested dxvk and vkd3d, update and force compatibility on the finals to use experimental(bleeding edge)

![image](https://github.com/user-attachments/assets/e4ce2cf9-e286-4f3a-aa06-6438fd0a966e)

![image](https://github.com/user-attachments/assets/80c1f38b-c055-49ec-9761-86761972a1b7)

# If it works have fun in the arena! 

# Nama Tama Love's you 

![image](https://github.com/user-attachments/assets/3cc6a3e7-5276-4643-a0ae-366009daf791)



