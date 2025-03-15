
## Install golang
The golang version from APT is pretty old, instead find the newest version on the [Go download page](https://go.dev/dl/)
If you're running 32 bit then use arch ARMv6 otherwise ARM64, copy the url, eg: `https://go.dev/dl/go1.24.1.linux-arm64.tar.gz`

Download and extract go
```
cd ~
wget https://go.dev/dl/go1.24.1.linux-arm64.tar.gz && sudo tar -C /usr/local -xzf go1.24.1.linux-arm64.tar.gz
```
Add the go binary path:
```
nano ~/.profile
```
Insert following
```
PATH=$PATH:/usr/local/go/bin
GOPATH=$HOME/go
```
Update your current shell with the configuration
```
source ~/.profile
```
Validate go is installed
```
go version
```

## Download and build bettercap
Install bettercap dependencies
```
sudo apt update && sudo apt install git build-essential libpcap-dev libusb-1.0-0-dev libnetfilter-queue-dev
```
```
cd ~ && git clone https://github.com/bettercap/bettercap.git && cd bettercap && make build
```
Install
```
sudo make install
```

## Start bettercap
```
sudo bettercap
```
### Running the web-ui
Bettercap is already bundled with bettercap-ui, but the caplet `http-ui` doesn't work probably. Instead we create our own.
Add the content of [better-ui.cap](FideliusFalcon/Bettercap-Install-Raspberry-Pi-/better-ui.cap) to `/usr/local/share/bettercap/caplets/better-ui.cap`

Start bettercap with the ui
```
sudo bettercap -caplet better-ui
```
\* This will only listen on localhost (127.0.0.1). If you're accessing bettercap remotely, remember to set the address
