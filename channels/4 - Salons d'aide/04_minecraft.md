# `#❔︱minecraft`
Le salon `#❔︱minecraft` est un salon vous permettant de poser vos questions par rapport
à Minecraft

### Permissions :
![](https://img.shields.io/badge/Lecture-OUI-green?style=for-the-badge) <br/>
![](https://img.shields.io/badge/Ecriture-OUI-green?style=for-the-badge)

<br/>

# Liste des référents 
| Nom | ID|
|:---|:---|
| RedsTom#4616 | 723471302123323434 |
| enimaloc#5587 | 136200628509605888 |
| Tartur#5891 | 797145312438648832 |
| Benco11#5388 | 439850938283589643 |
| Cleymax#7002 | 239086802651054081 |

# Message(s) Épinglé(s)

## Message 1 (par RedsTom#4616 [723471302123323434])

Tout le monde peut se réserver le droit de vous demander si vous avez appris Java. Si ce n'est pas le cas, les personnes vous répondant ont le droit de vous renvoyer vers un cours sur le java.<br>
<u>• Qu'est ce que ça change d'apprendre Java ?</u><br>
→ En apprenant Java, vous saurez ce que vous faites, et quelles conséquences a telle action sur votre code <br>
→ Vous optimiserez mieux votre code, et donc, vous aurez moins de problèmes <br>
→ Vous saurez lire vos erreurs, et donc faire du débogage vous même

• Où apprendre Java ?<br>
→ Sur YouTube :
- La chaîne YouTube de Graven est une bonne introduction aux différentes notions du langage https://bit.ly/yt-java-graven
- La chaîne YouTube de Koor est un moyen d'en savoir beaucoup d'un coup sur une notion en particulier https://bit.ly/yt-java-koor <br>

→ En textuel :
- Le site JMDouxDoux : http://bit.ly/txt-java-jmdouxdoux
- Le site de Koor : https://bit.ly/txt-java-koor

## Message 2 (par NeutronStars#4611 [190284899016638466])

> Le `static` ouvre trop la classe/l'attribut qui ne devient plus contrôler.

Alors pas du tout. Une variable statique peut tout autant être contrôler tout comme une variable non statique.
Ça n'ouvre certainement pas la classe qui l'utilise non plus. D'ailleurs ça ne veut rien dire.

> Cela nuit à la POO

Certainement pas, il faut savoir faire la part des choses.

> Le `static` devrait être utilisé dans les classes dites `Utils`

Encore une fois non. Cela dépend énormément de la situation dans laquelle tu l'utilises.

> pour contourner le `static` le mieux serait d'utiliser l'injection de dépendance via le constructeur.

Injection de dépendance. Voilà bien un grand mot qui n'a rien avoir avec le static.

>je vous rappelle que le mot clé `this` existe dans le cas ou vous devez link la classe `mère`

Bon d'abord le `this` fait référence à l'instance de l'objet actuel. Et non à sa classe herité. Pour faire référence à celle-ci c'est plutôt le mot clé `super`.

Il va falloir que tu revois ce qu'est un static.

Le static n'est pas mauvais et peut être utilisé dans beaucoup de situations.  Il n'est pas toujours utilisé dans des classes uniquement dites statique ou comme constantes.

Il faut arrêter de répéter ce que des personnes mal informés disent car ils ont entendu dire par telle personne que c'était pas bien.

Le static a des avantages comme des désavantage et cela vaut pour tout y compris la POO.

Plus j'entends parler de se mot clé et plus j'ai l'impression que c'est le corona de Java. Il faut arrêter  vous n'allez pas avancer comme ça.

## Message 3 (par RedsTom#4616 [723471302123323434])

Comment éviter le static

Pour éviter le static dans cette situation :
```groovy
class A {
    public static String salut() {
        return "Salut";
    }
}
class B {
    public void salut() {
        System.out.println(A.salut());
    }
}

// À l'appel
B b = new B();
b.salut();
```

On fait :
```groovy
class A {
    public String salut() {
        return "Salut";
    }
}
class B {
    public void salut(A a) {
        System.out.println(a.salut());
    }
}

// À l'appel
A a = new A();
B b = new B();
b.salut(a);
```

## Message 4 (par enimaloc#5587 [136200628509605888])

Pour ceux qui ont une erreur ressemblant a celle en pièce jointe vous devez:
- Ignorer l'erreur sur le `n`
- Mettre la valeur de `version` sous forme d'une chaîne de caractères

![image](https://cdn.discordapp.com/attachments/763849259732172880/816700718915256341/bug.png)

## Message 5 (par enimaloc#5587 [136200628509605888])

Voici les conventions de Java à respecter pour faciliter la lecture pour vous et les autres:
- Les variables, les fonctions sont en [camelCase](https://wiki.c2.com/?CamelCase)  (ex: `gravenDeveloppement`),
- Les constantes en [UPPER_SNAKE_CASE](https://fr.wikipedia.org/wiki/Snake_case) (ex: `GRAVEN_DEVELOPPEMENT`),
- Les classes en [PascalCase](https://wiki.c2.com/?PascalCase) (ex: `GravenDeveloppement`)
- Les packages en [flat case](https://en.wikipedia.org/wiki/Naming_convention_(programming)) (ex: `gravendeveloppement`)

## Message 6 (par enimaloc#5587 [136200628509605888])

Vous utilisez Eclipse et vous rencontrez ces problèmes :

1)  Unrecognized option: -Xincgc

Pour régler cette erreur, il vous faut aller dans vos Run Configuration

![image](https://cdn.discordapp.com/attachments/763849259732172880/857331903983517697/run_configurations.PNG)

ou : clic droit dans un fichier et

![image](https://cdn.discordapp.com/attachments/763849259732172880/857331961299206174/run_configurations_2.PNG)

Une fois dans Run Configurations, allez dans votre configuration de run (qui a généralement le nom de votre projet, ou sur mcp/forge le nom 'Client') et allez dans Arguments. Dans la partie VM Arguments, retirez l'argument `-Xincgc`
puis cliquez sur Apply puis Close et le tour est joué !
2) Vous utilisez forge et rencontrez ceci :
```
Exception in thread "main" java.lang.ClassCastException: class jdk.internal.loader.ClassLoaders$AppClassLoader cannot be cast to class java.net.URLClassLoader (jdk.internal.loader.ClassLoaders$AppClassLoader and java.net.URLClassLoader are in module java.base of loader 'bootstrap')
at net.minecraftforge.gradle.GradleStartCommon.searchCoremods(Unknown Source)
at net.minecraftforge.gradle.GradleStartCommon.launch(Unknown Source)
at GradleStart.main(Unknown Source)
```

Dans ce cas-là, vous avez une version différente de java 1.8 (et/ou 1.7 iirc). Il vous faudra alors vérifier votre version de java. Allez dans le cmd et renseignez la commande suivante `java -version`.

Si vous obtenez : `'java' n’est pas reconnu en tant que commande interne...` c'est que java n'est pas ou mal installé.
Sinon, vous êtes censé obtenir `java version "laversiondejava"`. Celle-ci doit commencer par 1.8, sinon, vous pouvez réinstaller le jdk 8 sur https://adoptopenjdk.net/?variant=openjdk8&jvmVariant=hotspot

Maintenant que vous avez le jdk 1.8, revenez sur Eclipse, et il vous faudra changer la version du runtime lors de l'exécution de votre programme à java 1.8 -> 3).

3) Comment changer la version d'exécution ?

Vous souhaitez changer la version d'exécution de votre programme.

a) Si vous souhaitez appliquer la nouvelle version à tous les projets<br>
Rendez-vous dans Window > Preferences

![image](https://cdn.discordapp.com/attachments/763849259732172880/857332155449475092/window_preferences.PNG)

Puis Java > Installed JREs et suivez b)

![image](https://cdn.discordapp.com/attachments/763849259732172880/857332233151971368/installated_jres.PNG)

b) Ajouter un jdk

Vous êtes dans la section Installed JREs, cliquez sur Add puis Standard VM et dans JRE Home, renseignez le dossier racine de votre jdk.
Cliquez sur Finish et, si vous souhaitez appliquer le jdk à tous vos projets, sélectionnez votre jdk.
Ensuite, cliquer sur Apply and Close.

c) Si vous souhaitez appliquer la nouvelle version à un projet spécifique
Sélectionnez votre projet, effectuez un clic droit puis cliquer sur Properties. Rendez-vous dans Java Build Path.

Ensuite, sélectionnez "JRE System Library" et cliquer sur le bouton Edit. Cliquez sur Alternate JRE puis Installated JREs et suivez b).

Après cela, cliquez sur le menu déroulant et sélectionnez votre jdk.
Puis cliquer sur Finish et Apply and Close.
---
4) Comment changer la version de compilation ?

Vous souhaitez changer la version de compilation de votre programme.
Sélectionnez votre projet > Properties > Java Compiler.

Cochez "Enable project specific settings" , cliquez sur le menu déroulant et sélectionnez la version de java dans laquelle vous souhaitez compiler votre programme.
Cliquez sur Apply and Close.

5) J'ai l'impression que mes packages ne s'emboîtent pas

J'ai l'impression que mes packages ne s'emboîtent pas (https://discordapp.com/channels/763846236766732368/763849259732172880/857335056914055178). Pour cela, il vous faut changer la vue de flat à hierarchical : https://discordapp.com/channels/763846236766732368/763849259732172880/857335620015095868 

## Message 7 (par NeutronStars#4611 [190284899016638466])

Allez, je vous donne une résolution **2022**, une liste de chose à apprendre pour bien (**mieux**) progresser:

1 - Apprendre à ouvrir son **navigateur**. Ce n'est pas très compliqué ne vous inquiétez pas, il suffit d'ouvrir la même fenêtre qui vous a servi pour installer **Discord**.

2 - Savoir écrire sur la barre de recherche. Il faut savoir que celle-ci ne comprends que des mots clefs et non des phrases à ralonge. Pour bien faire veuillez suivre ce pattern: `Nom du langage: Nature du problème le plus simplifié que possible..`<br>
**Exemple :** *Java: Comment apprendre ?*

3 - Savoir écrire et comprendre un minimum l'Anglais. Il n'est pas nécessaire d'avoir un niveau **B1** non plus, un simple niveau **A2** suffit largement. Il y a aussi des outils magiques en cas de réel problème de compréhension: (Je vous recommande **Deepl** et non **Translate**).

4 - Mélanger le point **2** et **3**. Si jamais vous avez du mal à trouver avec une recherche écrite en **Français** alors (et ce qui est préférable de faire dès le début) tentez de l'écrire en **Anglais**. Le pattern reste le même.<br>
**Exemple :** *Java: How to learn*

5 - En principe à partir d'ici vous avez déjà trouvé **99.99%** de vos soucis. Mais ici, j'ai l'impression que je vais devoir passer au point 6 directement.

6 - Apprendre Java avant de ce lancer sur une quelconque **API**. Il est inutile de développer des plugins **Minecraft** si vous n'avez aucune base. Si vous faites ça alors il y a **100%** de chance que vous viendrez ici pour pleurer comme quoi une **NPE** vous fait faire des cauchemars (PS: *Java: What is an NPE ?*) et **100%** de chance que je vienne vous tapez sur les doigts (Oui ça me fait un plaisir fou). Ma citation: *On apprend pas à écrire sans connaitre son alphabet.*

7 - Ne pas sortir d'excuse pour justifier votre ignorance/incompétence. Genre les:
> `C'est parce que je suis débutant.`<br>
> `C'est parce que ça fait longtemps que j'ai pas fait de Java.`<br>
> `ça fait plusieurs jours que je recherche et que je ne trouve pas.`

Et beaucoup d'autres. Si vous le faites, je vous taperez encore plus sur les doigts avec une plus grande règle. Vous ne pouvez pas me berner avec des excuses aussi minable.

8 - Ne pas dire **Java-Pur / Java Minecraft** ou autre connerie. Que vous utilisez ou pas une librairie tel que **Minecraft** ou non, vous faites du **Java**. Il n'y a aucune distinction sur ce langage. Je pensais que la saga d'**Harry Potter** vous l'avez déjà expliqué avec **Voldemort** et leur histoire de **Sang-pur**. Restez du bon côté de la force s'il vous plait !

9 - Ne pas se fier à ce que l'on connait déjà. Ce n'est parce que une chose **fonctionne** qu'elle est forcement bien faite. Qui vous dis qu'un nouvelle ajout ne ferait pas un effet de bord ? (Ps: *Java: What is a side effect ?*)

10 - Aller voir ce qu'est le **TDD** (Je suis gentil: **Test Driven Development**).

11 - Ne pas sur enchérir le nom de vos classes/méthodes/champs. Il faut donner des noms simples et qui ont du sens. Le nom **Main** pour vos classe est à bannir !

Je pense que je vais pouvoir m'arrêtez ici. Je pourrais vous demander de bien apprendre la **POO**, de ne pas faire de **Getter/Setter** etc... Mais j'irais trop loin pour vous. Si les 11 règles au dessus sont respecter, vous ne viendrez ici que pour des problèmes plus complexe ou mal documenté, voir même pour de la bonne pratique.

Vous pensez que pour **2022** vous y arriverez ? 

## Message 8 (par RedsTom#4616 [723471302123323434])

**Question courante :** J'ai ajouté Spigot 1.18 ou 1.18.1 sous forme de fichier Jar à mes dépendances mais ça ne fonctionne pas, comment faire ?

Depuis la version 1.18, **le jar de Spigot ne contient plus les fichiers nécessaires au développement.**

<u>Mais comment développer ducoup ?</u><br>
Et bien il va falloir savoir se moderniser et commencer à utiliser un buildtool tel que [Gradle](https://gradle.org/). <br>
Il existe quelques tutoriels sur internet sur la mise en place d'un projet **Gradle**.

<u>PS :</u> Le meilleur support de Gradle que j'ai pu trouver sur les IDE java est sur IntelliJ IDEA. Le support sur Eclipse est approximatif, mais cependant fonctionnel pour les projets de base.

Il vous faudra donc utiliser gradle, et avoir le code suivant dans votre fichier de build :
```groovy
repositories {
    mavenCentral()
    mavenLocal()        

     maven { url = 'https://oss.sonatype.org/content/repositories/snapshots' }
     maven { url = 'https://oss.sonatype.org/content/repositories/central' }
    // Éve
```

Si vous avez auparavant build Spigot avec le buildtools, vous pouvez utiliser ceci dans le bloc `dependencies`
```groovy
compileOnly 'org.spigotmc:spigot:1.18-R0.1-SNAPSHOT'
```

Si vous n'avez pas besoin du NMS et/ou que vous n'avez pas build Spigot avec buildtools :
```groovy
compileOnly 'org.spigotmc:spigot-api:1.18-R0.1-SNAPSHOT'
```

⚠️ **PS :** Si vous avez besoin du NMS, vous devrez impérativement build Spigot avec BuildTools et utiliser la première méthode.

[En apprendre plus](https://www.spigotmc.org/wiki/spigot-gradle/).

## Message 9 (par Tartur#5891 [797145312438648832])

<u>On ne fait pas de plugins sans apprendre Java.</u> Sinon, vous reviendrez tout le temps ici juste parce-que vous avez une NPE, des erreurs de syntaxe... et quand bien même votre code fonctionne, ce n'est pas une preuve que votre programme a été bien écrit.

Avant de se lancer dans l'apprentissage de l'API de Spigot, on apprend le Java. Voici un cours recommandé (vidéo ou texte, vous choisissez) : https://koor.fr/Java/Index.wp

En suite, une fois que vous aurez terminé ces cours, vous pourrez **enfin** vous lancer dans vos plugins. Je vous recommande donc de lire la doc de Spigot : https://www.spigotmc.org/wiki/spigot-plugin-development/ (tout est écrit sur comment faire quoi).

Une fois que tout cela sera fait, il ne restera plus qu'à mêler vos connaissances en Java et en Spigot pour créer des plugins incroyables ! Mais ne brûlez pas les étapes, prenez le temps de bien apprendre correctement même si cela doit prendre des mois.

Bon courage ! 

