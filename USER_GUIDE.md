
Introduction : aperçu du système et de son objectif  
Utilisation de base : comment utiliser les fonctionnalités clés  
Utilisation avancée : comment utiliser au mieux les options  
Dépannage : solutions aux problèmes connus et communs  

## john the ripper
C'est un logicile libre de crackage de mots de passe .

## utilisation de base
Pour utiliser **john the ripper** il nous faut un dossier compréssé sécurisé que l'ont peut créer en zip ou rar entre autre . ( Pour notre présentation ça sera zip )

Pour facilité l'utilisation de **JTR** nous allons commencer par créer des alias avec la commande :

```Bash
sudo snap alias john-the-ripper.zip2john zip2john
```

```Bash
sudo snap alias john-the-ripper.keepass2john keepass2john
```

Nous allons ensuite "envoyé" **JTR** sur le dossier ciblé en redirigeant la sortie dans un fichier texte pour recupérer le hashe du mot de passe avec la commande :

```Bash
zip2john /home/user/Bureau/dossier-cible.zip > hash.txt
```

Une fois le _hashe_ récuperer il nous reste simplement a le décripté en utilisant la commande :

```Bash
john hash.txt
```

Voila pour l'utilisation de base .

## Utilisation avancé

Dans les fonctions avancé nous allons trouver l'attaque par _dictionnaire_ .

### L'attaque par dictionnaire

Pour ce faire il nous faut une liste de mots de passe que l'ont peut télécharger sur [ openwall ](https://www.openwall.com/john/) ou ailleurs.

Les premières étapes sont les mêmes que vu ci-dessus on commence par récupérer le _hashe_ du fichier cible , une fois fait on "envoi" **john** mais cette fois ci avec l'attaque par dictionnaire pour ce faire on utilise la commande :

```Bash
john -w= /home/user/Bureau/password.lst hash.txt
```

Une fois le _hashe_ récupérer nous utiliserons la commande suivante pour le décrypter et l'afficher :

```Bash
john --show hash.txt
```

Cela vas nous permettre d'afficher le mot de passe plutot que de l'envoyer dans un dossier.

Et voila le travail !

Pour voir toutes les options disponibles avec **john** vous pouvez tapez la commande suivante :

```Bash
john
```

Ce qui nous permettras d'afficher dans le terminal toutes fonctions disponibles .

## Dépannage

#### Les problèmes courants :

- **John** ne trouve pas le dossier demandé ou la wordlist ?

  Pour résoudre se problèmes il suffit bien souvent de vérifié le chemin d'accès .

- En tapant _zip2john_ le terminal affiche commande introuvable ?

  Vérifier que les alias ont été correctement créer .

 Voila pour les problèmes les plus courants toutefois pour des information detaillées je vous invite a vous rendre sur le [ site officiel ]( https://www.openwall.com/john/)
