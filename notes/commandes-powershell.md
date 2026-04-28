# ⚡ Commandes PowerShell — Active Directory

> Commandes pratiquées lors du lab TryHackMe "Active Directory Basics"

---

## 🔐 Gestion des mots de passe

### Réinitialiser le mot de passe d'un utilisateur
```powershell
Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
```

### Forcer le changement de MDP à la prochaine connexion
```powershell
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose
```

---

## 👤 Gestion des utilisateurs

### Lister tous les utilisateurs du domaine
```powershell
Get-ADUser -Filter *
```

### Chercher un utilisateur spécifique
```powershell
Get-ADUser -Identity "m.dupont" -Properties *
```

### Désactiver un compte utilisateur
```powershell
Disable-ADAccount -Identity "m.dupont"
```

### Réactiver un compte
```powershell
Enable-ADAccount -Identity "m.dupont"
```

---

## 👥 Gestion des groupes

### Lister les membres d'un groupe
```powershell
Get-ADGroupMember -Identity "Domain Admins"
```

### Ajouter un utilisateur à un groupe
```powershell
Add-ADGroupMember -Identity "GRP_Comptabilite" -Members "m.dupont"
```

---

## 🖥️ Gestion des ordinateurs

### Lister tous les ordinateurs du domaine
```powershell
Get-ADComputer -Filter *
```

---

## 📁 Gestion des OU

### Lister les Unités d'Organisation
```powershell
Get-ADOrganizationalUnit -Filter *
```

---

> *Notes prises lors du lab TryHackMe — Active Directory Basics (100% complété)*
