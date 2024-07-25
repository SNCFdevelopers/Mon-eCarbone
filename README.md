# Mon-eCarbone

Vidéo de présentation de l'application Mon e-Carbone : [Publier | LinkedIn](https://www.linkedin.com)

Mon e.Carbone a pour objectif de donner à chaque collaborateur les leviers pour agir sur son empreinte carbone numérique. Au-delà du bilan carbone informatique par collaborateur, l'application permet un premier ménage immédiat dans les mails et les documents OneDrive via une connexion directe à Microsoft O365.

Cette application de sensibilisation et de mise en œuvre des premiers écogestes doit s’inscrire dans une politique numérique responsable complète pour être la plus efficace possible.

## Les Solutions et leur installation

L'utilisation de l'application nécessite une licence PowerApp Pro avec accès Dataverse pour chaque utilisateur.

### 1. Les solutions et leurs contenus

#### Numérique responsable – Tables :

- **Challenges** : Données liées aux différents challenges créés.
- **Company variables** : Données liées à la personnalisation des différents liens et visuels.
- **DataReference** : Données d'équivalences carbone des outils collaborateurs.
- **DetailMailBox** : Données créées pour chaque nouvel utilisateur contenant des informations de type poids et espaces Outlook.
- **Doublons** : Stocke les doublons présents sur le drive de l'utilisateur afin de faciliter leur gestion.
- **EvolutionProfil** : Données inhérentes aux niveaux disponibles.
- **FichiersVolumineux** : Stocke les informations des fichiers volumineux.
- **habitudeImpressions** : Données sur les impressions.
- **MailingList** : Données liées à la personnalisation des catégories de mails.
- **notif_teams** : Données choix de notifications teams.
- **ProductionCO2Equipe** : Données de chaque équipe (code RG).
- **Profils** : Données d'utilisateurs.
- **TBL_Participants** : Données des participants inscrits aux
- **TmpDirectoryList** : Table temporaire pour l’exécution des algorithmes OneDrive. 
- **TmpFilesList** : Table temporaire pour l’exécution des algorithmes OneDrive. 

#### Numérique responsable - Variables d'environnement : 

