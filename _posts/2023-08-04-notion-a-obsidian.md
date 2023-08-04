---
layout: post
title: Adieu Notion, bonjour Obsidian
subtitle: Pour un environnement d'écriture plus sain
tags: [knowledge, écriture, dev, blogging]
comments: true
img-cover: ../assets/postsAssets/2023-08-04-notion-a-obsidian-assets/header.jpg
---

Depuis longtemps, je suis à la recherche d'une solution d'écriture flexible: pour prendre des notes, trier mes ressources, documenter et gérer mes projets, blogger etc. J'ai abordé cette problématique de nombreuse manière et on peut dire sans trembler que Notion est une solution intéressante. Toutefois, aujourd'hui, je vais vous présenter une alternative.

Notion est un très bon outil, cet article n'est pas là pour dire le contraire. Ils innovent à fond avec un design de qualité, rein à dire. Mais j'y vois plusieurs problèmes aujourd'hui :

- Dépendence technologique
- Le prix 
	d'environ 5 euros + 10 euros d'IA par mois.
- Le stockage des données tout en cloud
	sans internet, il n'y a pas d'accès aux données.
- L'export en PDF et en Markdown n'est pas terrible.
- L'outil est complexe
	il est difficile de demander à des gens non technophiles de l'utiliser.
- Donnée difficielement accessible.
- Opaque
- Trop centraliser
	Obligation de séparer la documentation d'un projet locale

Je souhaite donc migrer vers une nouvelle manière de travailler et je pense avoirs trouver une solution interessante que vous partage ici.
## Mark down && Obsidian && Git && Jekyll

> ⚡ À première vu, je vous propose quelque chose de plus complexe qu'un simple logiciel, mais attendez un peu ! Il s'agit plutôt de combiner plusieurs outils et de remplacer l'application Notion par un environnement de travail.

