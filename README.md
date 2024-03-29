# Sniper

## Installing the kernel mode driver

The kernel driver needs to be compiled and installed manually. Therefore,
make sure you have the [Windows Driver Kit (WDK) 10](https://msdn.microsoft.com/en-us/library/windows/hardware/ff557573(v=vs.85).aspx) installed.
After compiling the driver with VS, you can install the driver with the following command

     RUNDLL32.EXE SETUPAPI.DLL,InstallHinfSection DefaultInstall 132 ./sniper.inf
	
The driver will be loaded automatically after reboot. To load it manually without reboot, run

     fltmc.exe load sniper
	 
If you don't have a valid code signing certificate and try to install the driver on 64bit Windows,
you need to enable test signed drivers as described [here](https://msdn.microsoft.com/en-us/library/windows/hardware/ff553484(v=vs.85).aspx).

Please make sure to always compile and install the correct driver version (32/64bit) depending on your operating system!

To uninstall the driver, run

    RUNDLL32.EXE SETUPAPI.DLL,InstallHinfSection DefaultUninstall 132 ./sniper.inf

## Usage

Check SniperTestApp for API Usage

## WIP
- Detect username responsible for I/O change.
- Detect IP Address if change is done remotely.
- Add Support for monitoring multiple paths.
- Add package to nuget
