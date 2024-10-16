<div align="center">

# ASCII Art with Figlet and Lolcat on Ubuntu

<img src="/images/artascii.png" width="90%"/>

</div>

### Step-by-step guide to adding a bit of flair to your terminal using **Lolcat** and **Figlet**.

---

### 1. Update and Upgrade your system

First, ensure your system is up to date with the following command:

```bash
sudo apt update && sudo apt upgrade
```

### 2. Install Lolcat and Figlet

Install the required packages to add colorful ASCII art to your terminal:

```bash
sudo apt install lolcat figlet
```

### 3. Add More Fonts for Figlet

To access additional fonts for Figlet, follow these steps:

Navigate to the **/usr/share** directory:

```bash
cd /usr/share
```

Clone the Figlet fonts repository:

```bash
git clone https://github.com/xero/figlet-fonts
```

Move the fonts into the Figlet directory and clean up:

```bash
mv figlet-fonts/* figlet && rm -rf figlet-fonts
```

---

### 4. Check Available Fonts

To list all the available fonts, use the following command:

```bash
showfigfonts
```

---

### 5. Display ASCII Art

To create and display ASCII art with Lolcat and Figlet, use the command below. Replace `"yourtexthere"` with the text you'd like to display and `fontname` with the name of the font you want (find these using `showfigfonts`).

```bash
figlet -f fontname "yourtexthere" | lolcat
```

---

### 6. Add ASCII Art to Your Terminal on Every Clear Command

If you want the ASCII art to appear every time you clear the terminal, follow these steps:

1. Navigate to `/etc`:

    ```bash
    cd /etc
    ```

2. Open the `.bashrc` file for editing:

    ```bash
    nano .bashrc
    ```

>[!NOTE]
If you're using ***zsh Shell*** open whit the next command
```bahs
nano ~/.zshrc
```
.
3. Add the following function at the end of the script. Replace `"fontname"` with your desired font and `"yourtext"` with the text you want to display.

    ```bash
    clear() {
        command clear
        echo -e "\033[30m$(figlet -f fontname -c "yourtext")\>
    }
    ```

---

### 7. See it in Action!

Now, whenever you type `clear` in your terminal, the ASCII art will be displayed at the top, giving your terminal a unique and colorful look!

---

Enjoy customizing your terminal with style!

