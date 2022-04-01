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
