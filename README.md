# DIY AI Robot with Home Assistant + ChatGPT + ElevenLabs

This project brings together Home Assistant, ChatGPT, and ElevenLabs to create a talking, blinking, 3D-printed AI robot powered by a Raspberry Pi.

---

## 🛠️ Home Assistant Supervised Installation (on Raspberry Pi OS Lite)

> These commands install Docker, required dependencies, and Home Assistant Supervised (non-OS version).

```bash
sudo apt update && sudo apt upgrade -y

sudo apt install -y software-properties-common apparmor-utils apt-transport-https ca-certificates curl dbus jq network-manager systemd-journal-remote systemd-journal-gateway docker.io

sudo systemctl enable NetworkManager
sudo systemctl start NetworkManager

curl -Lo os-agent.deb https://github.com/home-assistant/os-agent/releases/latest/download/os-agent_1.6.0_linux_aarch64.deb
sudo dpkg -i os-agent.deb

curl -Lo installer.sh https://raw.githubusercontent.com/home-assistant/supervised-installer/master/installer.sh
sudo bash installer.sh --machine raspberrypi4
```

After install, HA will be available at `http://<your_pi_ip>:8123`

---

## 🖥Display Configuration (`/boot/firmware/config.txt`)

Add these three lines to enable the 3.5" SPI TFT display:

```ini
dtoverlay=piscreen,rotate=270,speed=32000000,fps=20
framebuffer_width=480
framebuffer_height=320
```

Then reboot:

```bash
sudo reboot
```

---

## API Services

- 🔗 OpenAI API Key: https://platform.openai.com/account/api-keys  
- 🔗 ElevenLabs API Key: https://www.elevenlabs.io/api

---

## Components Used

- Raspberry Pi 4 (4GB or higher recommended)  
- 3.5-inch SPI TFT Display  
- USB Microphone  
- USB Speaker  
- 3D Printed Robot 
- 5V Fan  
- Jumper wires, magnets  
- Raspberry Pi OS Lite 
- Home Assistant Supervised  
- Flask (for custom expression API)

---
