# VEX Manim Animations

This repository contains a collection of **Jupyter Notebook-based Manim animations** designed for visualizing mathematical concepts related to **VEX Robotics** (Team 52800R). The animations aim to provide engaging and intuitive visualizations that help understand various mathematical principles that are used in 52800R's autonomous program.

*Powered by [Manim](https://www.manim.community/), the mathematical animation engine.*

![Example Manimation](./mainimations/media/ExampleManimation.gif)

## Table of Contents
1. [Features](#features)
2. [Getting Started](#getting-started)
   - [Method #1: Binder (Recommended)](#method-1-binder-recommended-no-installation-required)
   - [Method #2: Local Installation](#method-2-local-installation)
3. [Tips & Troubleshooting](#tips--troubleshooting)
4. [Contributing](#contributing)
5. [License](#license)

## Features
* Visual explanations of many aspects commonly used in VEX Robotics code
* Ready-to-run Jupyter notebooks with Manim `%%manim` magic
* Direct references to 52800R notebook entries

## Getting Started

Below are examples on how to set up this project for yourself.

### Method #1: Binder (recommended, no installation required):
1. Open Binder: https://bids.mybinder.org/
2. Paste the repository into the box: https://github.com/alfredoprograms/vex-manimations.git
![Binder Installation Screenshot](https://i.imgur.com/lH3i95b.png)
3. Press the launch button. This may take a few minutes.
4. You're all set to begin animating in Manim, all in your web browser!

### Method #2: Local Installation:
#### 1. Open a command line, and clone the repository:
```sh
git clone https://github.com/alfredoprograms/vex-manimations.git
cd vex-manimations
```
#### 2. Manim works best with **Python3.10**. Check your version:
```sh
python3 --version
```
If you need Python 3.10:
* Windows: Install from [python.org](https://www.python.org/)
* macOS:
```sh
brew install python@3.10
```
* Linux: Use your package manager. Example:
```sh
sudo apt install python3.10
```
#### 3. Install dependencies:
**Windows** (Chocolatey):
<br> Install Chocolatey, if needed:
```sh
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
<br>
Then install dependencies:

```sh
choco install ffmpeg
choco install gtk-runtime
choco install miktex
```

**MacOS**:
<br> Install Homebrew if you don't have it:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

<br> Then, install the required packages:

```sh
brew install ffmpeg cairo pango pkg-config
brew install --cask mactex
brew install dvisvgm ghostscript

export PATH="/Library/TeX/texbin:$PATH"
```

**Linux**:
<br> Simply run the following command:

```sh
sudo xargs -a apt.txt apt install -y
```
#### 4. Create a Conda Enviroment:
```sh
conda env create -f environment.yml
conda activate vex-manimations
```

If not using Conda, you can also use pip:
```sh
pip install manim numpy jupyterlab
```
#### 5. Use Jupyter Notebook
Add Manim to Jupyter configuration:

```sh
jupyter nbextension install --sys-prefix --overwrite --py manim
jupyter nbextension enable --sys-prefix --py manim
```
Finally:

```sh
jupyter notebook
```

You're all set for using Manim with VEX animations. Try to render a scene:
```py
%%manim -qm ExampleScene
class ExampleScene(Scene):
    def construct(self):
        self.play(Create(Square()))
```

## Tips & Troubleshooting
* Use `-qm` or `-qh` for faster/higher quality rendering
* First render may take longer
* If LaTeX fails &rarr make sure that full LateX distribution is installed and defined correctly in `PATH`

## Contributing
Feel free to open issues or pull requests with new animations!

## License
MIT License (see [LICENSE.md](LICENSE.md))