## Reference:
```
https://github.com/Orange-Cyberdefense/arsenal
```

# Arsenal - Installation & Personnalisation

### Requirements:
```
sudo apt install python3-pip
# or : sudo apt install --reinstall python3-pip
sudo pip3 install docutils
```

```
mkdir -p ~/app/saz-arsenal

cd ~/app/saz-arsenal

git clone https://github.com/Orange-Cyberdefense/arsenal

cd arsenal

rm -rf .git*

cd arsenal/data/cheats/

git clone https://github.com/AZIZI-Sajjad/saz-arsenal.git

sudo ln -s ~/app/saz-arsenal/arsenal/run /usr/local/bin/arsenal
```

### Create Alias in .bashrc
```
nano -c ~/.bashrc

alias cdarsenal='cd ~/app/saz-arsenal/arsenal/arsenal/data/cheats/saz-arsenal'

alias codearsenal='code ~/app/saz-arsenal/arsenal/arsenal/data/cheats/saz-arsenal'

source ~/.bashrc
```
### Run arsenal
```
arsenal

```

![alt text](image.png)