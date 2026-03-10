# Mindvision-Camera-Linux-PC-Setup

## Install SDK
1. Download [Mindvision Official](https://www.mindvision.ltd/Service-Support/Software-Download.html) or Download specific version [Mindvision_v2.1.0.49](https://drive.google.com/drive/folders/1hqpC7tozNhyAo76x0p-kmgEM_kFPaH4a?usp=sharing)
2. Extract the .tar file
3. Open terminal inside the target folder
4. Install
```
sudo ./install.sh
```
5. Reboot
```
sudo reboot
```

## Verify Installation
1. Verify the USB setup
```
lsusb
```
2. USB setup success if Mindvision camera detected. Example:
```
Bus 004 Device 002: ID f622:0001 MindVision SUA505GC
```
3. Open terminal inside the target folder
4. Change directory
```
cd demo/Sampli_Save_Demo
```
5. Manual Compilation
```
g++ -o demo main.cpp -I../../include -L/lib -lMVSDK -lpthread
```
6. Test Camera
```
sudo ./demo
```
7. When prompted with ```Input 0-0:```, type ```0``` and press Enter.
8. Verify image
```
ls
xdg-open test.bmp
```

## GTK_Demo: A graphical interface to adjust exposure, gain, and white balance in real-time
1. Install Dependency
```
sudo apt-get update
sudo apt-get install libgtk2.0-dev
```
1.1 Press ```y```

2. Manual compilation
```
g++ -o GTK_demo ./src/*.cpp -I./inc -I../../include `pkg-config --cflags --libs gtk+-2.0` -L/lib -lMVSDK -lpthread
```

