# Prosit 6 – Framework .net

## Mots clés :
- DLL :
- COM / DCOM :
- VC++ :
- ASP :
- VB6 :
- API
- Taux de réutilisation
- Annuaire
- Environnement Microsoft- Framework / Cadre de travail :

## Contexte

**Quoi ?** :- Problème de DLL- Augmenter le taux de réutilisation

**Comment ?** :- Avec un environnement Microsoft- Utiliser le framework .net

**Pourquoi ?** :- Augmenter l'efficacité de production

## Contrainte

Aucunes contraintes

## Problématique

Comment augmenter la productivité d'une entreprise avec un environnement Microsoft ?

Comment augmenter la productivité en augmentant le taux de réutilisation tout en évitant de remplacer les DLL ?

Comment trouver un cadre de travail commun pour tous ?

## Généralisation
- Centralisation +
- Généralisation +
- Normalisation +
- Productivité =
- Cadre de travail

## Hypothèse
- Il existe un framework qui permet de proposer un cadre de travail commun (.net)
- On peut utiliser .net pour avoir une seule technologie au sein d'un projet- Il existe un moyen d'éliminer les problèmes de nommage des DLL
- .net permet de contrôler le noms des DLL

## Plan d'action

Etudes :
### Framework Microsoft

.net est un framework qui fournis une vue orientée objet de windows: il encapsule de nombreuses fonctionalitées en classes. Il gère la sécu, le versioning et surtout tous les languages .NET sont intercompatibles

archi .net
![Image result for .net architecture](https://www.aapnainfotech.com/wp-content/uploads/2015/12/netframework4.5.png))

CLR: charge et fait tourner les aplli 

historique:
- 1.0 et Visual Studio .NET 2001
- 1.1 et Visual Studio 2003 transition 1.1 à 2.0 à eu des petits pb de compatibilité
- 2.0 et VS 2005 avec SQL 2005
- 3.0 2006 (WCF, WPF, WF et CardSpace)
- 3.5 2007 avec VS 2008 t SQL 2008

.net 2.0 représente la maturité du framework:
- un ensmeble stabilisé
- un IDE dédié entièrement à lui (visual studio)
- sert de fondation aux évolutions

il fournit à Microsoft une fondation technique unique pour Windows et les logiciels

3.0 + SP1:
- Windows Presentation Foundation
- Windows Communication Foundation
- Windows Workflow Foundation
- Windows CardSpace

.net 3.5:
- LINQ
- ASP.NET 3.5
- CLR add-in Framework
- autres améliorations

compilation et exécution:
CLR: common language runtime
code source->language compile->assembly


VS 2008 évo de 2005, pour dev en .net mais tout simplement pour tt en windows
pesé autour de 3 axes: 
- la prod: migration facile
- collab, gestion de projet(sur team system): pas abordé

permet le dev: pc, server, web(slverlight) , office

peut faire du multiplateforme pour le web (mac os 10, linux)


MSDN: abo avec VS qui donne accès la software assurance (les versions suivante et précédenes gratuites), acccès au windows serv et sql serv de microsoft pour le test, accès à un support
 
DLR: comme la CLR pour les langages dynamiques, fonctionne sur Windows Mac OS X et linux et elle est open source permet d'utiliser des langages dynamiques comme le Python ou le Ruby

Prall FX: extenson qu'on ajoute qui permettent de paraléliser les requêtes link qui gère la répartition des charges matérielles

site msdn: miscrosft developper network: la doc et les forums pour le .net
codeplex: forge .net
Mono: porte le .net (clr et copil) sur linux
moonlight: comme mono mais pour le .net web
 
 groupes utilisateurs : atoutFox, FX UG, DUG




dans .net ona :
un env d'exécution
plein de lib(framework class lib)



### .net- DLL

Dynamic-link library: bibliothèque logiciel dont les fonctions sont charge en mémoire par un programme, au besoin, lors de son exécution par opposition aux lib logicielles statiques ou partagées dont les fonctions sont chargées en mémoire avat le début de l'exécution du programme

elle existent depuis 1985 et sont une des fondations des OS windonws et sont utiliséspour les aPI, les drivers, les widgets et les polices de caratères??

fonctionnement:
il xiste 3 types de lib:
**statiques**:
incorporée dans le programme, si on la modif et il fau rebuild le prog

**Partagées**
pas inclue dans les progs qui l'utilise  mais liée au prog lors du chargement, si on la modif pas besoin de rebuild le programme

**Dynamique**
comme les partagées mais utilisées de manière diférente: elles sont reliées à l'appli que lorsqu'elle en a bsoin et les prog les utilisant on des instruction pour charger la lib et faire la liaison

pour dll l'opération de liaison est exécutée en 2 temps: à la construction de l'appli l'éditeur de lien créé des connecteurs et au chargement les connecteurs sont reliés entre eux

les foncions internes de windows sont mises à dispo par des API mises en oeuvres par des DLL. LEs trois principales sont User32.dll (manip de l'interface utilisateur), GDI32.dll (manip des dispositifs d'impression et d'affichage) et Kernel32.dll (utilisation des fonctions du kernel Windows sur les fichiers et les processus

Réalisation :
- Corbeille d'exercice
