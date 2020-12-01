### Boot Logo
The image is based on the image loaded from phone and an image made for fairphone. See https://forum.fairphone.com/t/fp2-change-splash-image-splash-img/29758.

### Read from your phone
Make a copy of the LOGO partition. For example (on your phone) by doing:
```devel-su dd if=/dev/disk/by-partlabel/LOGO of=logo.bin```

### LogoInjector
The sources are from https://forum.xda-developers.com/oneplus-one/themes-apps/mod-cm12-logo-bin-image-injector-v1-0-t3161139. There is a zip that also contains an executable for Windows. This seems like a good [howto](https://blog.phils3r.de/linux/2018/05/12/Boot-Logo-OnePlus-aendern.html)

Build it on linux for example with (ignore warnings):
```gcc lodepng.c LogoInjector.v1.2.c -o LogoInjector.v1.2``` 

### Replace the Logo image
Replace the logo with:
```./Logoinjector.v1.2 -i logo.bin -j 1-logo.png```

Note: both logo.bin as well as 1-logo.png **must** be in the current directory. 

On success the program will print the content of the newly created ``modified.logo.bin`` file.

### Flash to your phone
Flash new bin file with (on your pc):
```fastboot flash LOGO modified.logo.bin``` 
