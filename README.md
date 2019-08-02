# backport-iwlwifi

I just recently bought a Dell XPS 15 2019 and installed Ubuntu 19.  The only issue I had with the transition was that WiFi was not working.  After scouring the internet for a possible solution,  I found found something that worked for me.


## How to install the driver
Download the source code:
`
git clone https://github.com/romeolorenzo/backport-iwlwifi.git
`

Run make with vendor commands disabled:
```
make defconfig-iwlwifi-public
sed -i 's/CPTCFG_IWLMVM_VENDOR_CMDS=y/# CPTCFG_IWLMVM_VENDOR_CMDS is not set/' .config
make -j4
```

Install the modules
`
sudo make install
`

Reboot


