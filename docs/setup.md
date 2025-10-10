# 1) VirtualBox
  ## a) 

# 2) Kali Linux
   ### a) Download ISO
   Visit the official Kali Linux Website and go to Kali Linux Downloads page (https://www.kali.org/get-kali/#kali-installer-images)
   Recommended - select 'Installer' to download ISO for 64-bit systems
  ### b) Create VM
   Assuming you have VirtualBox already installed, select 'New'
   Configure VM settings - name your VM
   allocate at least 2 GB of RAM
   choose 'create a virtual hard disk now', choose 'dynamically allocate', and set size of hard disk to 20+ GB
  ### c) Verify Kali Linux ISO is mounted
   Click on 'Settings'
   Click on 'Storage' tab
   Under 'Controller: IDE' section click on empty disk icon
   On right side, click disk icon next to 'Optical drive' and select 'Choose a disk file'
   Browse location of Kali Linux ISO you downloaded earlier and select it
   Ensure that the "Adapter 1" is attached to 'NAT' for internet access
  ### d) Start VM and install Kali Linux
   click 'Start' to boot VM
   When you see the boot menu, click 'Graphical install' and press enter
   Follow Installation Prompts (recommended for partition disks - choose 'Guided - use entire disk')
  ### e) post-installation - login with your credentials you setup during the installation prompts
  ### Troubleshooting
  #### Fixing missing APT sources on Kali Linus
  If you see this error when running 'sudo apt update': 'Notice: It seems you don't have any APT data sources configured'
  Type 'sudo nano /etc/apt/sources.list'
  Type 'deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware' in the file
  Save and exit nano file
  Type 'sudo apt update' to test it
