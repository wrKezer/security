**the web3 Security Audit**

##### [Extreme Measure](#extreme-measures) : Separating everything with already hardened laptops. You can DIY your laptop like that, but it needs tons of time and research, so if you like this stuff, it is always good to know but not recommended for non-tech people. 

##### [General Usage Tips](#general-part) : General usage suggestions applied to all computers and operating systems. BUT I will not suggest using Windows. Linux > MacOS > Windows. If you have to use windows, consider using VM or dual boot for your important needs.

##### [Settings](#setings) : Settings for freshly installed Ubuntu, Macos and firefox.

##### [Home network](#my-home-setup) : My personal suggestions and usage for home network.


---
### Extreme measures

The easiest way to be secure is not to be at any target. 

For everyday computer usage, people visit tons of websites and install tons of apps, and with every click, they increase the possibility of being a target. If you click on any phishing link or any decoy website, everything is already done; these security measures are useless.

So the ultimate solution will be a separate computer for trading or banking stuff and not using that computer for personal use.

Here is the list for that:
- Buy [insurgo](https://insurgo.ca/), or [System 76 Lemur](https://system76.com/laptops/lemur) laptop.
- If you don't want to buy something like that, you can just gather a laptop that you can disable Intel ME. (Lenovo x230 is the best bet) with min 16GB of RAM, and do some research to improve the security and privacy of that laptop.
- Install Qubes OS; if it is a little hard for you, Ubuntu is also a great alternative. For Qubes, check for the recommended computer.
- Create a couple of Qubes, personal, trade, vault:
- These can be seen as different operating systems on your computer which cannot connect.
- On trade Qube, you will only install firefox, and metamask. Mic and Cam will be disconnected, and it will have a connection to the internet. This can go through VPN + Tor network. Or, if you do not want to deal with Catcha stuff, it can be Tor + VPN.
- Vault will be an offline Qube; it will not connect to the internet in any way. It will have Keepassxc in it so that you can store your password or keys for any kind. As it is always offline, you will not need to worry.
- The personal one is for your daily needs; it is better to use the internet with it via VPN as well.

---
### General Part

General is for everyone. It is about general computer use to be safe, and a lot of this info can be applied to Metamask usage.

- Disable Bluetooth when you don't use it.
- Disable Wifi when you don't use it.
- Use BIOS password.
- Enable Hard Disk encryption.
- Do not click on any link you see on the internet; you can never be sure if the other person or computer is compromised.
- Use 2FA. Preferably hardware one like Yubikey. It is easier to use, faster, and more secure. Just do not forget to have a spare one.
- Using firefox is the best bet. I will share some settings in the [Settings](#setings) part.
- Use this Firefox only for trading, nothing else. So that even when something wrong happens, you won't be on your main browser.
- Always use a hardware wallet. This is of course, not the safest, but paper wallets are harder to withdraw. 
- Only send what you need to your hot wallet. Always assume it can always be hacked, so do not have more than you can lose on your hot wallet.
- Use secure mail providers like [Protonmail](https://protonmail.com/).
- Your daily and trading browser should be different, and do not install any unnecessary extensions. 
- 99% of the hacks happen because of user error, do not forget that.
- Never store your seed phrases backup codes online or even on your computer. Only write them on paper, and store them accordingly.
- If you have to write them on the computer, then transfer your funds to new wallet, and ditch the old one.

---
### Setings:

#### When you install Ubuntu, which is the easiest of Linux Distros, I do use these commands:
```
# Update and some cleaning
sudo apt purge -y apport
sudo apt remove -y popularity-contest
sudo apt autoremove -y

# Installing bleachbit and Keepassxc
sudo apt update
sudo apt install bleachbit
sudo snap install keepassxc
sudo apt update
sudo apt upgrade

# Installing ProtonVPN
cd Downloads
wget https://protonvpn.com/download/protonvpn-stable-release_1.0.0-1_all.deb

- Open the Files application
- Navigate to "Downloads"
- Right-click the downloaded file
- Choose "Open with Software Install"
- Click the button to install the software

- In Terminal:
sudo apt-get update
sudo apt-get install protonvpn -y
sudo apt install gnome-shell-extension-appindicator gir1.2-appindicator3-0.1 -y
reboot

# Visual settings
settings set org.gnome.desktop.background picture-uri ''
gsettings set org.gnome.desktop.background primary-color 'rgb(66, 81, 100)'

# Installing Virtualbox
sudo apt update
sudo apt install virtualbox virtualbox-ext-pack -y
sudo apt update
sudo apt install -y build-essential dkms gcc make perl
sudo rcvboxadd setup
reboot
```

#### For MacOS
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew analytics off

brew install taskexplorer
brew install knockknock
brew install little-snitch
brew install oversight
brew install onyx
brew install virtualbox //For newer M1 Macbooks, brew install --cask parallels
brew install carbon-copy-cloner
brew update
brew upgrade
brew cleanup -s
brew autoremove 

```

#### In the firefox:
In settings:
```
Disable *Enable Picture-in-picture video controls*
Set home pages to black page
Disable all Home Content
Set your default search engine to DuckDuckGo and disable the links of others.
Disable *Provide search suggestions*
Set Enhanced Tracking Protection to *strict*
Enable *Delete cookies and site data when Firefox*
Disable Ask to save logins and password for websites
Disable keeping history
Block permissions for location, camera, microphone and notifications
Disable Firefox Data Collection and Usa
Enable HTTPS-Only Mode in all windows.
```
Then open about:config
```
geo.enabled: FALSE
browser.safebrowsing.malware.enabled: FALSE
dom.battery.enabled: FALSE
extensions.pocket.enabled: FALSE
browser.newtabpage.activity-stream.section.highlights.includePocket: FALSE
browser.newtabpage.activity-stream.feeds. telemetry: FALSE
browser.ping-centre.telemetry: FALSE
toolkit.telemetry.server: (Delete URL)
toolkit. telemetry enabled: FALSE
toolkit.telemetry.unified: FALSE
devtools.onboarding.telemetry.logged: FALSE
media.autoplay.default: 5
dom. webnotifications.enabled: FALSE
webgl.disabled: TRUE
network.http.sendRefererHeader: O
identity.fxaccounts.enabled: FALSE
browser.tabs.crashReporting.sendReport: FALSE
pdfis.enableScripting: FALSE
network.dns.disablePrefetch: TRUE
network.dns.disablePrefetchFromHTTPS: TRUE
network.prefetch-next: FALSE
```
---
#### My home setup

- **Insurgo laptop with Qubes OS**
```
- Trading: Has only firefox installed with metamask. All important links are already bookmarked. It goes through Tor + VPN (dedicated IP) so that I don't always see captcha errors.
- Vault: All my licenses, passwords, and everything is stored here, with no internet connection. Even if this is compromised, there is no problem as I use 2fa for all critical accounts.
- Personal: For general usage. It has firefox, signal, Veracrypt. Connects to the internet via VPN.
```

- **M1 Macbook** laptop with Ubuntu installed as VM, all trading is inside of that VM
```
- Little snitch blocking all iCloud and apple services, also checking what is going on. Setup can be a little tricky, but it will be worth it
- If you do not want to pay, you can use Lulu
- I do not use icloud, as none of the cloud services can be safer than being offline.
- Regular backups with Carbon Copy Cloner
- Klockknock to check what is going on in the computer; it is an open-source app to see what is running.
- I use brew to install almost everything; as I don't have iCloud account, I cannot use the app store.
- FileVault enabled
```

- **Protectli pfSense Router**
```
- The whole network goes through it
- ProtonVPN is always one; if it gets disconnected, it cannot connect to the internet. It connects to the closest server, so there is almost no speed loss.
- Cloudflare DNS is enabled within
- Using the service_watchdog Package to ensure that VPN is always working; if there is a problem, this will restart it.
```

- **Browser addons**
```
- uBlock
- unhook for youtube
- Multi-account containers
```

- **General Tips**
```
- Use Simplelogin to hide my real email address.
- Use signal for communication.
- Protonmail is the main mail service.
- Use strongbox app on the phone to see keepassxc database (copying it with cable, not online) and block its internet connection.
- Authy or ubikey 2fa.
- Using Firefox Focus as a mobile browser
```

---

This guide is still in the making.
You can reach me via wrkezer@pm.me
