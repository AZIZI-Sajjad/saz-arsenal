# saz-python

#plateform/python
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/python

## Python - Create and enter nenv - virtuel environnement 
```
### Create nenv
python3 -m venv .venv

### Activate nenv
source .venv/bin/activate
```

## Python - remove images's background
```
python3 -m venv .venv
source .venv/bin/activate
pip install "rembg[cpu]"
pip install "rembg[cpu,cli]"
rembg i source.jpg output.png
```