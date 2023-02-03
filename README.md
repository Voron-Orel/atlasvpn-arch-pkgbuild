# purevpn-cli-pkgbuid
Building the PureVPN-cli package and fix for installation on ArchLinux

# Usage:
```
git clone https://github.com/Voron-Orel/purevpn-cli-pkgbuid.git
cd purevpn-cli-pkgbuid
makepkg -s
sudo pacman -U *.pkg.tar.zst 
sudo mv src/{pured-linux-x64,purevpn-cli} /usr/bin/
sudo systemctl restart pured.service
purevpn-cli --help
```
