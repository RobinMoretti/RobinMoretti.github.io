---
layout: post
title: Brick Breacker - Log #1
subtitle: Log de développement
tags: [log, dev, mobile game, 🧱 Brick Breaker]
comments: true
---

Je suis assez content d'enfin voir les choses avancer depuis que j'ai résolu mes problèmes de gestion du `pixel perfect`, qui ont simplement disparu en passant à la dernière version de Unity3D, que je conseille fortement, tellement de nouvelles choses vraiment cool. Les outils `pixel perfect`  sur les versions précédentes ne sont vraiment pas stable.

![](/assets/postsAssets/2021-12-12-brick-breaker-log-1/PreviewUI.mov)

Bref j'ai terminé, la transition de scnène, le chargement et la gestions des niveaux, le paneau de régale et le système de sauvegarde, qui était beaucoup plus simple à gérer que ce que j'imaginais, grâce aux classes `FileStream` et `BinaryFormatter` qui permettent d'enregistrer dans un ficher n'importe quel instance d'objet/variable. `Application.persistentDataPath` nous permet de laisser gérer Unity pour choisir automatiquement le chemin selon la plateform (merci seigneur). Persitent signifie que la donnée pourras être rechargé plus tard.  

```csharp
public static void saveDataInFile(string path, object data){
    BinaryFormatter formater = new BinaryFormatter();
    
		path = Application.persistentDataPath + path;
   
    FileStream stream = new FileStream(path, FileMode.Create);

    formater.Serialize(stream, data);

    stream.Close();
}
```

Le système de niveau est aussi (+ ou -) terminé. 1 palier de niveau contient 4 niveau. Chaque niveau possède 4 succès:

- Terminer le niveau avec au moins une vie
- Terminer le niveau avec 3 vie
- Terminer le niveau dans le temps imparti
- Terminer le niveau en mode difficile

4 succès collecté de débloques le palier supérieur. 

L'objectif maintenant, c'est de réaliser les trois premiers paliers (donc 4 niveaux avec un niveau difficile pour chaque == 3 * 5 = 15).  

Voilà le premier palier (assez simple) avec toutes sorte de bars contrôlables. 

![Niveau-1.png](/assets/postsAssets/2021-12-12-brick-breaker-log-1/Niveau-1.png)

![niveau-4.png](/assets/postsAssets/2021-12-12-brick-breaker-log-1/niveau-4.png)

![Niveau-2.png](/assets/postsAssets/2021-12-12-brick-breaker-log-1/Niveau-2.png)

J'ai besoin d'avoir une bar contrôlable qui suit un chemin prédéfini. Le plus simple serait d'avoir un chemin éditable, un peu comme sur illustrator, pour que je puisse enchaîner la création de beaucoup de niveaux.

Un stream uploadé sur youtube, de la boss Freya Holmèr, game dev, enseignante et streameuse, m'a introduit à la création de mesh procédural. C'est probablement la meilleure introduction que je connais sur le thème. Le rythme très est tranquille, six heures de vidéo découpée en plusieurs étapes.

Pour info Feya Holmer, c'est une boss++ qui à créé le premier outils de création de sharder en noeudale (shader forge) il y a quelques années et qui a récemment publié un outils de dessins vectoriel dans unity, **[Shape](https://www.notion.so/Brick-Breacker-Log-1-476cbe6378014cecbfd419b9a023925e?pvs=21)**.

[https://www.youtube.com/watch?v=6xs0Saff940&t=14325s](https://www.youtube.com/watch?v=6xs0Saff940&t=14325s)

⚠️ Deux warnings, c'est en anglais, les potos faut s'y mettre, et faut avoir je pense, une minimum de base en vecteurs et en maths (normal, tangente, magnitude blabla. 

Plutôt que de réinventé la roue, j'ai utilisé un outil gratuit pour gérer le dessin vectoriel [**Bezier Path Creation](https://assetstore.unity.com/packages/tools/utilities/b-zier-path-creator-136082)** qui est simple et parfaitement adapté à mes besoins. 

[https://youtu.be/saAQNRSYU9k](https://youtu.be/saAQNRSYU9k)

Voilà le resultat et c'est tellement satisfaisant de reussir à réaliser exactement ce que j'avais en tête.

![](/assets/postsAssets/2021-12-12-brick-breaker-log-1/PreveiwVector.mp4)

![Drag1.gif](/assets/postsAssets/2021-12-12-brick-breaker-log-1/Drag1.gif)

Maintenenant go la réalisation de niveau. 

Prochain milestone, le son...

Et ensuite les premiers Beta testes.

La bise, Tchouss !

---

Robin Moretti ©️ 2015 - April 27, 2023