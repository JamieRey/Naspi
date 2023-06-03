## README

# Instalation Guide

1. Use the raspberry pi [imager](https://www.raspberrypi.com/software/) to install the OS, OS Lite (64 bit). Enable wifi & ssh through the advanced options on the imager by clicking on the settings cog.

2. Use your wifi router to find the IP address of your NasPi. Then SSH into it.
```bash
ssh user@ip.address
```

3. Run the argon eon install script to provide the software to run the cases LCD screen.
```bash
curl https://download.argon40.com/argoneon.sh | bash
```

3. Run the [openmediavault raspberry pi install script](https://github.com/OpenMediaVault-Plugin-Developers/installScript#installation).
```bash
sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```

# Resources

## Repositories

- [openmediavault](https://github.com/openmediavault/openmediavault)
- [openmediavault-installScript](https://github.com/OpenMediaVault-Plugin-Developers/installScript)

## Manuals

- [Argon EON](https://cdn.shopify.com/s/files/1/0556/1660/2177/files/FOR_PRINT_EON_INSTRUCTION_MANUAL_20211215.pdf?v=1646124298)