#### Type de fichier : MarkDown
Le [Markdown](https://fr.wikipedia.org/wiki/Markdown) est un langage de balisage léger. Les fichiers Markdown ont pour extension <u>.md</u>. Le Markdown nous permet d'écrire du texte sans l'aide d'un éditeur ou d'un logiciel particulier, comme dans un fichier <u>.txt</u>. L'un de ses avantages est sa légèreté d'utilisation, car il ne requiert pas d'outils spécifiques, et sa compatibilité avec de nombreux supports. Le Markdown est largement utilisé sur le web, les applications, les blogs, les messageries, etc. De plus, il est très facile de migrer d'un outil à un autre si nécessaire. De manière générale, le Markdown nous permet de réaliser tout ce qu'un éditeur de texte avancé peut nous offrir.


Exemple de mark down sans rendu : 
```
# Saxumque promissa orbam At ieiunia salutant sors
## Fingi curvamine putares pulsis

Lorem markdownum concipit sectos. Cum fama stabulorum molarem omnia [genitore
Baucis pariterque](http://iugalia.net/) genetrix Pleias materque terras frena
conprecor *arsit mora* in omnes. Est viribus tale nihil deo, longoque culpetne
aurea tum sparsos asper curvamine crimina inque [bene
partus](http://demensquem.org/quasque). Super quaterque iuris harundinis fugit
laticem umente, in gerunt quid caelum optato ira, est.

    if (cdDefragment) {
        view_passive.macintosh_android_open += abend_ripping;
    }
    spriteDataType.dashboardClientUp.whitelist_cron(addressBounce, menuSanBot(5,
            638071) + utf_finder, 1 + server_icon);
    if (pplSocial) {
        rom += forumRom(5);
        digital_xmp_font = lossy_encryption_dock + 5;
    } else {
        icioXslt += drm;
    }
    twitterStorage = surgeRadcabInbox;
    data_scrolling *= networkingBcc + 1;

```
#### Interface : Obsidian
[Obsidian](https://obsidian.md/) est une application qui permet d'écrire et de visualiser le rendu du Markdown directement à partir de fichiers locaux sur votre machine. On peut le voir de base comme un éditeur et un lecteur de markdown (avec tout plein de raccourcis pour accélérer le processus !).

Il a une logique un peu particulière en termes d'organisation de dossier. Tous les fichiers créés sont contenus dans un "vault", un coffre en français, qui est l'équivalent du dossier racine. À chaque nouvelle note, Obsidian créé un nouveau fichier `.md` et l'ajoute dans le dossier choisi. En réalité, Obsidian gère simplement un dossier avec de simples fichiers `.md`, puis les rends visible via son interface. Ce dossier est comme un autre sur votre machine (peu importe le système), à l'emplacement que l'on souhaite, et c'est la raison principale qui, à mon avis, rend ce **workflow HYPER versatile.**

De base, Obsidian ne gère que le Markdown, c'est assez maigre par rapport à ce que Notion propose. Un autre gros atout d'Obsidian, c'est sa communauté. Il existe un grand nombre de plugins qui permettent d'augmenter les fonctionnalités du logiciel et n'importe qui peut en développer de nouveaux. Et il y a des choses assez incroyables qui se rapprochent énormément de Notion : calendrier, Kanban, IA, base de données, etc.!

Exemple de formatage graphique du markdown :

![](../assets/postsAssets/2023-08-04-notion-a-obsidian-assets/md.jpg)

Exemple de structuration de fichiers, dans Obsydian et dans un explorateur de fichier :

![](../assets/postsAssets/2023-08-04-notion-a-obsidian-assets/md2.jpg)
### Synchronisation ou versionning avec Git

Obsidian intègre un outil pour stocker notre dossier dans le cloud moyennant paiement. Par défaut, tout est en local et pas de cloud. **MAIS**, étant donné que la base est un simple dossier, nous pouvons utiliser ce dossier comme un repo Git et versionner tout son contenu pour le sauvegarder, le partager entre différents périphériques et même collaborer à plusieurs. On pourrait même imaginer utiliser d'autre outils, comme Dropbox par exemple

Il existe un plugin Git qui permet de gérer cela facilement à l'intérieur d'Obsidian et de ne pas avoir à passer par un terminal. Nous pouvons même l'utiliser pour faire des sauvegardes automatiques toutes les X minutes, trés confortable.

![](../assets/postsAssets/2023-08-04-notion-a-obsidian-assets/git-preview.mkv)

### Blogging avec Jekyll

Cela mériterait un post dédié, mais pour faire simple, Jekyll est un générateur de site statique qui utilise des fichiers `.txt` ou `.md`. Il prend un dossier de fichiers (par exemple en markdown 😎), les traite et génère un site complet en HTML et CSS. Nous pouvons donc générer n'importe quel type de site via le terminal, sans avoir besoin d'un gros serveur ni d'une configuration backend, tout est traité sur la machine et envoyé en ligne. Cette solution est totalement compatible avec Obsidian.

Obsidian nous sert donc d'interface de gestion de contenu du site et tout peut être automatisé sur GitHub Pages gratuitement. C'est une sacrée synergie :

Dossier local -> géré par Obsidian -> Push sur un repo GitHub -> Déploiement automatique avec GitHub Pages



Pour terminer, je vais lister les plus et les moins de ce workflow. 
### 😍 :
- Adaptabilité 
	Je pense que ce workflow peut gérer tout type de document, qu'il s'agisse de gestion de projet, de blog, de listes de ressources, etc.
- Décentralisation 
	`Un coffre/dossier racine == un projet` Tout n'est pas centralisé dans un logiciel qui rend les choses opaques. Chaque projet peut contenir son propre "coffre-fort" dédié, ce qui évite de tout mélanger.
- Accessibilité 
	J'ai accès à mes fichiers même hors connexion.
- Simplicité d'accès 
	N'importe qui peut utiliser n'importe quel logiciel pour éditer ces markdowns sans casser le système. Il n'est pas nécessaire de contraindre mes collaborateurs à un logiciel particulier.
- Compatibilité 
	Un nombre incalculable d'outils est compatible avec le markdown, même sur le web. Même WhatsApp est compatible. 
	![](../assets/postsAssets/2023-08-04-notion-a-obsidian-assets/whatsapp.png)
- Léger en ressources
	Méthodologie compatible avec un grille pain 🍞 🤖

### 😥 :
- sans sync, l'écritures collaborative reste complexe
	À moins que vous ne testiez d'autres solutions, la gestion de version avec Git n'est pas faite pour tout le monde. Même si je ne comprends pas pourquoi les écrivains ne s'y mettent pas…
- Bidouille
	Ce n'est pas une solution clé en main, cela demande pas mal d'efforts mais j'ai travaillé de cette façon pendant deux semaines et je dois dire que c'est très satisfaisant.


Si vous avez des questions, n'hésitez pas ! 
Bye


#### Quelques resources supplémentaires, des plugins cool :
- [https://obsidian.rocks/dataview-in-obsidian-a-beginners-guide/](https://obsidian.rocks/dataview-in-obsidian-a-beginners-guide/)
- [https://github.com/lynchjames/obsidian-day-planner](https://github.com/lynchjames/obsidian-day-planner)
- [https://github.com/tgrosinger/advanced-tables-obsidian](https://github.com/tgrosinger/advanced-tables-obsidian)

