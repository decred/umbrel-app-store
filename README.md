# Decred App Store on Umbrel

Add this repository through the Umbrel user interface as shown in the following demo:

[![Watch the video](https://img.youtube.com/vi/4gcK-WYjqhc/maxresdefault.jpg)](https://www.youtube.com/watch?v=4gcK-WYjqhc)

## Or use the Umbrel CLI as described below

### Add app store

```sh
sudo ~/umbrel/scripts/repo add https://github.com/decred/umbrel-app-store/

sudo ~/umbrel/scripts/repo update
```

### Install Bison Wallet

```sh
sudo ~/umbrel/scripts/app install decred-dcrdex
```

### Remove this app store

```sh
sudo ~/umbrel/scripts/repo remove https://github.com/decred/umbrel-app-store/
```
