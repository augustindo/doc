# Packaging d’applications : les bonnes pratiques

<div class="alert alert-danger">
<b>
Cette page est en cours d'élaboration. Tant que cet avertissement n'est pas enlevé. Considérez ces informations comme potentiellement fausse.
Le nom YEP n'est à priori pas définitif, ni les niveaux, ni les bonnes pratiques en elle-même.
</b>
</div>

### Introduction
Ce document a pour but de lister les différentes bonnes pratiques concernant la création de paquet d'application YunoHost.

Chaque bonne pratique est numérotée avec un numéro suffixé par les lettres YEP (YunoHost Enhancement Proposals), ceci afin de pouvoir y faire référence facilement dans les outils d'analyse automatique de paquet ([package checker](https://github.com/YunoHost/package_check), [package linter](https://github.com/YunoHost/package_linter)), mais également lors des revues de code.

Chaque YEP est associée à :
* un statut indiquant si la règle a été validé ou si elle fait encore l'objet de discussion (brouillon, validé, refusé, obsolète) ;
* une indication sur le type de test à mener (manuel ou auto si un outil automatique peut vérifier) ;
* une indication du niveau d'app à partir duquel la règle est nécessaire (NOTWORKING, INPROGRESS, WORKING, OFFICIAL), certaines règles sont optionnelles ;

