
## Device specifications

| Device       | Redmi K20 Pro                               |
| -----------: | :---------------------------------------------- |
| SoC          | Qualcomm SDM855 Snapdragon 855                  |
| CPU          | 1x2.84 GHz Kryo 485 + 3x2.4 GHz Kryo 485 + 4x1.8 GHz Kryo 485            |
| GPU          | Adreno 640                                      |
| Memory       | 6GB / 8GB RAM (LPDDR4X)                         |
| Shipped Android version | 9.0                                  |
| Storage      | 64GB / 128GB / 256GB UFS 2.1 flash storage      |
| Battery      | Non-removable Li-Po 4000 mAh                    |
| Dimensions   | 74.3 mm x 156.7 mm x 8.8 mm                         |
| Display      |1080 x 2340 px (FHD+), 19.5:9 ratio                  |
| Rear camera 1 | Sony IMX586 Exmor RS,f/1.75, 0.800 µm, 48Mpx                     |
| Rear camera 2 | 2Omnivision OV8856, f/2.4, 1.120 µm, 8 Mpx                                |
| Front camera | 20 MP, f/2.2, 0.800 µm  |

## Device picture

![Redmi K20 Pro](http://www.mobile2go.com.my/images/thumbs/0007345_xioami-redmi-k20-pro-128gb-256gb-rom-6gb-8gb-ram-original-imported-set.jpeg)
 

# android_device_xiaomi_raphael
For building TWRP for Xiaomi Redmi K20 Pro

TWRP device tree for Xiaomi Redmi K20 Pro

## Features

Works:

- ADB
- Decryption of /data (Only if pattern or pin or password is not setted)
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG


TO-DO:

- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/raphael" name="mauronofrio/android_device_xiaomi_raphael" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_raphael-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/raphael/recovery.img
```

## Other Sources

Kernel Sources: using precompiled stock kernel

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
