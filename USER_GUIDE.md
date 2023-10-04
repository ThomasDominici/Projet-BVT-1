
Introduction : aperçu du système et de son objectif  
Utilisation de base : comment utiliser les fonctionnalités clés  
Utilisation avancée : comment utiliser au mieux les options  
Dépannage : solutions aux problèmes connus et communs  

## john the ripper
c'est un logicile libre de crackage de mots de passe .

## utilisation de base
Pour utiliser john the ripper il nous faut un dossier compréssé sécurisé que l'ont peut créer en zip ou rar entre autre . ( pour notre présentation ça sera zip )

Pour facilité l'utilisation de JTR nous allons commencer par créer des alias avec la commande :

```Bash
sudo snap alias john-the-ripper.zip2john zip2john
```

Nous allons ensuite "envoyé" JTR sur le dossier ciblé en redirigeant la sortie dans un fichier texte pour recupérer le hashe du mot de passe avec la commande :

```Bash
zip2john /home/user/Bureau/dossier-cible.zip > hash.txt
```

Une fois le hashe récuperer il nous reste simplement a le décripté en utilisant la commande :

```Bash
john hash.txt
```

Voila pour l'utilisation de base .

## Utilisation avancé

