# 📜 LaTeX on Windows

Learn how to get started with writing LaTeX on Windows. This guide assumes a [Windows 10 or 11](https://www.microsoft.com/en-us/software-download/) and a [Visual Studio Code](#%E2%8C%A8%EF%B8%8F-visual-studio-code) installation.

## ⌨️ Visual Studio Code

We will be using [Visual Studio Code](https://code.visualstudio.com/), the most popular code editor out today, along with some extensions:

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python): Support extension for Python
- [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl): Virtual environment integration with WSL
- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop): Support extension for LaTeX

## 🪟 WSL

As per the official Microsoft description, "The Windows Subsystem for Linux lets developers run a GNU/Linux environment." Put into simple terms, you can use a Linux environment without waiting an hour for your dual-boot or VM configuration to load. Still confused? Check out [this video](https://www.youtube.com/watch?v=-atblwgc63E).

### ⤵️ Install

We'll be using version `2` since it's supposedly faster. You can check out the official Microsoft Comparison [here](https://docs.microsoft.com/en-us/windows/wsl/compare-versions). Install and configure with:

```pwsh
wsl --install
wsl --set-default-version 2
```

### 💡 Enable

A simple installation isn't enough, so you'll need to enable a feature to use WSL.

- Navigate to `Task Manager` through <kbd>🪟</kbd> or with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Esc</kbd>.
  - Make sure `Virtualization` is enabled in the `CPU` section of your task manager's `Performance` page
- Navigate to `Turn Windows features on or off` through the Windows search bar
- Enable `Windows Subsystem for Linux` if it isn't already

Now go ahead and reboot your computer.

## 🐧 Ubuntu

The most popular and beginner-friendly Linux distribution out there, Ubuntu has collaborated with Microsoft to make WSL possible. This is the Linux distribution that we'll be running atop WSL.

### ⤵️ Install

Install Ubuntu from the [Microsoft Store](https://apps.microsoft.com/store/detail/ubuntu/9PDXGNCFSCZV). Once finished, enter Ubuntu through the <kbd>🪟</kbd>, and it'll bring up a window and start installing the distribution.

Once finished, launch the app and run its installation course. Then you'll be prompted to enter a username, which you can just set to your Windows username, or whatever you like. Same goes for your password, although it's advisable to keep this the same as your Windows password so you don't have to reach for a sticky note or use your brain every time. Your **keyboard won't output** to the screen while you type out your password, as this is an intentional feature to keep your credentials secure.

⚠️ If you can't type out a username, or it's automatically set as `root`, run the following in PowerShell (retrieved from [issue](https://github.com/microsoft/WSL/issues/8736)) to briefly reinstall and re-enter a username.

```pwsh
wsl --unregister Ubuntu
ubuntu install --ui=none
```

## 🖊️ LaTeX

### ⤵️ Install

Install the tools to compile LaTeX locally with:

```bash
sudo apt update
sudo apt install texlive-full -y
```

Now start a LaTeX project with:

```bash
mkdir ~/proj && cd $_
touch main.tex && code .
```

Edit your `main.tex` file with a template from [Overleaf](https://www.overleaf.com/latex/templates), and simply save for the LaTeX Workshop extension to compile it into a PDF. Check out [autoCV](https://github.com/jitinnair1/autoCV) to set up CI/CD to push edits to your online portfolio/site.
