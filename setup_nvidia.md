```
# 1. Basics
sudo apt install zsh
chsh -s $(which zsh)
exec zsh

sudo apt install git
sudo apt install build-essential
sudo apt install stow
sudo apt install curl


sudo apt install openssh-server

# Zerotier
curl -s https://install.zerotier.com | sudo bash
# Join Datarock Network
sudo zerotier-cli join 83048a0632210e4c


# Tailscale (Para debian 12 pero funciono para 13)
curl -fsSL https://pkgs.tailscale.com/stable/debian/bookworm.noarmor.gpg | sudo tee /usr/share/keyrings/tailscale-archive-keyring.gpg >/dev/null
curl -fsSL https://pkgs.tailscale.com/stable/debian/bookworm.tailscale-keyring.list | sudo tee /etc/apt/sources.list.d/tailscale.list
sudo apt-get update
sudo apt-get install tailscale

# 2. NVIDIA Driver + CUDA Toolkits
# cuda 12.8 + driver
# https://developer.nvidia.com/cuda-12-8-1-download-archive?target_os=Linux&target_arch=x86_64&Distribution=Debian&target_version=12&target_type=deb_local

wget https://developer.download.nvidia.com/compute/cuda/repos/debian12/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-8
sudo apt-get install -y cuda-drivers

# Estas siguientes lineas deberian estar en el .zshrc de lo contrario agregarlas:
# export PATH=/usr/local/cuda-12.6/bin${PATH:+:${PATH}}
# export LD_LIBRARY_PATH=/usr/local/cuda-12.6/lib64/${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

# 3. CuDNN
sudo apt-get -y install cudnn9-cuda-12

# Wezterm
curl -fsSL https://apt.fury.io/wez/gpg.key | sudo gpg --yes --dearmor -o /usr/share/keyrings/wezterm-fury.gpg
echo 'deb [signed-by=/usr/share/keyrings/wezterm-fury.gpg] https://apt.fury.io/wez/ * *' | sudo tee /etc/apt/sources.list.d/wezterm.list
sudo apt update
sudo apt install wezterm

# Google Chrome
sudo apt install wget gnupg software-properties-common
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo gpg --dearmor -o /usr/share/keyrings/google-chrome.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/google-chrome.gpg] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list
sudo apt update
sudo apt install google-chrome-stable

# VS Code
sudo apt install snapd
sudo snap install snapd
sudo snap install code --classic

# Jetbrains Toolbox es instalacion grafica
```
