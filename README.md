# 2squared

Big LED trees with blinky blinks

## Docs

* Engine: [LX](http://heronarts.com/lx/api/index.html)

## Installation

* Download [Processing](https://processing.org/download/?processing)
  * You will need to download version 2 of Processing
* Install [LibNFC](http://nfc-tools.org/index.php?title=Libnfc#Installation) (On Mac OS X, I recommend Homebrew; see below)
* Clone this repo (or download the zip)
* Open `Trees.pde` in Processing and run the sketch

#### Mac OS X LibNFC Install

* Install Homebrew: `ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`
* Do all the brewy stuff by running: `brew doctor`
* Install libnfc: `brew install libnfc`

#### Other OS X stuff

###### To Make NFC actually work

OS X has smart card reader integration and automatically launches pcscd every time a smartcard reader device is connected. This conflicts with the libnfc-based driver, which is much faster than a pcscd based-tag reader. You can work around this by killing pcscd manually, or you can prevent pcscd from starting.

To prevent pcscd from starting, edit `/System/Library/LaunchDaemons/com.apple.securityd.plist` and add:

`-soff`

below:

`/usr/sbin/securityd-i`

and reboot the system.

###### To get rid of crazy logging

Additionally, the config file for libnfc can be found at: `/usr/local/Cellar/libnfc/1.7.0/etc/nfc/libnfc.conf`

add: `log_level=0 `to this file to disable the verbose error logging.
