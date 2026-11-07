## Install and Configure XFCE Desktop with X11 on Ubuntu

Follow these steps to install the XFCE desktop environment and configure Ubuntu to use X11 instead of Wayland.

### 1. Install XFCE and Xorg

Open the terminal and execute the following commands:

```bash
sudo apt update
sudo apt install xfce4 xfce4-goodies xorg
```

During installation, if prompted to select a display manager, choose **lightdm**.

### 2. Disable Wayland

Open the GDM configuration file:

```bash
sudo nano /etc/gdm3/custom.conf
```

Locate the `[daemon]` section and add or uncomment the following line:

```ini
WaylandEnable=false
```

Save the file and exit the editor.

### 3. Switch to the XFCE Desktop

1. Sign out of your current desktop session.
2. At the login screen, click the **gear icon**.
3. Select **Xfce Session**.
4. Log in with your credentials.

### 4. Reboot the System

Restart your system:

```bash
sudo reboot
```

### 5. Verify the Display Server

After logging in, open the terminal and execute:

```bash
echo $XDG_SESSION_TYPE
```

Expected output:

```text
x11
```

**Note:** XFCE normally uses X11 by default. If you select LightDM instead of GDM3, modifying `/etc/gdm3/custom.conf` is generally unnecessary because LightDM does not use that configuration file.
