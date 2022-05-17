**the web3 Security Audit**

##### [Extreme Measure](#extreme-measures) : Separating everything with already hardened laptops. You can DIY your own laptop like that, but needs tons of time and research so if you like these stuff it is always good to know, but not recommended for non tech people. 

##### [General Usage Tips](#general-part) : General usage suggestions which can be applied to all computers and operating systems. BUT I will not suggest using Windows. Linux > MacOS > Windows. If you have to use windows, consider using VM or dual boot for your important needs.

##### [Settings](#setings) : Settings for freshly installed Ubuntu, Macos and firefox.

##### [Home network](#my-home-setup) : My personal suggestions and usage for home network.


---
### Extreme measures

Easiest way to be secure is not to be at any target. 

For everyday computer usage, people visit tons of websites, install tons of apps and with every click, we always incease the possibility of being target. If you click on any phising link, or any decoy website, everything is already done, all of these security measures are useless.

So the ultimate solution will be a separate computer for trading or banking stuff and not using that computer for any personal usage.

Here is the list for that:
- Buy [insurgo](https://insurgo.ca/), or [System 76 Lemur](https://system76.com/laptops/lemur) laptop.
- If you dont want to buy something like that, you can just gather a laptop that you can disable intel ME. (Lenovo x230 is the best bet) with min 16GB or RAM, and do some research to improve security and privacy of that laptop.
- Install Qubes OS, if it is a little hard for you, Ubuntu is also great alternative. For Qubes check for the recommendad computer.
- Create couple of Qubes, personal, trade, vault:
- These can be seen as different operating systems on your computer which cannot connect each other.
- On trade Qube, you will ony install firefox, and metamask. Mic and Cam will be disconnected, it will have a connection to internet. This can go through VPN + Tor network. Or if you do not want to deal with Catcha stuff, it can be Tor + VPN.
- Vault will be an offline Qube, it will not connect to internet in any way. It will have Keepassxc in it, so that you can store your password or keys for any kind. As it is always offline, you will not need to worry.
- The personal one is for your daily needs, it is better to use internet with it via VPN as well.

---
### General Part

This is for everyone. it is about general computer use to be safe, and a lot of info can be applied to Metamask usage.

- Disable bluetooth when you dont use it.
- Disable Wifi when you dont use it.
- Use BIOS password.
- Enable Hard Disk encryption.
- Do not click on any link you see on the internet, you can never be sure if the other person or computer is compromised.
- Use 2FA. Preferably hardware one like Yubikey. It is easier to use, faster, more secure. Just do not forget to have a spare one.
- Using firefox is the best bet, I will share some settings that I use in the [Settings](#setings) part.
- Use this Firefox only for trading, nothing else. So that even when something wrong happens you wont be on your main browser.
- Always use hardware wallet. This is of course not the safest, but paper wallets are harder to withdraw. 
- Only send what you need to your hot wallet, always assume it can always be hacked, so do not have more than you can loose on your hot wallet.
- Use secure mail providers like [Protonmail](https://protonmail.com/).
- Your daily and trading browser should be different and do not install any unnecessary extensions. 
- 99% of the hacks happen because of user error, do not forget that.
- Never ever store your seed phrases backup codes online, or even on your computer. Only write them on paper, and store it accordingly.
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
- Trading: Has only firefox installed with metamask. All important links are already bookmarked. Goes through Tor + VPN (dedicated ip) so that I dont always see captcha errors.
- Vault: All my licenses, passwords and everything is stored here, no internet connection. Even if this is compromised, there is no problem as I use 2fa for all of the important accounts.
- Personal: For general usage. It has firefox, signal, Veracrypt. Connects to internet via VPN.
```

- **M1 Macbook** laptop with Ubuntu install as VM, all trading is inside of that VM
```
- Little snitch blocking all icloud and apple services, also checking what is going on. Setup can be a little ticky, but it will worth it
- If you do not wanna pay, you can use Lulu
- I do not use icloud, as none of the cloud services can be safer than being offline.
- Regular backups with Carbon Copy Cloner
- Klockknock to check what is going on in the computer, it is a open source app to see what is running.
- I use brew to install almost everything, as I dont have icloud acc, I cannot use app store.
- FileVault enabled
```

- **Protectli pfSense Router**
```
- Whole network goes throuh it
- ProtonVPN is always one, if it gets disconnected, cannot connect to internet. It connects to closest server, so almost no speed loss.
- Cloudflare DNS is enabled within
- Using service_watchdog Package to be sure that VPN is always working, if there is a problem, this will restart it.
```

- **Browser addons**
```
- uBlock
- unhook for youtube
- Multi-account containers
```

- **General Tips**
```
- Using Simplelogin to hide my real email addres.
- Using signal for communication.
- Protonmail is the main mail service.
- Using strongbox app on the phone to see keepassxc database (copying it with cable, not online) and block its connection to internet.
- Authy or ubikey 2fa.
- Using Firefox Focus as mobile browser
```

---

This guide is still in the making.
You can reach me via wrkezer@pm.me
