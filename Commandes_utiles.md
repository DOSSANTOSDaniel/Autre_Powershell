# Commandes utiles

## Lancer une commande en tant que administrateur

```Powershell
powershell Start-Process powershell -Verb runAs
```

## Télécharger un fichier à partir d'un site web

```Powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-kali-linux-new -OutFile Kali-linux.appx -UseBasicParsing

ou

curl.exe -L -o ubuntu-2004.appx https://aka.ms/wsl-ubuntu-2004
```

## Renomer un fichier

```Powershell
Rename-Item .\Ubuntu.appx .\Ubuntu.zip
```

## Décompresser un fichier ZIP

```Powershell
Expand-Archive .\Ubuntu.zip .\Ubuntu
```

## Metre à jour windows

PSWindowsUpdate est un ensemble de commandes permettant de gérer le client Windows Update.

Installation de PSWindowsUpdate :

```Powershell
find-Module PSWindowsUpdate
Install-Module -Name PSWindowsUpdate -Force
Import-Module PSWindowsUpdate
```

Voir les commandes possibles :
```Powershell
Get-Command -Module PSWindowsUpdate
```

Afficher les mises à jours disponibles :

```Powershell
Get-WindowsUpdate
```

Installation des misess à jours disponibles :

```Powershell
Install-WindowsUpdate -AcceptAll -AutoReboot
```
Avec la création de logs :

```Powershell
Install-WindowsUpdate -AcceptAll -Install -AutoReboot | Out-File "c:\logs\$(get-date -f dd-MM-yyyy_HH-mm)-WinMSJ.log" -force
```

Installation d'une mise à jour en particulier :

```Powershell
Get-WindowsUpdate -KBArticleID "KB1234567" -Install
```

Ne pas installer une mise à jour en particulier :

```Powershell
Install-WindowsUpdate -NotKBArticle "KB1234567" -AcceptAll
```
