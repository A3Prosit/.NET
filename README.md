# Prosit 6 – Framework .net

  

## Mots clés :

-   DLL :
    
-   COM / DCOM :
    
-   VC++ :
    
-   ASP :
    
-   VB6 :
    
-   API
    
-   Taux de réutilisation
    
-   Annuaire
    
-   Environnement Microsoft
    
-   Framework / Cadre de travail :
    

  

## Contexte

Quoi ? :

-   Problème de DLL
    
-   Augmenter le taux de réutilisation
    

Comment ? :

-   Avec un environnement Microsoft
    
-   Utiliser le framework .net
    

Pourquoi ? :

-   Augmenter l'efficacité de production
    

  

## Contrainte

Aucunes contraintes

  

## Problématique

Comment augmenter la productivité d'une entreprise avec un environnement Microsoft ?

Comment augmenter la productivité en augmentant le taux de réutilisation tout en évitant de remplacer les DLL ?

Comment trouver un cadre de travail commun pour tous ?

  
  
  

## Généralisation

-   Centralisation +
    
-   Généralisation +
    
-   Normalisation +
    
-   Productivité =
    

-   Cadre de travail
    

  

## Hypothèse

-   Il existe un framework qui permet de proposer un cadre de travail commun (.net)
    
-   On peut utiliser .net pour avoir une seule technologie au sein d'un projet
    
-   Il existe un moyen d'éliminer les problèmes de nommage des DLL
    
-   .net permet de contrôler le noms des DLL
    

  

## Plan d'action

Etudes :

-   Framework Microsoft
    
-   .net
    
-   DLL
    

Réalisation :

-   Corbeille d'exercice


## Le .NET :
.NET - Microsoft : Outil pour développer sur toutes les plateformes microsoft
  
Au coeur de .NET Framework : << Voir internet image >> --> "Visual Studio" englobe le tout

### Historique
Avant .Net :
- Plateforme hétérogène avec différents modèles de dev ( VB / MFC / WIN32 {...} )
- Arrivée de .net 1999/2000 

.NET 1.0 ⇒ 2001

.NET 2.0 : Marque la maturité du framework .Net  ==> 2005 /!\ Compatibilité 1.0
- Ensemble stabilisé
- IDE dédié entièrement à lui
- Sert de fondation à l'évolution actuelle
   
  .NET 3.0 : 
  - Présentation
  - Communication
  - Workflow
  - Dev mobilie

.NET 3.5 : 
- LINQ :  Couche d'accès aux donnée
{...}

.NET 4.0 :  F# / P€ (parallélisé) {...}

⇒ Actuellement en V.4.7.2

### La Compilation :

