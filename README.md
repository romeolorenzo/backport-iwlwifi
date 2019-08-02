# backport-iwlwifi

I just recently bought a Dell XPS 15 2019 and installed Ubuntu 19.  The only issue I had with the transition was that WiFi was not working.  After scouring the internet for a possible solution,  I found found something that worked for me.


## How to install the driver
Download the source code:<br />
`
git clone https://github.com/romeolorenzo/backport-iwlwifi.git
`

Run make with vendor commands disabled:<br />
```
make defconfig-iwlwifi-public
sed -i 's/CPTCFG_IWLMVM_VENDOR_CMDS=y/# CPTCFG_IWLMVM_VENDOR_CMDS is not set/' .config
make -j4
```

Install the modules<br />
`
sudo make install
`

Reboot



The origin site where I got this:
https://wireless.wiki.kernel.org/en/users/drivers/iwlwifi/core_release
