### Boot Logo
The image is based on image loaded from phone and an image made for fairphone. See https://forum.fairphone.com/t/fp2-change-splash-image-splash-img/29758.

### Read from your phone
Read the image dat from the LOGO partition. For example with (on your phone):
```devel-su dd if=/dev/disk/by-partlabel/LOGO of=logo.bin```

### LogoInjector
Sources are from https://forum.xda-developers.com/oneplus-one/themes-apps/mod-cm12-logo-bin-image-injector-v1-0-t3161139. There is a zip that also contains an executable for Windows.

Build it for linux for example with:
```gcc lodepng.c LogoInjector.v1.2.c -o LogoInjector.v1.2```

Replace an image with:
```./logoinjector.exe -i logo.bin -j 1-logo.png```

### Flash to your phone
Flash new bin file with (on your pc):
```fastboot flash LOGO logo.modified.bin``` 