- **var_appId_masuperapp** : contient le client ID. 
- **var_clientSecret_masuperapp** : contient le client secret. 
- **var_ecarbone_appId** : contient l’ID de l’application. 
- **var_carbone_audience** : contient l’url du tenant de l’environnement Dataverse(ex : https://orgxxx.crmxx.dynamics.com/). 
- **var_carbone_mail** : contient le mail de contact utilisateurs. 
- **var_ecarbone_secret** : contient le secret de l’application Azure.
- **var_ecarbone_teamsApps** : contient le lien. 
- **var_ecarbone_tenantId** : contient le tenant de L’application. 
- **Var_teamsApps_masuperapp.
- **Var_tenant_masuperapp.

#### Numérique responsable - Custom Connectors : 

- **GraphAPI-GetMyDrive-1** : connecteur personnalisé GraphAPI permettant d'établir une connexion directe avec Microsoft Graph, l'API unifiée de Microsoft pour accéder aux données et aux services de OneDrive. 
- **Microsoft Graph API-1** : connecteur personnalisé GraphAPI permettant d'établir une connexion directe avec Microsoft Graph, l'API unifiée de Microsoft pour accéder aux données et aux services de Outlook.

#### Numérique responsable - Flux : 

- **Analyse One Drive** : Collecter les données OneDrive de l'utilisateur. 
- **BtnApiGraph** : Collecter les mails de l'utilisateur en fonction de leurs poids. 
- **BtnApiGraph-Date** : Collecter les mails de l'utilisateur en fonction de leurs dates de reception. 
- **BtnApiGraph-Date-Sender** : Collecter les mails de l'utilisateur en fonction de leurs dates d'envoi. 
- **BtnApiGraph-Notif** : Collecter et classer les mails de type notifications. 
- **BtnApiGraph-Sender** : Collecter les mails envoyés en fonction de leurs poids. 
- **Btn-Delete-AllNotifications** : Supprimer les mails catégorisés comme notifications. 
- **Btn-GetNbNotifications** : Collecter les notifications d'acceptation et de refus. 
- **ChargementEquipe** : Collecter des données de suppression OneDrive et Outlook des utilisateurs d'une même équipe. 
- **DeleteDocOneDrive** : Récupérer les documents Onedrive, leurs poids et de les supprimer. 
- **DeleteMails** : Récupérer les mails, leurs poids et de les supprimer. 
- **Envoi_notifications_teams** : Gérer l'envoi d'une notification de résultat d'analyse. 
- **EnvoiRappelUtilisateur** : Gérer l'envoi d'une notification de fin de challenge en fonction du choix de l'utilisateur. 
- **ExportExcel** : Exporter SharePoint des statistiques de toutes les équipes. 
- **GetOneDriveSize** : Récupérer les données OneDrive de l'utilisateur. 
- **HistoriqueProfil** : Récupérer les données CO2 de du profil de l'utilisateur. 
- **Notif_Fin_Challenge** : Gérer l'envoi d'une notification prévenant de la fin d'un challenge. 
- **Notif_teams_Challenge** : Gérer l'envoi d'une notification de l'inscription à un challenge. 
- **PurgeTmpOneDrive** : Gérer la colonne de liste des fichiers temporaires de l'utilisateur une fois par mois. 
- **Volumineux-AnalyseOneDrive** : Gérer la récupération des documents OneDrive en fonction de leurs poids.

#### Numérique responsable - Références de connexions : 

- **GraphAPI-GetMyDrive - 1** : connexion à l'API GRAPH pour OneDrive. 
- **Microsoft Dataverse** : connexion à Dataverse. 
- **Microsoft Graph API - 1** : connexion à l'APIGRAPH pour Outlook. 
- **Office 365 Outlook NumriqueresponsableFlux-4967f** : connexion à Office365. 
- **OneDrive Entreprise NumriqueresponsableFlux-0b21b** : connexion au OneDrive Entreprise. 
- **SharePoint NumriqueresponsableFlux-246d2** : connexion aux sharepoint entreprise. 

#### Numérique Responsable : 

- **GestionImageEvolutionProfil** : Application de gestion de la table EvolutionProfil. 
- **Mon e-Carbone** : Application principale. 
- **Plateforme d'administration mon e-carbone** : Application de gestion des challenges et référentiel.



## 2.Installation des Solutions 

Ouvrez Power Apps et connectez-vous à votre compte. 
Dans Power Apps sélectionnez FICHIER > IMPORTER, sélectionnez le dossier local contenant les fichiers puis cliquez sur IMPORTER. 

Ordre de déploiement des solutions : 

#### 1.Numérique responsable – Tables (Voir le contenu plus haut) 

#### 2.Créer une application côté Azure : Lien vers la documentation Microsoft. 

L’application Azure permet l’appel de plusieurs ressources de la GRAPH API : 
- Récupération de la taille des courriels / boite courriels de l’utilisateur 
- Récupération de la taille du OneDrive de l’utilisateur 
- Notification Teams 

La liste des droits à affecter à l’application une fois créer : 

 

 

 

 

L’ensemble des éléments d’authentification sont à actualisé dans les variables d’environnement : 
**Solution : Numérique responsable - Variables d'environnement**
- Locataire : var_ecarbone_tenantId (ID du tenant Microsoft de votre entreprise) - Audience : var_ecarbone_audience (https://orgXXXX.crm.dynamics.com) 
- Client ID: var_ecarbone_appId 
- Secret ID: var_ecarbone_secret 

Ainsi que dans les 2 connecteurs personnalisés : 
- Microsoft Graph API – 1 
- GraphAPI-GetMyDrive – 1 

#### 3.Numérique responsable - Custom Connectors : 

Modifier les custom connectors pour ajouter les variables crées précédemment contenant vos Client ID et Secret ID. 
Retourner sur Azure : Il est impératif de générer les URL de redirection et de les associés dans l’application Azure (App Registration)  
EX : https://global.consent.azure-apim.net/redirect/  

#### 4.Numérique responsable - Variables d'environnement 

**!! N’oubliez pas de les renseigner.**
Actualiser l'application Azure avec l'adresse de retour.  

#### 5.Créer les références de connexion 

#### 6.Numérique responsable - Flux 

**!! Il est obligatoire d’avoir importé l’application des customs connectors et de créer et paramétrer l’application azure pour importer la solution des flux.** 
**!! Le flux btnApiGraph contient la variable var_ecarbone_mail (permettant le contact des utilisateurs avec le SAV de l’app) à modifier.** 

Les flux présents dans cette solution emploient vos variables d’environnement mises à jour précédemment. Tester chaque flux pour vérifier qu’elles soient toutes à jour. 

#### 7.Numérique Responsable 

Installer la solution 
