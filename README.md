## Reference:
https://github.com/Orange-Cyberdefense/arsenal


Arsenal - Installation & Personnalisation  


mkdir -p ~/app/saz-arsenal  
cd ~/app/saz-arsenal  
git clone https://github.com/Orange-Cyberdefense/arsenal  
cd arsenal
rm -rf .git*  
cd arsenal/data/cheats/  
git clone https://github.com/AZIZI-Sajjad/saz-arsenal.git  
sudo ln -s ~/app/saz-arsenal/run /usr/local/bin/arsenal  


nano -c ~/.bashrc  
alias cdarsenal='cd ~/app/saz-arsenal/arsenal/data/cheats/saz-arsenal'  
alias codearsenal='code ~/app/saz-arsenal/arsenal/data/cheats/saz-arsenal'  



