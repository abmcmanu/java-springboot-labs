# Lab 00 — Installation & Setup de votre environnement (JDK, IntelliJ)

Bienvenue dans le *premier lab* de votre parcours ! 🎉

Ce lab a pour objectif de vous accompagner pas à pas dans l’installation complète de votre environnement de développement. 
Vous n'avez **aucune connaissance préalable** ? Parfait. Tout est expliqué simplement.

---

# 🎯 Objectifs du Lab

À la fin de ce lab, vous saurez :

- Installer Java (JDK) sur votre ordinateur.
- Installer IntelliJ IDEA, un logiciel pour écrire du code (IDE).
- Vérifier les installations.

Ces outils seront utilisés dans **tous les labs suivants**.

---

# 💡 Avant de continuer : quelques remarques importantes

## 🖥️ 1. Capacité recommandée de votre ordinateur

Pour suivre ce parcours confortablement, voici les recommandations minimales :

- **RAM : 8 Go (minimum recommandé)**  
  → 16 Go si possible, car IntelliJ et Java peuvent consommer beaucoup de mémoire.
- **Espace disque :** 5 à 10 Go pour les outils + vos projets.
- **Processeur :** Dual-Core ou mieux (Intel i5/AMD équivalent recommandé).
- **Système d’exploitation :**
    - Windows 10 ou 11
    - macOS (Intel ou Apple Silicon)
    - Linux (Ubuntu conseillé)

> Pas besoin d’un ordinateur de gamer : une machine de bureau standard suffit largement.

---

## 🧰 2. Les différentes versions d'IntelliJ IDEA

Lorsque vous téléchargez IntelliJ, vous verrez **deux versions** :

### ✔ IntelliJ IDEA Community (GRATUIT)
- Parfait pour apprendre Java et Spring Boot
- Léger, complet, idéal pour les débutants
- 100% suffisant pour notre parcours

### 💼 IntelliJ IDEA Ultimate (PAYANT)
- Axé sur le monde professionnel
- Fonctionnalités avancées : API REST, bases de données, plugins avancés
- Utile lorsque vous travaillerez en entreprise

👉 **Pour ce parcours : nous utiliserons UNIQUEMENT la version Community.**  
Elle suffit parfaitement pour coder, apprendre et progresser vers un niveau junior.

---

## 🆚 3. IntelliJ IDEA ou Visual Studio Code : lequel choisir ?

Les deux sont bons, mais pas pour les mêmes raisons :

### 🧠 Pourquoi nous privilégions IntelliJ IDEA ?
- Meilleure intégration native avec **Java, Maven, Spring Boot**
- Suggestions de code plus intelligentes
- Outil le plus utilisé dans les entreprises Java
- Gestion automatique des projets Java

**C'est l'outil idéal pour un débutant en Java.**

### 🟦 Et Visual Studio Code ?
VS Code est excellent, mais nécessite :
- Beaucoup d’extensions
- Une configuration manuelle
- Moins adapté à un débutant Java

👉 Vous pouvez l’utiliser *si vous le maîtrisez déjà*, mais **IntelliJ reste le choix pédagogique le plus simple**.

---

## ✏️ 4. Il existe aussi d’autres éditeurs…
Les éditeurs suivants *peuvent* être utilisés, mais ne sont pas recommandés pour un débutant :

- **Eclipse IDE** (ancien, moins ergonomique)
- **NetBeans** (peu utilisé aujourd’hui)
- **Vim / Neovim** (réservé aux utilisateurs avancés)
- **Notepad++** (pas adapté pour un vrai projet Java)

👉 Pour apprendre efficacement, **restez sur IntelliJ Community**.

# 🧩 1. Installer Java (JDK 17+)

Pour pouvoir programmer en Java, il faut installer le **JDK – Java Development Kit**.  
Le JDK contient tout ce dont Java a besoin : le compilateur, le moteur d'exécution et les outils de base.

