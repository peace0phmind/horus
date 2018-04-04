#Horus development in Mac OS X

[return to Home](../../README.md)


If you are a developer and you want to modify the code, contribute, build packages, etc. you may follow this steps

## 1. Set up the environment

### Tools

#### Install FTDI driver
* [FTDI USB Driver](http://www.ftdichip.com/Drivers/VCP/MacOSX/FTDIUSBSerialDriver_v2_3.dmg)

#### Atom IDE
Download open source [Atom code editor](https://atom.io/).

#### Install Homebrew
```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Git version control
```bash
brew install git
```

#### Python
use anaconda python 3

#### OpenCV
```bash
brew tap homebrew/science
brew info opencv
brew install opencv
```

```bash
ln -s /usr/local/Cellar/opencv/3.4.1_2/lib/python3.6/site-packages/cv2.cpython-36m-darwin.so 
/usr/local/Cellar/opencv/3.4.1_2/lib/python3.6/site-packages/cv2.so
ln -s /usr/local/Cellar/opencv/3.4.1_2/lib/python3.6/site-packages/cv2.so $HOME/anaconda3/lib/python3.6/site-packages
```

#### wxPython
```bash
pip install wxpython
```

#### Python modules
```bash
pip install -U pyserial pyopengl pyopengl-accelerate numpy scipy matplotlib==1.5.3
```

##### Pyobjc QTKit

* Install Xcode.app. Then, switch xcode commands and accept the xcodebuild license

```bash
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
sudo xcodebuild
```

* Install qtkit
```bash
pip install -U pyobjc-core pyobjc-framework-cocoa pyobjc-framework-quartz pyobjc-framework-qtkit
```

In order to generate dmg package, some extra dependencies are needed

#### Packaging dependencies
```bash
pip install -U py2app
```

Also some patches are needed to make py2app work

## 2. Download source code

All source code is available on GitHub. You can download main Horus project by doing:

### Horus
```bash
git clone https://github.com/peace0phmind/horus.git
cd horus
```

## 3. Execute source code

In the project directory, execute the command:

```bash
pythonw horus
```

## 4. Build packages

Horus development comes with a script *package.sh*. This script generates a final release package. You should not need it during development, unless you are changing the release process. If you want to distribute your own version of Horus, then the *package.sh* script will allow you to do that.

```bash
bash package.sh darwin  # Generate dmg package
```
