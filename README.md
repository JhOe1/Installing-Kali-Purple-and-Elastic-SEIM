# Installing Kali Purple and Elastic SEIM

---
In this project, I will be installing Kali purple on a virtual machine which will serve as blue, Then will also have another Kali machine which will serve as the Red team and lastly a Windows machine that will serve as the victim. For the experiment, i will be using Virtual box as my hypervisor 

I will be conducting a series of attacks on the Windows machine using Kali for attacks the monitoring these attacks using Kali Purple where the Elastic SEIM will be installed.

First, i have to install Kali Purple i already downloaded the ISO from Kali website 


Kali purple machine will have 8GB of RAM, 4 CPU and 80GB ROM

<img width="1007" alt="Screenshot 2024-11-01 at 03 14 14" src="https://github.com/user-attachments/assets/5442e0d8-1143-49ad-8096-7d0408bd15b5">

<img width="900" alt="Screenshot 2024-11-01 at 03 31 52" src="https://github.com/user-attachments/assets/f5cbe6f4-8a7d-4b54-b8c5-48f4cba9c431">



Next, I installed all the dependencies using the following lines of codes to get Elastic Stack Running 

# Elastic stack installation

# 1. Install dependencies:


<img width="1002" alt="Screenshot 2024-11-14 at 17 05 03" src="https://github.com/user-attachments/assets/165bf6ff-e6aa-4e97-aff4-0486051eca95">

I used the following commands to install dependencies needed to get Elastic Search up and running 

"sudo apt-get install curl
curl -fsSL https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/elastic-archive-keyring.gpg
echo "deb https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-8.x.list
sudo bash -c "export HOSTNAME=kali-purple.kali.purple; apt-get install elasticsearch -y"


# 2. Convert to single-node setup :

<img width="997" alt="Screenshot 2024-11-14 at 17 08 20" src="https://github.com/user-attachments/assets/41e32da1-e86a-4ca8-b429-1f6a6baca406">
Next I used the following commands to  Convert to a single-node setup 

sudo sed -e '/cluster.initial_master_nodes/ s/^#*/#/' -i /etc/elasticsearch/elasticsearch.yml
echo "discovery.type: single-node" | sudo tee -a /etc/elasticsearch/elasticsearch.yml


# 3. Install Kibana:

<img width="997" alt="Screenshot 2024-11-14 at 17 13 14" src="https://github.com/user-attachments/assets/bd39179c-bd8c-4c80-a9b7-688b65f3d97f">
Next i install Kibana with the following command 
"sudo apt install kibana
sudo /usr/share/kibana/bin/kibana-encryption-keys generate -q"
# Add keys to /etc/kibana/kibana.yml














echo "server.host: \"kali-purple.kali.purple\"" | sudo tee -a /etc/kibana/kibana.yml
# Ensure kli-purple.kali.purple is only mapped to my IP Address in /etc/hosts in order to bind Kibana to that interface
sudo systemctl enable elasticsearch kibana --now

