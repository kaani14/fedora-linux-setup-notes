# fedora-linux-setup-notes

I used this post-install guide as reference: [Fedora 43 Post Install Guide](https://github.com/devangshekhawat/Fedora-43-Post-Install-Guide)


## NVIDIA Drivers for Encrypted Disk

* If you have encrypted your disk, you will see a blank screen after typing your password for accessing your disk. Plymouth tries to initialize graphics before the NVIDIA module is loaded, leading to a black or frozen screen.
* Restart the PC and keep hitting 'e' to enter the GRUB Menu.
* To the line starting with "linux" (it will be the longest line), append "nomodeset". This tells the system not to use the GPU.
* Now you can successfully login and run the commands install the driver:

`sudo dnf install akmod-nvidia`

`sudo dnf install xorg-x11-drv-nvidia-cuda`

Wait for upto 10 minutes for Kernel to rebuilt.

`modinfo -F version nvidia`

Reboot