### Index des YEP
| ID |  Titre | Status | Test | Niveau |
|----|--------|--------|------|--------|
| **YEP 1** | **Communiquer avec la communauté** | | | |
| YEP 1.1 | Nommer son app et son dépôt  | validé | manuel | NOTWORKING |
| YEP 1.2 | Inscrire l'app sur un "répertoire" connu  | validé | manuel | NOTWORKING |
| YEP 1.3 | Indiquer la licence associée au paquet  | brouillon | AUTO | WORKING |
| YEP 1.4 | Informer sur l'intention de maintenir un paquet   | brouillon | manuel | WORKING |
| YEP 1.5 | Mettre à jour régulièrement le statut de l'app  | brouillon | manuel | WORKING |
| YEP 1.6 | Se tenir informé sur l'évolution du packaging d'apps  | validé | manuel | OFFICIAL |
| YEP 1.7 | Ajouter l'app à l'[organisation YunoHost-Apps](https://github.com/YunoHost-Apps)  | validé | manuel | OFFICIAL |
| YEP 1.8 | Publier des demandes de test  | validé | manuel | OFFICIAL |
| YEP 1.9 | Documenter l'app  | validé | AUTO | OFFICIAL |
| YEP 1.10 | Garder un historique de version propre   | brouillon | manuel | OFFICIAL |
| YEP 1.11 | Ajouter l'app au [bugtracker YunoHost](https://dev.yunohost.org)   | brouillon | manuel | OFFICIAL |
| | | | | |
| **YEP 2** | **Stabiliser une app** | | | |
| YEP 2.1 | Respecter le format du manifeste  | validé | auto | INPROGRESS |
| YEP 2.2 | Utiliser bash pour les scripts principaux  | validé | auto | WORKING |
| YEP 2.3 | Sauvegarder les réponses lors de l'installation  | validé | manuel | WORKING |
| YEP 2.4 | Détecter et gérer les erreurs  | brouillon | manuel | WORKING |
| YEP 2.5 | Copier correctement des fichiers   | brouillon | manuel | WORKING |
| YEP 2.6 | Annuler l'action si les valeurs d'entrées sont incorrectes   | validé | manuel | WORKING |
| YEP 2.7 | Donner des permissions suffisantes aux instructions bash   | validé | auto | WORKING |
| YEP 2.8 | Modifier correctement une configuration système   | brouillon | manuel | WORKING |
| YEP 2.9 | Enlever toutes traces de l'app lors de la suppression   | brouillon | manuel | WORKING |
| YEP 2.10 | Configurer les logs de l'application   | brouillon | manuel | WORKING |
| YEP 2.11 | Utiliser une variable plutôt que l'app id directement  | validé | manuel | OFFICIAL |
| YEP 2.12 | Utiliser les commandes pratiques (helpers)  | validé | auto | OFFICIAL |
| YEP 2.13 | Traduire le package en anglais   | brouillon | manuel | OFFICIAL |
| YEP 2.14 | Remplir correctement un fichier de conf   | brouillon | manuel | OFFICIAL |
| YEP 2.15 | Suivre les instructions d'installation de l'application   | validé | manuel | OFFICIAL |
| YEP 2.16 | Vérifier la disponibilité des dépendances sur ARM, x86 et x64   | validé | manuel | OFFICIAL |
| YEP 2.17 | Prendre en compte la version d'origine lors des mises à jour   | validé | manuel | OFFICIAL |
| | | | | |
| **YEP 2.18** | **Stabiliser une webapp** | | | |
| YEP 2.18.1 | Lancer le script d'installation d'une webapp correctement   | validé | manuel | WORKING |
| YEP 2.18.2 | Supporter l'installation sur un domaine   | validé | auto | WORKING |
| YEP 2.18.3 | Supporter l'installation sur un sous-domaine   | validé | auto | WORKING |
| YEP 2.18.4 | Supporter l'installation sur un sous-dossier   | validé | auto | OFFICIAL |
| YEP 2.18.5 | Ajouter la tuile YunoHost pour naviguer facilement entre les applications   | validé | manuel | OFFICIAL |
| | | | | |
| **YEP 3** | **Sécuriser une app** | | | |
| YEP 3.1 | Ne pas demander ou stocker de mot de passe LDAP   | brouillon | manuel | NOTWORKING |
| YEP 3.2 | Ouvrir un port correctement   | brouillon | manuel | WORKING |
| YEP 3.3 | Faciliter le contrôle de l'intégrité des sources   | brouillon | manuel | OFFICIAL |
| YEP 3.4 | Isoler l'app   | brouillon | manuel | OFFICIAL |
| YEP 3.5 | Suivre les recommandations de la documentation de l'app   | validé | manuel | OFFICIAL |
| YEP 3.6 | Mettre à jour les versions contenant des CVE   | draft | manuel | OFFICIAL |
| | | | | |
| **YEP 4** | **Intégrer une app** | | | |
| 4.1 | Lier au ldap   | validé | manuel | OFFICIAL |
| YEP 4.2 | Lier l'authentification au sso   | validé | manuel | OFFICIAL |
| YEP 4.2.1 | Déconnexion   | validé | manuel | OFFICIAL |
| YEP 4.3 | Fournir un script de sauvegarde YunoHost fonctionnel   | validé | auto | OFFICIAL |
| YEP 4.4 | Fournir un script de restauration YunoHost fonctionnel   | validé | auto | OFFICIAL |
| YEP 4.5 | Utiliser les hooks   | validé | manuel | OPTIONAL |
| YEP 4.6 | Gère le multi-instance   | validé | manuel | OPTIONAL |
| YEP 4.7 | Ajouter un module à la CLI   | validé | manuel | OPTIONAL |
| YEP 4.8 | Ajouter un module à l'admin web   | brouillon | manuel | OPTIONAL |


### YEP 1 - Communiquer avec la communauté
La YEP 1 est une meta YEP, elle explique ce qu'il faut faire pour échanger avec la communauté autour d'un paquet d'application YunoHost.

#### YEP 1.1 - Nommer son app et son dépot  | validé | manuel | NOTWORKING |
Chaque application YunoHost possède un id inscrit dans le manifest de l'application.
Cet identifiant doit être unique entre chaque paquet d'application.
Il est donc recommandé de vérifier sa disponibilité en consultant la liste des applications référencées dans les dépôts d'applications connus (official, community, internetcube).

De plus l'identifiant doit respecter l'expression régulière suivante `^[a-z1-9]((_|-)?[a-z1-9])+$` . Autrement dit, il doit respecter les règles suivantes :
* être en minuscule
* commencer par une lettre ou un chiffre
* être alphanumérique (le underscore est autorisé)
* ne pas contenir 2 underscores ou tirets qui se suivent
* ne pas terminer par un underscore ou un tiret

Pour les noms d'applications contenant des espaces la quasi totalité des paquets actuels les retirent simplement sans les remplacer par des tirets ou underscores.

Par convention, les dépôts d'applications YunoHost sont toujours nommés de leur ID suivis de la chaine de caractère "\_ynh". Ainsi on peut distinguer le dépôt upstream de l'application, du dépôt du package yunohost. Cette notation permet également de trouver des applications non répertoriées à travers les moteurs de recherche des plateformes proposant des gestionnaires de version (github par exemple).

Exemple : ID : exemple Nom de dépôt : exemple_ynh

#### YEP 1.2 - Inscrire l'app sur un « répertoire » connu  | validé | manuel | NOTWORKING |
Il est conseillé dès le début du packaging d'inscrire une app sur un des dépôts d'application YunoHost.

Ces dépôts ont plusieurs fonctions :
* communiquer l'existence d'un paquet ;
* indiquer la dernière version associée au paquet (afin de permettre à la mise à jour de l'app par YunoHost) ;
* indiquer l'état de fonctionnement du paquet ;
* indiquer des informations sur le support d'un paquet.

Pour les listes official.json et community.json, l'inscription se fait sur [le dépôt git "apps"](https://github.com/YunoHost/apps).

Pour la liste d'application du projet LaBriqueInter.net, l'inscription se fait en consultant [la doc du dépôt du site internet](https://github.com/labriqueinternet/labriqueinter.net).

#### YEP 1.3 - Indiquer la licence associée au paquet  | brouillon | AUTO | WORKING |
#### YEP 1.4 - Informer sur l'intention de maintenir un paquet   | brouillon | manuel | WORKING |
#### YEP 1.5 - Mettre à jour régulièrement le statut de l'app  | brouillon | manuel | WORKING |
#### YEP 1.6 - Se tenir informé sur l'évolution du packaging d'apps  | validé | manuel | OFFICIAL |
Afin de suivre l'évolution du format de packaging ainsi que des bonnes pratiques, il est recommandé de:
* s'inscrire à la liste de discussion apps@list.yunohost.org
* suivre [la catégorie App intégration du forum](https://forum.yunohost.org/c/app-integration)

Pour suivre l'évolution de YunoHost de façon plus générale:
* rejoindre le salon XMPP dev@conference.yunohost.org ([3 jours de logs sont disponibles](https://im.yunohost.org/logs/dev/))
* suivre [la catégorie Annoucement du forum](https://forum.yunohost.org/c/announcement)
* suivre les discussions sur contrib@list.yunohost.org

#### YEP 1.7 - Ajouter l'app à l'[organisation YunoHost-Apps](https://github.com/YunoHost-Apps)  | validé | manuel | OFFICIAL |
L'ajout d'une app sur l'[organisation YunoHost-Apps](https://github.com/YunoHost-Apps) permet de faire connaitre l'apps auprès des autres contributeurs qui pourraient être tentés de packager l'application visée.

C'est aussi un moyen pour permettre de déployer rapidement un correctif de sécurité si nécessaire dans le cas où le mainteneur ne serait pas disponible.

#### YEP 1.8 - Publier des demandes de test  | validé | manuel | OFFICIAL |
Afin d'assurer le bon fonctionnement d'un paquet, il convient de publier une annonce afin d'ouvrir les tests sur le paquet. Cette annonce peut se faire sur le forum dans [la catégorie App intégration du forum](https://forum.yunohost.org/c/app-integration).

Il est recommandé d'indiquer si certains tests n'ont pas été menés.
<div class="alert alert-danger">
<b>
TODO: Lister les tests types à mener
</b>
</div>
#### YEP 1.9 - Documenter l'app  | validé | AUTO | OFFICIAL |
Avant tout, il convient de faire une description correcte de l'app dans le champ `description` du manifest. L'insertion de mot clé dans cette description peut être une bonne idée, dans la mesure où un utilisateur pourrait être amené à faire une recherche (CTRL+F) parmi toutes les applications.

Il y a également le README.md, ce dernier peut contenir:
* le nom de l'app
* un bref résumé de ce qu'elle fait
* des éventuels compléments d'installation si le script ne suffit pas lui-même
* des instructions pour l'utiliser (par exemple pour relier son smartphone ou son ordinateur)
* l'endroit pour signaler un dysfonctionnement / une demande
* la roadmap/TODO
* éventuellement les pré-requis en termes de mémoires ram, processeur etc. (certains équipements ont moins de 512Mo de ram)

#### YEP 1.10 - Garder un historique de version propre   | brouillon | manuel | OFFICIAL |
#### YEP 1.11 - Ajouter l'app au [bugtracker YunoHost](https://dev.yunohost.org)   | brouillon | manuel | OFFICIAL |

### YEP 2 - Stabiliser une app
#### YEP 2.1 - Respecter le format du manifeste  | validé | auto | INPROGRESS |
Le manifeste permet de décrire une app afin que YunoHost puisse lui appliquer les bons traitements. Pour plus d'information voir la [documentation dédiée](https://yunohost.org/#/packaging_apps_manifest).

#### YEP 2.2 - Utiliser bash pour les scripts principaux  | validé | auto | WORKING |
Les scripts d'action (install, upgrade, remove, backup et restore) doivent être en bash afin que la cli/api yunohost puisse correctement les appeler.

Ceci étant, rien n'empêche à l'intérieur de ces scripts de faire appel à d'autres scripts ou bibliothèques de fonction. Ceux-ci ne sont pas obligés d'être en bash.

Cependant, il faudra porter une attention particulière à l'affichage correct des logs d'information, de warning, ou d'erreurs. Afin qu'un utilisateur de la cli/api yunohost puisse comprendre le fonctionnement du script venant d'être exécuté et au besoin réparer son instance YunoHost.

#### YEP 2.3 - Sauvegarder les réponses lors de l'installation  | validé | manuel | WORKING |
Lors de l'installation, il est nécessaire de sauvegarder chaque réponse aux questions du manifeste. En effet, même si au début il n'est pas nécessaire d'écrire un script de mise à jour, par la suite ce sera sans doute le cas. Or, sans les informations initiales, la mise à jour peut être plus fastidieuse.

#### YEP 2.4 - Détecter et gérer les erreurs  | brouillon | manuel | WORKING |
#### YEP 2.5 - Copier correctement des fichiers   | brouillon | manuel | WORKING |
#### YEP 2.6 - Annuler l'action si les valeurs d'entrées sont incorrectes   | validé | manuel | WORKING |
Chaque script devrait vérifier que les valeurs d'entrées sont correctes.

Voici quelques exemples:
* Vérifier que le nom de domaine existe
* Vérifier que l'utilisateur existe
* Vérifier que le chemin choisi est disponible

Dans le cas où l'une des valeurs est incorrecte, il est alors nécessaire d'annuler toutes modifications réalisées préalablement sur l'instance. Le mieux étant de faire tous ces contrôles avant de modifier le système.


#### YEP 2.7 - Donner des permissions suffisantes aux instructions bash   | validé | auto | WORKING |
Certaines instructions nécessitent les droits sudo. Il faut dans ce cas ne pas oublier de préfixer ces instructions par `sudo `.

Dans d'autres cas il est nécessaire de donner des droits à l'aide de chmod et de chown.

#### YEP 2.8 - Modifier correctement une configuration système   | brouillon | manuel | WORKING |
#### YEP 2.9 - Enlever toutes traces de l'app lors de la suppression   | brouillon | manuel | WORKING |
#### YEP 2.10 - Configurer les logs de l'application   | brouillon | manuel | WORKING |
#### YEP 2.11 - Utiliser une variable plutôt que l'app id directement  | validé | manuel | OFFICIAL |
Il est conseillé de rendre les scripts le plus générique possible, un bon moyen d'y parvenir est d'utiliser une variable pour le nom de l'app afin d'éviter qu'il se retrouve partout dans les scripts. Ainsi un autre packageur pourra plus facilement se servir du script pour une autre app.

#### YEP 2.12 - Utiliser les commandes pratiques (helpers)  | validé | auto | OFFICIAL |
Afin de simplifier le packaging, d'uniformiser les pratiques, d'éviter les erreurs et d'augmenter la durée de vie d'un script vis-à-vis des futures versions de YunoHost. Un ensemble de helpers permettant de faire de nombreuses actions est proposé.

Pour plus d'information:
* consulter [la documentation des helpers](https://yunohost.org/#/packaging_apps_helpers_fr)
* explorer [le répertoire des helpers](https://github.com/YunoHost/yunohost/tree/unstable/data/helpers.d)

#### YEP 2.13 - Traduire le package en anglais   | brouillon | manuel | OFFICIAL |
#### YEP 2.14 - Remplir correctement un fichier de conf   | brouillon | manuel | OFFICIAL |
#### YEP 2.15 - Suivre les instructions d'installation de l'application   | validé | manuel | OFFICIAL |

#### YEP 2.16 - Vérifier la disponibilité des dépendances sur ARM, x86 et x64   | validé | manuel | OFFICIAL |
YunoHost s'installe sur ARM, sur x86 et x64. Un package devrait donc être testé sur ces 3 architectures.

Certains paquets ne sont pas disponibles sur ARM, il convient dans ce cas d'étudier d'autres solutions ou d'indiquer dans le README.md que l'application ne fonctionne pas sur ARM.

#### YEP 2.17 - Prendre en compte la version d'origine lors des mises à jour   | validé | manuel | OFFICIAL |
Le script de mise à jour doit pouvoir fonctionner même si les mises à jour précédentes n'ont pas été effectuées.

Ainsi, il doit être possible de faire des sauts de mise à jour d'une version N-x vers une version N. Pour ce faire il est conseillé d'enregistrer les numéros de version dans les settings de l'app.

### YEP 2.18 - Stabiliser une webapp
La majeure partie des applications YunoHost sont des web apps, mais certaines n'en sont pas. Les YEP 2.18.x développent certaines spécificités liées aux web app.

#### YEP 2.18.1 - Lancer le script d'installation d'une webapp correctement   | validé | manuel | WORKING |
Bien souvent une web app s'installe à partir de formulaires affichés sur une page web. Cette façon de faire, bien que pratique pour un humain, l'est moins pour un programme.

Il convient donc de vérifier si l'application ne propose pas une solution d'installation en ligne de commande.

Si ce n'est pas le cas, il convient d'utiliser l'option -H de curl. En effet, dans certains cas la redirection DNS pourrait ne pas être active au moment de l'installation.
```
curl -kL -H "Host: $domain" --data "&param1=Text1&param2=text2" https://localhost$path/install.php > /dev/null 2>&1
```

#### YEP 2.18.2 - Supporter l'installation sur un domaine   | validé | auto | WORKING |
Une web app devraient pouvoir s'installer sur un domaine directement sans sous dossiers.

#### YEP 2.18.3 - Supporter l'installation sur un sous-domaine   | validé | auto | WORKING |
Une web app devraient pouvoir s'installer sur un sous-domaine directement sans sous dossiers.

#### YEP 2.18.4 - Supporter l'installation sur un sous-dossier   | validé | auto | OFFICIAL |
Une web app devraient pouvoir s'installer dans un sous-dossier.

#### YEP 2.18.5 - Ajouter la tuile YunoHost pour naviguer facilement entre les applications   | validé | manuel | OFFICIAL |
Sauf dans de rare cas il est conseiller d'intégrer le carré YunoHost qui permet de retourner sur le menu du SSO. Cette intégration se fait dans la configuration nginx.

Certains utilisateurs ont remplacé ce carré par un script ajoutant un menu en haut de chaque webapp.

### YEP 3 - Sécuriser une app
#### YEP 3.1 - Ne pas demander ou stocker de mot de passe LDAP   | brouillon | manuel | NOTWORKING |
#### YEP 3.2 - Ouvrir un port correctement   | brouillon | manuel | WORKING |
#### YEP 3.3 - Faciliter le contrôle de l'intégrité des sources   | brouillon | manuel | OFFICIAL |
#### YEP 3.4 - Isoler l'app   | brouillon | manuel | OFFICIAL |
#### YEP 3.5 - Suivre les recommandations de la documentation de l'app   | validé | manuel | OFFICIAL |
En général, une application propose une documentation afin d'aider les administrateurs systèmes à réaliser l'installation. Il est conseiller d'en suivre les recommandations, notamment celles concernant les permissions à accorder par fichier ou répertoire.

Le mainteneur de paquet doit toutefois rester vigilant, certaines documentations pouvant être erronées ou insuffisante.

#### YEP 3.6 - Mettre à jour les versions contenant des CVE   | draft | manuel | OFFICIAL |

### YEP 4 - Intégrer une app
Cette meta YEP traite de l'intégration d'une app avec l'environnement YunoHost. Une bonne intégration est en général un gage de qualité et de confort pour les utilisateurs.

#### YEP 4.2 - Lier l'authentification au sso   | validé | manuel | OFFICIAL |
Le Single Sign On permet d'éviter d'avoir à créer les mêmes utilisateurs pour chaque app. Ainsi un utilisateur YunoHost pourra se connecter via le Single Sign On à l'ensemble des apps.

Pour se faire, il convient de lier son app au LDAP et/ou d'utiliser des hooks pour dupliquer les informations du user dans la base de données de l'app.

Une fois cette opération faite, le mainteneur peut utiliser l'instruction HTTP REMOTE_USER pour vérifier si un utilisateur est loggué ou non. En général, des modules existent (que ce soit au niveau de la technologie, du framework ou même de l'app elle-même).

Au besoin, SSOwat permet de sécuriser l'accès à une ou plusieurs parties de l'app. Il peut ainsi être pertinent de sécuriser l'accès à une page d'administration avec le SSO plutôt qu'un htaccess et de rendre le reste de l'app accessible à tous les visiteurs.

#### YEP 4.2.1 - Déconnexion   | validé | manuel | OFFICIAL |
Lorsque l'on clique sur une action de déconnexion au sein de l'app, celle-ci devrait déconnecter l'utilisateur du SSO. Sinon il y a un risque que l'utilisateur laisse par mégarde une session ouverte.

#### YEP 4.3 - Fournir un script de sauvegarde YunoHost fonctionnel   | validé | auto | OFFICIAL |
#### YEP 4.4 - Fournir un script de restauration YunoHost fonctionnel   | validé | auto | OFFICIAL |
#### YEP 4.5 - Utiliser les hooks   | validé | manuel | OPTIONAL |
YunoHost offre la possibilité de lancer des actions à chaque traitement effectué par la ligne de commande. Ceci peut être pratique dans de nombreux cas.

Exemples:
* Ajouter/supprimer un utilisateur dans la base de données de l'app lorsque l'on utilise `yunohost user create` ou `yunohost user remove`
* Ajouter le support d'un nouveau nom de domaine lors de l'action `yunohost domain add`
* Lancer un script après que le parefeu ait été rechargé

Liste des hooks:
* post_domain_add
* post_domain_remove
* post_user_create
* post_user_delete
* post_backup_create
* post_backup_restore
* pre_backup_delete
* post_backup_delete
* post_app_addaccess
* post_app_removeaccess
* post_app_clearaccess
* post_app_addaccess
* post_iptable_rules

Ces scripts sont à placer dans un répertoire `hooks` comme dans ce package: https://github.com/YunoHost-Apps/owncloud_ynh/tree/master/hooks .


#### YEP 4.6 - Gèrer le multi-instance   | validé | manuel | OPTIONAL |
Il est parfois pratique de pouvoir installer plusieurs fois une même app. Par exemple pour plusieurs noms de domaine différents.

Il faut toutefois faire attention à la façon de gérer les chemins de fichier, les dépendances, les ports utilisés etc. de sorte qu'il n'y ait pas de collision.

#### YEP 4.7 - Ajouter un module à la CLI   | validé | manuel | OPTIONAL |
Il est possible de créer un module afin d'ajouter des commandes à la ligne de commandes yunohost.

Pour ce faire, il faut ajouter un actionmaps dans /usr/share/moulinette/actionsmap/ . Cet actionmaps doit commencer par "ynh_".

Les paquets [menu_ynh](https://github.com/YunoHost-Apps/menu_ynh/) et [subscribe_ynh](https://github.com/YunoHost-Apps/subscribe_ynh/) bien qu'un peu ancien (et non à jour) peuvent servir de base pour mettre en place ce genre de module.
#### YEP 4.8 - Ajouter un module à l'admin web   | brouillon | manuel | OPTIONAL |