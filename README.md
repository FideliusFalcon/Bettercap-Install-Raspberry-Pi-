# Bettercap installation on Raspberry Pi
## Install Golang
**Update the available the packages and install them**  
$sudo apt-get update && sudo apt-get upgrade -y  

**Install golang (This will not install the newest version, but it suit our need)**  
$sudo apt-get install golang  

**Set path**  
$export GOPATH=$HOME/go  
$export PATH=$PATH:$GOROOT/bin:$GOPATH/bin  

**Write these paths into the profile at the bottom of the document**  
$sudo nano ~/.profile  

## Install bettercap dependencies
$sudo apt-get install build-essential libpcap-dev libusb-1.0-0-dev libnetfilter-queue-dev

## Install bettercap
**Download bettercap**  
$go get github.com/bettercap/bettercap

**Install bettercap**  
$cd $GOPATH/src/github.com/bettercap/bettercap  
$make build  
$sudo make install  

## Update caplets and install ui
**Start bettercap**  
$sudo bettercap  

**Update caplets**  
$caplets.update   
$ui.update   
