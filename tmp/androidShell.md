# Android Shell

## Android v. Linux

### Les similarités

Android utilise noyau Linux. Nombreuses commandes Unix/Linux de base fonctionnent sur Android.

```bash
# Gestionnaire des fichiers
ls -l        # Lister les fichiers
cd /data     # Changer de répertoire
cp fichier1 fichier2  # Copier un fichier
mv fichier1 dossier/  # Déplacer un fichier
rm fichier.txt   # Supprimer un fichier
find <target-directory> -name "<folder/file-name>" # exact match
grep -r "search_term" /path/to/search # full text search
# Gestionnaire des processus
ps -A        # Afficher les processus actifs
top          # Voir l'utilisation du CPU en temps réel
kill 1234    # Tuer un processus par son PID
ping 8.8.8.8       # Tester la connexion Internet
ifconfig          # Voir l’état des interfaces réseau (remplacé par `ip` sur certaines versions)
netstat -tulnp    # Voir les connexions réseau actives
# Gestionnaire du stokage
df -h        # Afficher l’espace disque utilisé
mount <partiion>        # Voir les partitions montées
umount <partition>  # Démonter une partition
uname -a     # Voir les infos du noyau Linux
cat /proc/cpuinfo   # Voir les infos du processeur
logcat       # Voir les logs système Android
```

### Les différences 

- Pas de commandes GNU :

    - Android utilise Toybox ou BusyBox à la place de certaines commandes GNU/Linux.
    Exemple : la commande sed ou awk peut ne pas fonctionner comme sur une distribution Linux classique.

- Pas de gestionnaire de paquets comme `apt` ou `dnf` :

    - Il n'y a pas apt-get, yum, ou dnf 
    
    - Sur un appareil rooté, on peut utiliser pkg (Termux) ou apk (Alpine Linux via chroot/Proot).

- Arborescence différente :

    - Android utilise sa propre structure de fichiers.

    - Linux standard :

    	- `bin`: Binaries système  
    	- `etc`: Fichiers de configuration  
    	- `home`: Répertoires des utilisateurs  
    	- `var/log`: Logs système  
    
    - Android :

    	- `system`: Contient le système d’exploitation  
        - `data`: Stocke les applications et données utilisateur  
        - `cache`: Utilisé pour les mises à jour et caches  
        - `vendor`: Contient les pilotes et fichiers spécifiques au fabricant  

- Pas de `systemmd` ou `SysVinit` :

    Android utilise `init.rc` au lieu de `systemd` ou `SysVinit` pour gérer les services au démarrage.

## Gestionnaire des paquets

### Package Manager (pm)

Android dispose d'un gestionnaire de paquets intégré accessible via la commande `pm`. Cette commande permet de gérer les applications installées sur l'appareil.

```bash
# Lister toutes les applications installées
pm list packages

# Filtrer la liste des applications par nom
pm list packages | grep facebook

# Afficher le chemin d'installation d'une application
pm path com.application.exemple

# Désactiver une application (requiert les droits root ou ADB)
pm disable com.application.exemple

# Réactiver une application
pm enable com.application.exemple

# Désinstaller une application (requiert les droits root ou ADB)
pm uninstall com.application.exemple

# Désinstaller pour l'utilisateur courant uniquement
pm uninstall --user 0 com.application.exemple

# Installer une application depuis un fichier APK
pm install /chemin/vers/application.apk

# Effacer les données d'une application
pm clear com.application.exemple
```

Contrairement aux gestionnaires de paquets Linux comme `apt` ou `dnf`, `pm` est limité à la gestion des applications Android et ne permet pas d'installer des bibliothèques système ou des outils en ligne de commande.

