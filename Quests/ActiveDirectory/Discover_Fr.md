# Installation et Configuration d'Active Directory Domain Services (AD DS) sur Windows Server 2012 R2

<details>
  <summary><h2>Challenge</h2></summary>
  
Installe et configure Active Directory server en reprenant la machine virtuelle que tu as utilisé pour faire les quêtes sur le DNS et DHCP .

- 1- Installer le rôle AD DS sur Windows Serveur 2012 R2
- 2- Créer un domaine `wilders.lan`
- 3- Explique la procédure que tu as utilisée dans une documentation qui permet de reproduire ton installation et que tu postera comme solution à cette quête
</details>

<details>
  <summary><h2>Pré-requis</h2></summary>

- 1- Une machine virtuelle Windows Server 2012 R2 déjà configurée.
- 2- Les rôles DNS et DHCP doivent déjà être installés et configurés.
- 3- Un accès administrateur au serveur.

</details>

<details>
  <summary><h2>Étapes de l'Installation</h2></summary>

**1. Ouvrir le Gestionnaire de Serveur**  

- 1- Connectez-vous à votre serveur Windows Server 2012 R2.
- 2- Ouvrez le **Gestionnaire de serveur** (Server Manager).

**2. Ajouter le Rôle AD DS**

- 1- Dans le **Gestionnaire de serveur**, cliquez sur **Gérer** (Manage) en haut à droite, puis sur **Ajouter des rôles et fonctionnalités** (Add Roles and Features).
- 2- Dans l’assistant d’ajout de rôles et de fonctionnalités, cliquez sur **Suivant** jusqu’à arriver à l’étape **Type d’installation.**
- 3- Sélectionnez **Installation basée sur un rôle ou une fonctionnalité** (Role-based or feature-based installation) et cliquez sur **Suivant.**
- 4- Sélectionnez le serveur local (nom de votre serveur) et cliquez sur **Suivant.**
- 5- Dans la liste des rôles, cochez **Services de domaine Active Directory (AD DS).**
- 6- Une fenêtre apparaîtra pour indiquer les fonctionnalités supplémentaires nécessaires. Cliquez sur **Ajouter les fonctionnalités** (Add Features).
- 7- Cliquez sur **Suivant** jusqu’à l’étape de **Confirmation**, puis cliquez sur **Installer.**

**3. Promouvoir le Serveur en Contrôleur de Domaine**

Une fois le rôle AD DS installé, une notification apparaîtra dans le **Gestionnaire de serveur** pour finaliser la configuration.

- 1- Cliquez sur la notification indiquant **Promouvoir ce serveur en contrôleur de domaine.**
- 2- Dans l’Assistant Configuration Active Directory, sélectionnez **Ajouter une nouvelle forêt** (Add a new forest) car il s’agit d’un nouveau domaine.
- 3- Dans le champ **Nom de domaine racine** (Root domain name), entrez le nom de domaine souhaité : `wilders.lan`.
- 4- Cliquez sur **Suivant.**

**4. Configurer les Options du Domaine**

- 1- Choisissez le niveau fonctionnel de la forêt et du domaine. Pour Windows Server 2012 R2, laissez **Windows Server 2012 R2** sélectionné.
- 2- Cochez l'option **Serveur DNS** (DNS Server) pour installer le rôle DNS si nécessaire.
- 3- Entrez un mot de passe pour le **Mode de Récupération des Services Directory** (DSRM). Assurez-vous de le noter quelque part de sûr.
- 4- Cliquez sur **Suivant.**

**5. Configuration DNS**

- 1- Si un avertissement concernant la délégation DNS apparaît, cliquez sur **Suivant** pour continuer.
- 2- Vérifiez les paramètres de nom NetBIOS (il devrait être automatiquement configuré en fonction de votre domaine).
- 3- Cliquez sur **Suivant.**

**6- Chemins d'accès aux Dossiers**

- 1- Laissez les chemins d'accès par défaut pour la **Base de données**, le **Journal des Logs**, et le SYSVOL.
- 2- Cliquez sur **Suivant.**


**7. Vérifier la Configuration**
- 1- Sur l'écran **Options**, vérifiez que toutes les configurations sont correctes.
- 2- Cliquez sur **Suivant** pour continuer, puis sur **Installer** pour lancer l'installation.  
    **Remarque : Le serveur redémarrera automatiquement une fois l'installation terminée.**

**8. Vérification de l'Installation**

- 1- Après le redémarrage, connectez-vous avec les informations d'identification du domaine `wilders.lan`.
- 2- Ouvrez le **Gestionnaire de serveur** pour vérifier que les rôles AD DS et DNS sont bien installés et fonctionnent.

</details>

<details>
  <summary><h2>Tests Post-Installation</h2></summary>
  
- 1- Ouvrez **Utilisateurs et Ordinateurs Active Directory** (Active Directory Users and Computers) dans le menu **Outils** du Gestionnaire de serveur.
- 2- Vérifiez que le domaine `wilders.lan` est visible et accessible.
- 3- Créez un nouvel utilisateur pour valider la configuration :
  - Cliquez droit sur **Utilisateurs > Nouvel Utilisateur.**
  - Remplissez les informations requises, et créez l’utilisateur.
- 4- Assurez-vous que l'utilisateur nouvellement créé peut se connecter au domaine.

</details>

_Cette documentation permet de reproduire l’installation et la configuration d’Active Directory sur une machine virtuelle Windows Server 2012 R2 avec un domaine `wilders.lan`._
