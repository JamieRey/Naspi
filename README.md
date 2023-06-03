## README

# Instalation Guide

1. Use the raspberry pi [imager](https://www.raspberrypi.com/software/) to install the OS, OS Lite (64 bit). Enable wifi & ssh through the advanced options on the imager by clicking on the settings cog.

2. Use your wifi router to find the IP address of your NasPi. Then SSH into it.
```bash
ssh user@ip.address
```
If you run into this error
```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
```
then run this command below to generate a ssh key for your device on your network.
```bash
ssh-keygen -R <host>
```

3. Update & upgrade your packages.
```bash
sudo apt update
sudo apt upgrade
```

4. Run the argon eon install script to provide the software to run the cases LCD screen.
```bash
curl https://download.argon40.com/argoneon.sh | bash
```

5. Run the [openmediavault raspberry pi install script](https://github.com/OpenMediaVault-Plugin-Developers/installScript#installation).
```bash
sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```
you might need to add this flag
```bash
--no-check-certificate
```
then after you've rebooted, run this to check the install was sucessful
```bash
sudo omv-firstaid
```

# Customisations

# Open Media Vault

- Default credentials are admin:openmediavault
- Enable drives on network...
- Set up portainer... 
- Support homer as the homepage for the server by changing the port of omv by going to **System -> Workbench**

# Portainer

```bash
curl -sSL https://get.docker.com | sh
```
```bash
sudo usermod -aG docker username # Gives permission to user for docker
```
```bash
sudo docker pull portainer/portainer-ce:latest
```
```bash
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:latest
```

- Best list of images for homesetup
  - [Lissy93](https://github.com/Lissy93/portainer-templates) - `https://raw.githubusercontent.com/Lissy93/portainer-templates/main/templates.json`


# Resources

## Commands
```bash
argon-config
```
```bash
sudo reboot --reboot #(faster with flag)
````

## Repositories

- [openmediavault](https://github.com/openmediavault/openmediavault)
- [openmediavault-installScript](https://github.com/OpenMediaVault-Plugin-Developers/installScript)
- [alternative argon-eon](https://github.com/JeffCurless/argoneon)
- [Homer](https://github.com/bastienwirtz/homer)
- [Portainer template list](https://github.com/Lissy93/portainer-templates)

## Forums

- [r/selfhosted](https://www.reddit.com/r/selfhosted/)

## Manuals

- [Argon EON](https://cdn.shopify.com/s/files/1/0556/1660/2177/files/FOR_PRINT_EON_INSTRUCTION_MANUAL_20211215.pdf?v=1646124298)
