#! /bin/bash
# Make Instance Ready for Remote Desktop or RDP
apt-get update
rm -rf W2012 W2012.img W2012.gz ngrok ngrok.zip ng.sh > /dev/null 2>&1
echo "Download windows files"
wget -O Win2012.gz https://bit.ly/W2012.gz
gunzip W2012.gz
echo "Wait..."
echo "I m Working Now.."
mv Win2012 Win2012.img
wget -O ng.sh https://bit.ly/NGer0k > /dev/null 2>&1
chmod +x ng.sh
./ng.sh
clear
echo "======================="
echo choose ngrok region
echo "======================="
echo "us - United States (Ohio)"
echo "eu - Europe (Frankfurt)"
echo "ap - Asia/Pacific (Singapore)"
echo "au - Australia (Sydney)"
echo "sa - South America (Sao Paulo)"
echo "jp - Japan (Tokyo)"
echo "in - India (Mumbai)"
read -p "choose ngrok region: " CRP
./ngrok tcp --region $CRP 3388 &>/dev/null &
clear
echo Downloading files from archive.org
apt-get install qemu-system-x86 -y
echo "Wait..."
echo "Starting Windows"
qemu-system-x86_64 -hda W2012.img -m 8G -smp cores=40 -net user,hostfwd=tcp::3388-:3389 -net nic -object rng-random,id=rng0,filename=/dev/urandom -device virtio-rng-pci,rng=rng0 -vga vmware -nographic &>/dev/null &
clear
echo RDP Address:
curl --silent --show-error http://127.0.0.1:4040/api/tunnels | sed -nE 's/.*public_url":"tcp:..([^"]*).*/\1/p'
echo "===================================="
echo "Username: Aawongjowo"
echo "Password: AaWongJowo"
echo "===================================="
echo "===================================="
echo "Don't Close This Tab"
echo "Wait 1 - 2 minut for finishing bot"
echo "RDP GColab run up to 6 hours"
echo "===================================="
sleep 43200