> 📌 **Important à savoir :**  
> La version du *JDK* installée correspond à la version de *Java* que vous souhaitez utiliserer.  
> Aujourd’hui, plusieurs versions existent (Java 8, 11, 17, 21…).  
> Certaines très anciennes applications utilisent encore Java 8,11 → on appelle cela des **applications legacy**.  
> **Dans ce parcours, nous travaillons avec Java 17**, une version stable et très utilisée.

---

# 📥 Télécharger le JDK selon votre système

Selon que vous êtes sur **Windows**, **macOS** ou **Linux**, la méthode change un peu.

---

# 🪟 Installation sur Windows

### ✔ 1. Télécharger le JDK Oracle

1. Rendez-vous sur le site oracle : **[Ici](https://www.oracle.com/java/technologies/javase-downloads.html)**
2. Descendez dans la page et cherchez **Java SE 17**.
3. Choisissez l’installeur correspondant à votre système :
    - `Windows x64` si votre Windows est en 64-bit
    - `Windows x86` si votre système est 32-bit
4. Si vous ne savez pas :  
   Allez dans : **Paramètres → Système → Informations → Type du système**

### ✔ 2. Installer le JDK

Lancez le fichier téléchargé → cliquez sur *Next* → laissez les paramètres par défaut.

### ✔ 3. (Parfois nécessaire) Configurer les variables d’environnement

> ⚠️ Beaucoup de débutants oublient cette étape.  
> Sans elle, la commande `java` ne fonctionne pas dans le terminal.

### ➤ Ajouter JAVA_HOME

1. Clic droit sur **Ce PC** → **Propriétés**
2. **Paramètres système avancés**
3. **Variables d’environnement**
4. Dans *Variables système* → **Nouveau…**

- **Nom :** `JAVA_HOME`
- **Valeur :** `C:\Program Files\Java\jdk-17`  
  *(le dossier exact dépend de votre installation et le nom du dossier)*

- ![Step2LocatingJDKFile](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/Step2LocatingJDKFile.png)

Pour notre cas en image la version de java est 18.

> ⚠️ Il faut savoir que la version de Java que vous utilisez détermine les fonctionnalités disponibles.
Si vous souhaitez utiliser celles de Java 17, vous pouvez travailler avec une version supérieure ou égale à 17, mais ce n’est pas conseillé.
Idéalement, utilisez exactement la version 17.
Nous verrons cela lors de la configuration de notre IDE.

![Step2ConfiguringEnvironmentVariables](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/Step2ConfiguringEnvironmentVariables.png)
![Step2SettingJAVAHOMEEnvironmentVariable](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/Step2SettingJAVAHOMEEnvironmentVariable.png)

### ➤ Modifier la variable Path

1. Dans *Variables système*, sélectionner **Path**
2. Cliquer sur **Modifier**
3. Ajouter à la fin : ;%JAVA_HOME%\bin

![Step2SettingEnvironmentVariable](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/Step2SettingEnvironmentVariable.png)

> 📝 Le `;` est essentiel : c’est un séparateur Windows.

### ✔ 4. Vérifier l’installation

Ouvrez **CMD** et tapez :
`java -version` et de suite `javac -verion`

Si vous voyez une version Java 17 ( openjdk 17 )  → tout est correct 🎉

![Step3CheckingJDKVersion](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/Step3CheckingJDKVersion.png)


> **Remarque :**  
Si vous êtes sur un autre système (Mac ou Ubuntu), n'hésitez pas à me contacter pour que j'ajoute le parcours d'installation correspondant.

# 🎉 Votre système est prêt !

Une fois l’installation terminée et `java -version` fonctionne correctement, vous pouvez passer à la suite du lab.

---

# 🧩 2. Installer IntelliJ IDEA (Community Edition)

Pour écrire et exécuter vos programmes Java, nous allons utiliser **IntelliJ IDEA Community Edition**, un environnement de développement gratuit, moderne et très utilisé par les développeurs Java.

---

## 📥 Télécharger IntelliJ (Windows)

1. Rendez-vous sur : **[jetbrains ici](https://www.jetbrains.com/idea/download)**
2. Scroller jusqu'à la version community dans la section Windows, cliquez sur **Download – Community Edition (gratuit)**.

![intellij-idea-website-windows-tab](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/intellij-idea-website-windows-tab.jpg)

3. Le fichier d’installation (`.exe`) va se télécharger.

![intellij-idea-website-2-community-edition-download](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/intellij-idea-website-2-community-edition-download.jpg)

![intellij-idea-download-started](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/intellij-idea-download-started.jpg)

---

## 💿 Installer IntelliJ (Windows)

Une fois le fichier téléchargé :

1. Double-cliquez dessus.
2. Cliquez sur **Next**.
3. **Laissez absolument toutes les options par défaut**.  
   👉 Pour un débutant, la configuration standard est la plus simple et la plus sûre.
4. Vous pouvez éventuellement cocher :
    - **Add "Open Folder as Project"** (optionnel mais pratique)
5. Continuez avec **Install**.
6. Redémarrez votre ordinateur si on vous le demande.

> 💡 *Pourquoi laisser tout par défaut ?*  
> Parce que les réglages avancés sont destinés aux développeurs expérimentés.  
> La configuration proposée par IntelliJ est optimisée pour débuter sans erreurs.

---

## 🚀 Premier lancement

Lors du premier démarrage :

1. Acceptez les termes d’utilisation.
2. Choisissez un thème (clair ou sombre, comme vous préférez).
3. IntelliJ peut télécharger des composants supplémentaires → laissez-le faire.

Vous arrivez ensuite sur l’écran d’accueil.

![FirstStart](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/FirstStart.webp)

---

# 🛠 Créer votre premier projet Java

### 1️⃣ Cliquer sur **New Project**

Une fenêtre apparaît pour choisir la configuration du projet.

![NewProject](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/NewProject.webp)

### 2️⃣ Vérifier le JDK (Java 17)

IntelliJ essaie automatiquement de détecter le JDK installé sur votre machine.

- 👉 **Si tout est bien installé**, vous verrez automatiquement :  
  **JDK 17 (C:\Program Files\Java\jdk-17...)**

- ❗ **Si IntelliJ ne détecte rien**, alors :
    1. Cliquez sur **Add JDK**
    2. Naviguez vers :  
       `C:\Program Files\Java\jdk-17`
    3. Validez

> ✔ Une fois ajouté une première fois, IntelliJ retiendra ce chemin pour vos futurs projets.

### 3️⃣ Laisser les autres options par défaut
Puis cliquez sur **Create**.

---

# 🧪 Test : créer votre première classe Java

Quand le projet s’ouvre :

1. Dans l’arborescence à gauche, faites clic droit sur le dossier `src`
2. Choisissez : **New → Java Class**

![YourFirstJavaClass](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/YourFirstJavaClass.webp)

3. Donnez un nom, par exemple : **Main** (La première lettre toujours en majuscule)

![YourFirstJavaClass2](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/YourFirstJavaClass2.webp)

Collez ce petit code :

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Bonjour Java !");
    }
}
```

S'il existe un code lors de la creation du fichier, je supprime et remplace par le code plus haut 

▶ Exécuter le programme
En haut à droite, cliquez sur le bouton Run (icône verte ▶). puis sur Run `Main.main()`
![FirstClassJava](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/FirstClassJava.png)

![JeClickPourLancer](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/JeClickPourLancer.png)

Si tout fonctionne, la console affiche : Bonjour Java !

![AffichageConsole](https://raw.githubusercontent.com/abmcmanu/java-springboot-labs/main/assets/niveau0/AffichageConsole.png)


🎉 Félicitations !  
Vous avez maintenant installé **Java (JDK 17)** et l’IDE **IntelliJ IDEA Community Edition**, les deux outils essentiels pour commencer votre parcours et avancer sereinement dans les prochains labs.