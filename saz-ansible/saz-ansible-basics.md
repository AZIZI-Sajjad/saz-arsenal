# saz-ansible-basics

#plateform/Linux Widows
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/ansible

## Ansible - Désactiver COW et séparer les étapes par des lignes en étoiles    ************************************************************
```
    # 1- Modifier le fichier de configuration de Ansible
        nano -c /etc/ansible/ansible.cfg
    # 2- ajouter ces lignes à la fin
        [defaults]
        nocows = 1
```

