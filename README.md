# raspi-flutter: Raspberry Pi Flutter Development Toolkit

<p align="left">
<img src="assets\background.png?raw=true" width="100%" alt="raspi-flutter" />
</p>

**raspi-flutter** is a command-line tool that simplifies the installation and development of Flutter applications on your Raspberry Pi. This Bash script automates the process of setting up the Flutter environment, installs essential files and dependencies, and offers additional features like running your Flutter apps in **kiosk** mode.

With **raspi-flutter**, you can effortlessly configure your Raspberry Pi for Flutter app development and create immersive user experiences by running your apps in kiosk mode.


## Prerequisites

Before running the installer script, ensure you have the following prerequisites:

- **Raspberry Pi 4 with Raspberry pi OS 64-bit** (Raspbian)
- **Bash shell** (version 4.0 or higher) - by default is available
- **Curl** - by default is available

## Kiosk Mode Result
https://github.com/Snapp-X/raspi-flutter/assets/47558577/f580b1e8-e295-453a-8894-e03f2d9d67fc


## Getting Started

To quickly install `raspi-flutter` on your Raspberry Pi, open a terminal and simply run the following command:

```bash
bash <(curl -fSL https://raw.githubusercontent.com/Snapp-X/raspi-flutter/main/installer.sh) && source ~/.bashrc
```
## Usage

Once `raspi-flutter` is installed on your Raspberry Pi, you can use it by simply running the desired command in your terminal. Here are the available commands:

- **doctor**: Check the installation status and dependencies.
- **install**: Install Flutter and set up the environment.
- **uninstall**: Uninstall Flutter (Note: Uninstallation is not implemented yet).
- **kiosk**: Run a Flutter app bundle in kiosk mode.
- **disable_kiosk**: Disable the kiosk mode.
- **autologin**: Enable auto login on your device.
- **disable_autologin**: Disable auto login on your device.

For example, to check the installation status, kiosk mode state, and dependencies, simply run:

```bash
raspi-flutter doctor
```

## Install Flutter Environment

The "install" command in `raspi-flutter` automates the installation of Flutter on your Raspberry Pi and prepares the environment for Flutter app development. Here's what it does:

- **Installs Linux Dependencies**: It ensures that essential Linux packages, such as `curl`, `git`, and more, are installed on your Raspberry Pi.

- **Clones Flutter from GitHub**: fetches the Flutter repository from GitHub and places it in your specified directory.

- **Sets Up PATH**: It configures your system's PATH environment variable to include the Flutter binary directory, making the `flutter` command globally executable.

- **Installs Development Dependencies**: it installs necessary Linux development dependencies required for Flutter app development, including compilers and libraries.

- **Chooses Flutter Channel**: You can specify your preferred Flutter channel (e.g., stable, beta) to ensure you're using the desired Flutter release.

- **Runs Flutter Doctor**: This command checks your Flutter installation and displays any missing components or configuration issues.

- **Precaches Assets**: It precaches Linux-specific assets, ensuring a smooth development experience.

To use the "install" command, simply follow the Getting Started section in this README and run:

```bash
raspi-flutter install
```
## Kiosk Mode

`raspi-flutter` allows you to run your Flutter app in a kiosk mode on your Raspberry Pi, ensuring a seamless and focused user experience. To enable kiosk mode, follow these steps:

1. **Build Your Flutter App**: Ensure you have built your Flutter app for the Linux platform in release mode. You can use the following command to generate the app bundle:

```bash
 flutter build linux --release
```
1. **Enable Kiosk Mode**:To run your Flutter app in kiosk mode, use the following command, replacing `<file_path>`  with the exact path to the Flutter app bundle you built in step 1:

```bash
raspi-flutter kiosk <file_path>
```

For example:

```bash
raspi-flutter kiosk /home/pi/app/build/linux/arm64/release/bundle/app
```
Ensure that the specified file path exists, points to an executable file, and is the path to your Flutter app bundle.

**Auto Login**: 
Kiosk mode typically requires auto login on your Raspberry Pi. If auto login is not already enabled, raspi-flutter will enable it for you.

You can also enable the auto login manually, by using the following command:

```bash
raspi-flutter autologin
```

**Disable Kiosk Mode (Optional)**:

To disable the kiosk mode and return your Raspberry Pi to a standard desktop environment, follow these steps:

1. **Exit Full-Screen Mode**:
   If your Raspberry Pi is currently in full-screen kiosk mode, you need to exit this mode before disabling kiosk mode. You can typically exit full-screen mode by pressing `Alt+F4`(Close the app) or `F11`(Exit Fullscreen mode).

2. **Disable Kiosk Mode**:
   Open a terminal on your Raspberry Pi and execute the following command to disable kiosk mode:

```bash
raspi-flutter disable_kiosk
```


This command will remove the kiosk-related settings and restore your desktop environment.

Please note that enabling kiosk mode may affect the default behavior of your Raspberry Pi desktop environment. Ensure you have a backup or can access your Raspberry Pi via SSH in case you need to make any adjustments.


## Contributing

If you encounter any issues with the installer script or have suggestions for improvements, please [open an issue](https://github.com/yourusername/your-repo/issues). You are welcome to contribute to the development of this project by forking the repository and submitting pull requests.

## License

This project is licensed under the MIT License

