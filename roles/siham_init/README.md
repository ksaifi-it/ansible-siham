# Ansible role: siham_init


Ce rôle Ansible permet de déployer les prérequis d'un serveur APP ou TOOLS de SIHAM. 
Ce rôle va : 
- Configurer les prérequis Siham

- Installer un certain nombre de packages yum pour les besoins de l'application Siham.

- Créer les dossiers /data/exploit et /data/distrib , et créer les liens symboliques /exploit et /distrib correspondants.

## Prérequis

Système RHEL 8.x et plus, ainsi qu'un accès réseau ouvert vers le serveur satellite (ou redhat.com).  


## Parametres

### Parametres obligatoires

Néant 

### Parametres optionnels


| Parameter | Description | Type | Default value |
| --------- | ----------- | ---- | ------------- |
| siham_is_templatetools | Est ce que c'est un serveur Tools | boolean | false |
| siham_is_templateapp  | Est ce que c'est un serveur App | boolean | false |
| siham_init_service_to_disable | services à arrêter et désactviter | list(string)  | "- firewalld.service" |
| siham_init_ipv6_disable | indique si il faut désactiver ipv6 | booleen | yes |
| sihamcommon_nfs_dir | liste de points de montage à définir | liste[objet] | <pre>  - mount_point: "/exploit/sources"<br>    nfs_share: "sham-xl-filesnf:/data/nfs/storage/sources"<br>  - mount_point: "/interfaces"<br>    nfs_share: "sham-xl-filesnf:/data/nfs/storage/interfaces"<br>  - mount_point: "/exploit/backup"<br>    nfs_share: "sham-xl-bakup01:/data/nfs/storage/sauvegarde"</pre> |
|-|point de montage|mount_point: "string"||
|-|partage nfs|nfs_share: "string"||


