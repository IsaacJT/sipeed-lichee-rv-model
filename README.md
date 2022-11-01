# sipeed-lichee-rv-model

Model assertion file for build Ubuntu Core images for the Sipeed Lichee RV.

## Build instructions

Install the `ubuntu-image` utility:

    snap install --classic ubuntu-image
    
Build or download the latest versions of the kernel and gadget snaps from the links below.
    
Create an image file using the assertion and downloaded snaps:

    ubuntu-image snap ubuntu-core-22-sipeed-lichee-rv.model \
      --snap sipeed-lichee-rv-kernel_*-allwinner_riscv64.snap \
      --snap sipeed-lichee-rv-gadget_*_riscv64.snap
      
The image is generated and saved to the following file: `sipeed-lichee-rv.img`

Copy the image to an SD card using `dd`:

    dd if=sipeed-lichee-rv.img of=/dev/<path to SD card> bs=4M
    
Insert the SD card into the device, connect a serial console, and boot.

## Related repositories

Kernel snap: https://github.com/IsaacJT/sipeed-lichee-rv-kernel-snap

Gadget snap: https://github.com/IsaacJT/sipeed-lichee-rv-gadget-snap
