# gitlab-installation
![gitlab](https://user-images.githubusercontent.com/48319188/112189390-e16cfb00-8bfb-11eb-9182-228f11d25cbe.png)

=============INSTALLATION GITLAB SUR CENTOS ================

## Installation des dependances
```
sudo yum -y update
sudo yum -y install epel-release curl vim policycoreutils-python
```

## Installation de postfix si vous voulez envoyer des notifications
```
sudo yum install postfix
```

## Demarage du service  apres installation
```
sudo systemctl enable postfix
sudo systemctl start postfix
```

## Ajouter le référentiel GitLab CE
### Créez un nouveau fichier de référentiel pour GitLab:
```
sudo vi /etc/yum.repos.d/gitlab-ce.repo
```

### Ajoutez ensuite les lignes suivantes:
```
[gitlab-ce]
name=gitlab-ce
baseurl=https://packages.gitlab.com/gitlab/gitlab-ce/el/7/$basearch
repo_gpgcheck=1
gpgcheck=1
enabled=1
gpgkey=https://packages.gitlab.com/gitlab/gitlab-ce/gpgkey
       https://packages.gitlab.com/gitlab/gitlab-ce/gpgkey/gitlab-gitlab-ce-3D645A26AB9FBD22.pub.gpg
metadata_expire=300
```

### Installez GitLab CE en exécutant la commande:
```
sudo EXTERNAL_URL="http://gitlab.datasquad.com" yum install -y gitlab-ce
```
NB: Remplacez EXTERNAL_URL par votre nom de domaine pour Gitlab.
