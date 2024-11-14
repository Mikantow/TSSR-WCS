# Création d'une Unité d'Organisation, d'un Groupe d'Utilisateurs et d'un Utilisateur dans Active Directory pour `wilders.lan`

Après avoir configuré Active Directory avec le domaine `wilders.lan`, suivez ces étapes pour créer une Unité d'Organisation (OU), un groupe d’utilisateurs, et ajouter un utilisateur dans ce groupe.

<details>
  <summary><h2>Objectif</h2></summary>

1. Créer une Unité d'Organisation nommée **Wilders_students**.
2. Créer un groupe d’utilisateurs nommé **Students** au sein de cette OU.
3. Créer un utilisateur au sein de ce groupe.
</details>

<details>
  <summary><h2>Pré-requis</h2></summary>

- Accès administrateur à Active Directory avec le domaine `wilders.lan`.
</details>

<details>
  <summary><h2>Étapes de la procédure</h2></summary>

### 1. Créer l'Unité d'Organisation (OU)

1. Ouvrez **Utilisateurs et Ordinateurs Active Directory** (Active Directory Users and Computers) dans le menu **Outils** du **Gestionnaire de serveur**.
2. Dans la console, faites un clic droit sur le nom de domaine `wilders.lan`, puis sélectionnez **Nouveau > Unité d'Organisation**.
3. Nommez la nouvelle OU **Wilders_students**.
4. Cochez l'option **Protéger cet objet contre la suppression accidentelle** pour sécuriser l’OU.
5. Cliquez sur **OK** pour créer l'OU.

### 2. Créer le Groupe d’Utilisateurs

1. Dans l'OU **Wilders_students**, faites un clic droit, puis sélectionnez **Nouveau > Groupe**.
2. Nommez le groupe **Students**.
3. Laissez les options par défaut pour le **Type de groupe** (Sécurité) et la **Portée du groupe** (Global).
4. Cliquez sur **OK** pour créer le groupe.

### 3. Créer un Utilisateur dans le Groupe

1. Dans l'OU **Wilders_students**, faites un clic droit et sélectionnez **Nouveau > Utilisateur**.
2. Renseignez les informations de l'utilisateur :
   - **Prénom** : John
   - **Nom** : Doe
   - **Nom d’ouverture de session** : jdoe
3. Cliquez sur **Suivant** et configurez le mot de passe de l'utilisateur.
4. Décochez **L’utilisateur doit changer le mot de passe à la prochaine ouverture de session** si vous préférez que le mot de passe soit permanent.
5. Cliquez sur **Suivant** puis sur **Terminer** pour créer l’utilisateur.

### 4. Ajouter l'Utilisateur au Groupe Students

1. Faites un clic droit sur l'utilisateur **John Doe** (ou le nom d’utilisateur que vous avez créé) dans l'OU **Wilders_students**, puis sélectionnez **Propriétés**.
2. Accédez à l’onglet **Membre de** et cliquez sur **Ajouter**.
3. Entrez **Students** dans le champ de recherche, puis cliquez sur **Vérifier les noms** pour confirmer.
4. Cliquez sur **OK** pour ajouter l'utilisateur au groupe **Students**.

</details>

<details>
  <summary><h2>Vérification</h2></summary>

- Ouvrez **Utilisateurs et Ordinateurs Active Directory** et vérifiez que :
  - L'OU **Wilders_students** existe bien dans le domaine `wilders.lan`.
  - Le groupe **Students** est bien présent dans l'OU **Wilders_students**.
  - L’utilisateur **John Doe** est bien membre du groupe **Students**.

</details>

_Cette documentation permet de reproduire la création d'une Unité d'Organisation, d'un groupe, et d'un utilisateur dans Active Directory pour le domaine `wilders.lan`._
