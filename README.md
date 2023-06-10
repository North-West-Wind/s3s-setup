# s3s-setup
Setup and helper script for [splatnet3statink (s3s)](https://github.com/frozenpandaman/s3s) by frozenpandaman.

## Usage
Refer to [s3s](https://github.com/frozenpandaman/s3s#usage-) for normal s3s usage.

This script adds an extra function for copying the `gtoken` for browsing SplatNet3 in a browser instead of the NSO app.
```
$ s3s [-g] [-x] [-f]
```
The `-g` flag prints the `gtoken` from `config.txt` to the console.  
The `-x` flag can only be used with the `-g` flag. It uses `xclip` to copy the `gtoken` to clipboard instead of printing it on screen.  
The `-f` flag has no relationship with `gtoken`. It should only be used if the installation of `s3s` is messed up. The path of installation is `~/.config/s3s/`.

## Install
Arch Linux users can install this script from the AUR. It is named `s3s-setup`.

For other Linux users, you can install this manually.
### Prerequisites
- Python 3

### Instructions
1. Clone this repo using `git clone https://github.com/North-West-Wind/s3s-setup` or download it as a ZIP and extract it.
2. Copy `s3s` to `~/.local/bin/` for user-only installation, or copy it to `/usr/local/bin/` for system-wide installation.
3. Run `s3s` in the terminal. You will be asked to setup s3s for the first time. Follow those instructions.
4. After setup, you can use s3s with a simpler command `s3s <arguments>`.

(The following instructions are optional, and only works for systems using systemd)  
(This is a systemd service that automatically starts uploading battles when user logins)  
1. Copy `s3s-monitor.service` to `~/.config/systemd/user/` for user-only installation, or copy it to `/etc/systemd/user/` for system-wide installation.
2. Run `systemctl --user daemon-reload` in the terminal to reload the services.
3. Run `systemctl --user enable --now s3s-monitor.service` in the terminal to enable and start the service.
4. Your battles will be uploaded every 5 minutes and the script will update itself.

## License
GPLv3