Source Code ⇒ Language Compiler ⇒ Assembly (avec la VM, que l'on appelle CLR common language runtime ⇒ Reste celui de la 2.0)
VM ⇒ Va prendre la partie qu'elle a besoin et va la faire tourner sur  l'environnement ⇒ Code bas niveau géré et secure + briques pour produire

### Les composantes :
- Trois axes :
	- Productivité : Migration / LINK (couche accès données)
	- Team Systèmes : Gestion de projet (Cycle de vie d'un projet...)
	- Expérience utilisateur : Office {...} Développeur / designer

Games, on peut passer de l'une à l'autre :
- Express : amateurs / fonctionnalités limitées
- Professional : Tout à la version actuelle
- Standard Edition + MSDN : Pour les développeurs seuls ou en petites équipes, MSDN est un abo pour obtenir toutes les versions à venir + forums de discutions avec Microsoft.
- Team System : Pour les équipes, solution de gestion d'un cycle de vie d'un projet logiciel

Ps : On a un "micro Framework & Compact Framework" : ⇒ Mobilité, enfouie, embarquée :  Cafetière, frigo, montre... peut 'booter lui même'

### Ce qu'on peut faire avec

- Services 
- Windows App ⇒ WPF
- Web Apps ==> ASP.net (supporter Ajax...) + Fonctionnalités Silverlight
- Office Apps (Excel ⇒ Office...)
- Mobile Apps


*Silverlight* : Technologie (plugin) adressable depuis visual studio, applications internet riche, avec interface riche (3D, ombrages, transparent {...} )
DLR ** Dynamic Language Runtime**  : Ruby, VBX (surtout orienté web)
	- Dynamique
	- Silverlight
	- Compatible Windows / MAC OS / Linux
	- Open Source (ex : projet Moonlight)

CLR : Langages statiques C# / Java / VB

Année du multicore : 
- Parall FX: Extensions .NET pour paralléliser des requêtes LINK ou algo en multi-thread
- 
### Divers : 

Codeplex <==> Ancien Github Microsoft
Mono : Développer des applis microsoft sur d'autres environnements ⇒ Linux
CPL : Communauté
Groupes utilisateurs : UG : AtoutFox / FXUserGroupe / dugfr

## Le Garbabe Collector [GC] (ramasse miette) :

- JVM / CLR a la responsabilité d'allouer de la mémoire pour stocker l'objet en question dans une zone réservée : "tas" ou "heap".
- Le rôle d'un Garbage Collector sera de bâtir des graphes d'objets en partant des références racines (référence permettant au programme d'atteindre l'objet) et en parcourant récursivement toutes les références rencontrées. Dès qu'un objet est supprimé, il doit être effacé du graphe, et sa **mémoire récupérée**.

Algorithmes : 
- **Mark and Sweep** : 
	- Plus simple et plus connu
	- Lors exécution, tous les objets sont marqués ==> Accéssible
	- Lors du deuxième tour, il joue du balayeur (sweep), en parcourant tous les objets non marqués pour les supprimer.
	- PRO/CONS
		- Temps exécution proportionnel à la taille du tas
		- Laisse le tas fragmenté
		- Fonctionne mal si les objets n'ont pas une taille globale uniforme
- **Collecte par recopie (stop & copy)** : 
	- Découper l'espace d'allocation mémoire (tas), en deux parties égales. 
	- Les objets référencés dans le premier espace sont copiés dans le second espace
	- On met à jour les références de l'application pour pointer vers le deuxième espace.
	- Tous les objets "vivants" sont copiés vers le premier espace. 
	- PRO/CONS
		- Compacter automatiquement le tas (no fragmentation)
		- Problème entre données pointeurs et entières
		- Copie systématique (et inutile) d'objets qui ont une durée de vie importante
		- Pause bloquantes et potentiellement longue
**3 Familles de CG**
- Conservatifs : "dans le doute s'abstenir" pour éviter les problèmes mémoire contenants un pointeur
- Incrémentaux : Partitionner en plusieurs parties cohérentes, que l'on peut déclencher indépendamment des unes et des autres. ⇒ Pas bloquer lors de recopie, et applications plus fluides
- Générationnels : On met une zone spéciale pour les objets "immortels" ou trop volumineux, et une autre pour les objets qui sont crées dynamiquement (voués à disparaître rapidement).

**Le GC .NET**
- Compromis entre le Mark & Sweep et la collecte par recopie : "Mark and Compact"
- A chaque collecte, le CG bâtit les graphes d'objets atteignables à partir de chaque référence racine
- Tour  : Parcourt le tas linéairement objet par objet. Chaque fois qu'il trouve un objet non référencé, sa mémoire est "libre". Les objets qui ne sont pas touchés dans le second tour, sont recopiés vers le bas du tas, pour écraser la zone mémoire libre, et compacter le tout. Les références sont mises à jours. (Sauf si +20 Ko ⇒ Stockés dans un endroit du tas et pratiquement jamais recopié)

/!\ Si mémoire est pleine, le cycle de collecte ne s'exécute pas.

## Les assemblys : 
Avant, on enregistrait les références des programmes, des dll... Dans le registre. Quand il y avait deux dll du même nom, ou plusieurs versions d'une même dll, ou que l'on déplacait un programme... Grosse pagaille.

- Une assembly est une collection de types et de ressources, qui représente une **unité logique de fonctionnalités**
- En .NET :
	- Contient du code CIL (Common Intermediate Language) et des informations supplémentaires afin de prévenir des erreurs de versions et d'accroître la sécurité. Ce code est compilé par le compilateur C#.
	- Le code CIL est ensuite compilé par le CLR en code machine, et exécutable.
Ils peuvent être : 
- Applications & fichiers exécutables (.exe), aussi appelés PE (portable executable)
- Bibliothèques de types (Dynamic Link Librairies), d'extension .dll

Il se caractérise par :
- nom
- version
- ID de culture
- Clé publique

Dans le manifeste de l'assembly  : 
- La liste de l'ensemble des fichiers (exe, dll, données, images, ressources...)
- Les méta données (descriptifs types, classes publiques...)
- Enumération des autres assembly
- Ensemble des autorisations requises pour que l'assembly fonctionne


