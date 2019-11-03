# This amazing terminal in Windows 🔥

<img src="https://i.imgur.com/E7GdYni.png">

To achieve this result there quite many steps:

1. Install Linux 🐧 subsistem on Windows
2. Install the new Windows Terminal
3. Install zsh and oh-my-zsh
4. Install custom fonts (Nerd fonts)
5. Install powerlevel9k and change the configuration
6. Change the Windows terminal color scheme
7. Remove the highlited color of the folders

----

## Install Linux 🐧 subsystem on Windows

To install the linux subsystem on Windows you need to

###  **Turn on the subsystem in PowerShell**

Open Powershell as administrator and run this command:
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

### **Install your Linux distro from the Windows Store**
Navigate to the Windows Store and click on the distro of Linux you want to install. I suggest you to install Ubuntu. 

Once the download finishes, open the window and wait for the installation process to finish.


---

## 2. Install the new Windows Terminal
Simply go to the Windows Store and search for 'windows terminal'  or open [this.](https://www.microsoft.com/store/productId/9N0DX20HK701)

--- 

## 3. Install zsh and oh-my-zsh
Go to the Windows terminal open a new tab in Ubuntu and run this command

```bash
sudo apt-get install zsh
```

and than set **zsh** as the default shell with

```bash
chsh -s $(which zsh)
```

Now we need to install **oh-my-zsh**, a community-driven framework for managing the zsh configuration.

just simply run this command:


```bash
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


---

## 4. Install custom fonts

To install all the necessary fonts just run [this script ]()
This simple script gets the fonts and installs them.

---
## 5. Install powerlevel9k

To install this theme for use in Oh-My-Zsh, clone this repository into your OMZ custom/themes directory.

```bash
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```


You then need to select this theme in your ```~/.zshrc```:

```bash
ZSH_THEME="powerlevel9k/powerlevel9k"
```
We can now make our powerlevel9k theme, in this case we'll use mine that I took from github and modified. 

[Here]() you can copy it.

---

To change the Windows Terminal color scheme open the json configuration and add this to the colors
```json
{
        "name": "Andromeda",
        "black": "#000000",
        "red": "#cd3131",
        "green": "#05bc79",
        "yellow": "#e5e512",
        "blue": "#2472c8",
        "purple": "#bc3fbc",
        "cyan": "#0fa8cd",
        "white": "#e5e5e5",
        "brightBlack": "#666666",
        "brightRed": "#cd3131",
        "brightGreen": "#05bc79",
        "brightYellow": "#e5e512",
        "brightBlue": "#2472c8",
        "brightPurple": "#bc3fbc",
        "brightCyan": "#0fa8cd",
        "brightWhite": "#e5e5e5",
        "background": "#262a33",
        "foreground": "#e5e5e5"
}
```
and paste this in profiles:

```json
{
        "startingDirectory": "C:/Users/YOUR-NAME/Desktop",
        "guid": "{09dc5eef-6840-4050-ae69-21e55e6a2e62}",
        "name": "Ubuntu",
        "colorscheme": "Andromeda",
        "historySize": 9001,
        "snapOnInput": true,
        "cursorColor": "#FFFFFF",
        "cursorShape": "bar",
        "commandline": "wsl.exe",
        "fontFace": "MesloLGS NF",
        "fontSize": 12,
        "acrylicOpacity": 0.95,
        "useAcrylic": true,
        "closeOnExit": false,
        "padding": "0, 0, 0, 0",
        "icon": "ms-appdata:///roaming/ubuntu-32.png"
}
```
---

## 7. Remove the highlited color of the folders


Add this to yout ```.zshrc``` configuration

```bash
export LS_COLORS="$LS_COLORS:ow=1;34:tw=1;34:"
```