# Custom Fonts Installation Script

This script automates the installation of custom fonts that are downloaded from internet. Manual installation taking extraction of file, moving fonts folder to directory depending on user specific or system wide font installation, and cleaning up scraps like original zip files. This script simplifies that process.

## Prerequisites

### Give permissions

#### unzip tool should be present
```sh
sudo pacman -S unzip
# OR
sudo apt-get install unzip
# OR use any other package manager compatible with your system
```

You have to give executable permission
```sh
chmod +x installFonts
```
alternatively, you can use `bash` keyword before script to execute it
```sh
bash installFonts 
```

### optional
You can move script to your scripts directory and export that path to bash, zsh, etc.
```sh
cd ~
mkdir scripts
cd scripts
git clone https://github.com/47seconds/reconnectBluetooth.git
mv installFonts/installFonts .
rm -rf installFonts
vim ~/.bashrc
# add this at last line: export PATH=$HOME/scripts:$PATH
# :wq to save and exit vim
source ~/.bashrc
```
Now you can access this script from anywhere.

## Usage

#### Get help:
```sh
./installFonts -h
# OR
./installFonts --help
```

#### To install fonts user specific:
```sh
./installFonts [.ZIP FONT FILE 1] [.ZIP FONT FILE 2] [...]
# OR
./installFonts -l [.ZIP FONT FILE 1] [.ZIP FONT FILE 2] [...]
#OR
./installFonts --local [.ZIP FONT FILE 1] [.ZIP FONT FILE 2] [...]
```

#### To install fonts system-wide:
```sh
./installFonts -g [.ZIP FONT FILE 1] [.ZIP FONT FILE 2] [...]
# OR
./installFonts --global [.ZIP FONT FILE 1] [.ZIP FONT FILE 2] [...]
```

## Notes
- **Paths:** User specific fonts will be installed at `~/.local/share/fonts/` and System-wide fonts will be installed at `/usr/share/fonts/`.
- **System-wide Install:** make sure to add `sudo` for system-wide font installations.
- **Execution Ease:** You don't need `./` if added script path to shell path.