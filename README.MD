# Installation Minikube sur K8s serveur 

## Installation sur Python    
```
apt install python3-pip
pip3 install -r requirements.txt
python3 app.py
```

## Docker
```
docker run -d -p 5000:5000 danielbaks/flask-tff
```
 
## Desactivation du swap 
1. Se connecter a la Debian en sudo 
2. Edition du ficher grub 

```
nano /etc/default/grub 
```

```
GRUB_CMDLINE_LINUX="cgroup_enable=memory swapaccount=1"
```
3. Mettre a jour le grub

```
sudo update-grub 
```

4.Miniube dans une VM: 

Pour faire fonctioner minikube dans une VM il faut désactiver les driver de minikube cela permetra a minikube d'utiliser les driver de la VM
```
sudo apt-get install -y conntrack
cd /usr/bin/
ln -s /usr/sbin/conntrack conntrac
```

5. Lancer minikube

```
minikube start --driver=none
```
