# Mon-eCarbone


## Solutions nécessaires et objets liés

### Numérique responsable – Tables :

- Challenges: Données liées aux différents challenges créés.
- Company variables: Données liées à la personnalisation des différents liens et visuels.
- DataReference: Données d'équivalences carbone des outils collaborateurs.
- DetailMailBox: Données créées pour chaque nouvel utilisateur contenant des informations de type poids et espaces Outlook.
- Doublons: Stocke les doublons présents sur le drive de l'utilisateur afin de faciliter leur gestion.
- EvolutionProfil: Données inhérentes aux niveaux disponibles.
- FichiersVolumineux: Stocke les informations des fichiers volumineux.
- habitudeImpressions: Données sur les impressions.
- MailingList: Données liées à la personnalisation des catégories de mails.
- notif_teams: Données choix de notifications teams.
- ProductionCO2Equipe: Données de chaque équipe (code RG).
- Profils: Données d'utilisateurs.
- TBL_Participants: Données des participants inscrits aux challenges.
- TmpDirectoryList: Table temporaire pour l’exécution des algorithmes OneDrive.
- TmpFilesList: Table temporaire pour l’exécution des algorithmes OneDrive.

### Numérique responsable - Variables d'environnement

### Numérique responsable - Custom Connectors :

- GraphAPI-GetMyDrive-1: connecteur personnalisé GraphAPI permettant d'établir une connexion directe avec Microsoft Graph, l'API unifiée de Microsoft pour accéder aux données et aux services de OneDrive.
- Microsoft Graph API-1: connecteur personnalisé GraphAPI permettant d'établir une connexion directe avec Microsoft Graph, l'API unifiée de Microsoft pour accéder aux données et aux services de Outlook.

### Numérique responsable - Flux :

Flux:
- Analyse One Drive : Collecter les données OneDrive de l'utilisateur.
- BtnApiGraph : Collecter les mails de l'utilisateur en fonction de leurs poids
- BtnApiGraph-Date :Collecter les mails de l'utilisateur en fonction de leurs dates de reception
- BtnApiGraph-Date-Sender : Collecter les mails de l'utilisateur en fonction de leurs dates d'envoi
- BtnApiGraph-Notif : Collecter et classer les mails de type notifications
- BtnApiGraph-Sender : Collecter les mails envoyés en fonction de leurs poids
- Btn-Delete-AllNotifications : Supprimer les mails catégorisés comme notifications
- Btn-GetNbNotifications : Collecter les notifications d'acceptation et de refus
- ChargementEquipe : Collecter des données de suppression OneDrive et Outlook des utilisateurs d'une même équipe
- DeleteDocOneDrive : Récupérer les documents Onedrive, leurs poids et de les supprimer
- DeleteMails : Récupérer les mails, leurs poids et de les supprimer
- Envoi_notifications_teams : Gérer l'envoi d'une notification de résultat d'analyse
- EnvoiRappelUtilisateur : Gérer l'envoi d'une notification de fin de challenge en fonction du choix de l'utilisateur
- ExportExcel : Exporter SharePoint des statistiques de toutes les equipes 
- GetOneDriveSize : Récuperer les données OneDrive de l'utilisateur
- HistoriqueProfil : Récupeer les données CO2 de du profil de l'utilisateur
- Notif_Fin_Challenge : Gérer l'envoi d'une notification prévenant de la fin d'un challenge
- Notif_teams_Challenge : Gérer l'envoi d'une notification de l'inscription à un challenge
- PurgeTmpOneDrive : Gérer la colonne de liste des fichiers temporaires de l'utilisateur une fois par mois
- Volumineux-AnalyseOneDrive : Gérer la récupération des documents OneDrive en fonction de leurs poids

Références de connexions :
- GraphAPI-GetMyDrive - 1 NumriqueresponsableFlux-ae997: connexion à l'API GRAPH pour OneDrive.
- Microsoft Dataverse NumriqueresponsableFlux-fdaa6 : connexion à Dataverse
- Microsoft Graph API - 1 NumriqueresponsableFlux-f2220 : connexion à l'APIGRAPH pour Outlook
- Office 365 Outlook NumriqueresponsableFlux-4967f : connexion à Office365
- OneDrive Entreprise NumriqueresponsableFlux-0b21b : connexion au OneDrive Entreprise
- SharePoint NumriqueresponsableFlux-246d2 : connexion aux sharepoint entreprise


### Numérique Responsable :

Applications:
- GestionImageEvolutionProfil: Application de gestion de la table EvolutionProfil.
- Mon e-Carbone: Application principale.
- Plateforme d'administration mon e-carbone: Application de gestion des challenges.

Rôles de sécurité:
- AdministrateurMone-Carbone: Rôle d'administration des applications.
- UtilisateurMone-carbone: Rôle d'utilisateur de l'application Mon E-carbone.

### Ordre de déploiement des solutions :

1. Numérique responsable - Table.
2. Numérique responsable - Variables d'environnement.
3. Créer une application côté Azure: [Lien vers la documentation Microsoft](https://learn.microsoft.com/fr-fr/entra/identity-platform/quickstart-register-app).
4. Numérique responsable - Custom Connectors: Modifier les custom connectors pour ajouter le Client ID et le Secret ID. Actualiser l'application Azure avec l'adresse de retour. Créer les références de connexion.
5. Numérique responsable - Flux.
6. Numérique Responsable.
