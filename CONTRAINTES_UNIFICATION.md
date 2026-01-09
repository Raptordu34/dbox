# Contraintes d'Unification du Projet

Ce document détaille les contraintes logicielles, de présentation et de journalisation identifiées dans les différents modules du projet (hors drivertest).

## Table des Matières

- [1. Contraintes Logicielles](#1-contraintes-logicielles)
- [2. Contraintes d'Unification des README](#2-contraintes-dunification-des-readme)
- [3. Contraintes d'Unification des Logs](#3-contraintes-dunification-des-logs)

---

## 1. Contraintes Logicielles

### 1.1 Versions Java

**Version cible : Java 21** ✅ **TOUS LES MODULES CONFORMES**

| Module | Version Actuelle | Statut |
|--------|------------------|--------|
| mpubusiness | Java 21 | ✅ Conforme |
| mpudriver | Java 21 | ✅ Conforme |
| sensorsbusiness | Java 21 | ✅ Conforme |
| urmbusiness | Java 21 | ✅ Conforme |
| urmdriver | Java 21 | ✅ Conforme |

**Configuration standardisée :**

```xml
<properties>
    <maven.compiler.source>21</maven.compiler.source>
    <maven.compiler.target>21</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
</properties>
```

### 1.2 Versions Maven

**Version Maven minimale requise : 3.8+**

Tous les README spécifient Maven 3.8 ou supérieur comme prérequis.

### 1.3 Plugin Maven Compiler

**Version cible : 3.13.0** ✅ **TOUS LES MODULES CONFORMES**

| Module | Version Actuelle | Statut |
|--------|------------------|--------|
| mpubusiness | 3.13.0 | ✅ Conforme |
| mpudriver | 3.13.0 | ✅ Conforme |
| sensorsbusiness | 3.13.0 | ✅ Conforme |
| urmbusiness | 3.13.0 | ✅ Conforme |
| urmdriver | 3.13.0 | ✅ Conforme |

**Configuration standardisée :**

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.13.0</version>
    <configuration>
        <source>21</source>
        <target>21</target>
    </configuration>
</plugin>
```

### 1.4 Plugin Maven Assembly

**Version cible : 3.7.1** ✅ **TOUS LES MODULES CONFORMES**

| Module | Version Actuelle | Statut |
|--------|------------------|--------|
| mpudriver | 3.7.1 | ✅ Conforme |
| urmdriver | 3.7.1 | ✅ Conforme |

**Configuration standardisée :**

### 1.5 Dépendances de Journalisation

**Configuration standardisée (tous les modules conformes) :**

| Dépendance | Version | Statut |
|------------|---------|--------|
| SLF4J API | 2.0.12 | ✅ Uniforme |
| Log4j2 SLF4J2 Impl | 2.22.1 | ✅ Uniforme |
| Log4j2 Core | 2.22.1 | ✅ Uniforme |

```xml
<!-- Logging: SLF4J API + Log4j2 Implementation -->
<dependency>
    <groupId>org.slf4j</groupId>
    <artifactId>slf4j-api</artifactId>
    <version>2.0.12</version>
</dependency>
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-slf4j2-impl</artifactId>
    <version>2.22.1</version>
</dependency>
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-core</artifactId>
    <version>2.22.1</version>
</dependency>
```

### 1.6 Autres Dépendances Spécifiques

#### Pi4J (Modules Driver)

**Version standardisée : 3.0.3**

- mpudriver : ✅ 3.0.3
- urmdriver : ✅ 3.0.3

```xml
<properties>
    <pi4j.version>3.0.3</pi4j.version>
</properties>
```

#### jSerialComm (urmdriver)

**Version : 2.11.0**

```xml
<dependency>
    <groupId>com.fazecast</groupId>
    <artifactId>jSerialComm</artifactId>
    <version>2.11.0</version>
</dependency>
```

### 1.7 Identifiants Maven

**Convention standardisée :**

```xml
<groupId>fr.ensma.a3.ia</groupId>
<version>1.0-SNAPSHOT</version>
<packaging>jar</packaging>
```

| Module | artifactId | name |
|--------|-----------|------|
| mpubusiness | mpu-business | Raspberry MPU Business |
| mpudriver | mpudriver | Raspberry MPU6050 Driver |
| sensorsbusiness | sensor-aggregator | Raspberry Sensor Aggregator |
| urmbusiness | urm-business | Raspberry URM Business |
| urmdriver | urm37-driver | Raspberry URM37 Driver |

---

## 2. Contraintes d'Unification des README

### 2.1 Structure Générale Standardisée

Tous les README suivent une structure cohérente :

```markdown
# [Titre du Module avec Emojis]

[Description concise du module]

## ✨ Fonctionnalités
[Liste à puces avec emojis décrivant les fonctionnalités]

## 🛠️ Prérequis

### Matériel (si applicable - drivers uniquement)
[Liste du matériel requis]

#### 🔌 Schéma de Câblage (drivers uniquement)
[Image SVG et tableau de connexions]

### Logiciel
[Versions Java, Maven, configurations système]

### Dépendances (modules business uniquement)
[Modules dépendants à installer]

## 🚀 Installation et Compilation

[!IMPORTANT] Bloc avec ordre de compilation

[Commandes Maven]

## 📦 Intégration dans votre projet

[Bloc XML de dépendance Maven]

## 💻 Exemple d'Utilisation

[Code Java complet et commenté]

## 📂 Structure du Projet

[Liste des fichiers principaux]
```

### 2.2 Emojis Standards Utilisés

| Section | Emoji | Usage |
|---------|-------|-------|
| Fonctionnalités | ✨ | Titre de section |
| Prérequis | 🛠️ | Titre de section |
| Installation | 🚀 | Titre de section |
| Intégration | 📦 | Titre de section |
| Exemple | 💻 | Titre de section |
| Structure | 📂 | Titre de section |
| Câblage | 🔌 | Sous-section |
| Items fonctionnels | 🚀⚙️📊🌡️🧱📦🛡️📝🔗⚡ | Liste à puces |

### 2.3 Blocs IMPORTANT

**Convention standardisée :**

```markdown
> [!IMPORTANT]
> **TITRE EN MAJUSCULES :** Description du point important.
>
> ```bash
> # Commandes si applicable
> ```
```

**Usages identifiés :**
- Ordre de compilation des dépendances
- Prérequis indispensables
- Avertissements matériels (tension, etc.)

### 2.4 Sections Spécifiques aux Modules Driver

Les modules `mpudriver` et `urmdriver` incluent :

1. **Section Matériel** avec :
   - Liste du matériel requis
   - Schéma de câblage SVG
   - Tableau de connexions
   - Avertissements de sécurité (tensions, etc.)

2. **Configuration Système** :
   - Activation I2C/UART via `raspi-config`
   - Permissions utilisateur (`dialout` pour UART)

### 2.5 Sections Spécifiques aux Modules Business

Les modules business (`mpubusiness`, `urmbusiness`, `sensorsbusiness`) incluent :

1. **Section Dépendances** listant les modules driver requis
2. **Bloc IMPORTANT** détaillant l'ordre de compilation
3. **Exemples utilisant les patterns Singleton** (mpubusiness, urmbusiness)

### 2.6 Format des Exemples de Code

**Conventions standardisées :**

- Utilisation de `try-with-resources` pour la gestion des ressources
- Imports explicites en début d'exemple
- Commentaires numérotés expliquant les étapes clés
- Boucle de test avec nombre d'itérations défini
- Gestion des exceptions avec `printStackTrace()`
- Affichage console avec `System.out.printf()` pour le formatage

### 2.7 Recommandations d'Uniformisation

Pour maintenir la cohérence :

1. **Toujours inclure** :
   - Emoji dans le titre principal
   - Section Fonctionnalités avec emojis
   - Bloc IMPORTANT pour les prérequis critiques
   - Code Java complet et exécutable dans les exemples

2. **Respecter l'ordre des sections** tel que défini en 2.1

3. **Utiliser le même style** :
   - Voix active et concise
   - Formatage Markdown GitHub-flavored
   - Tableaux pour les connexions matérielles
   - Blocs de code avec spécification du langage

---

## 3. Contraintes d'Unification des Logs

### 3.1 Framework de Journalisation

**Standard adopté : SLF4J + Log4j2**

Tous les modules utilisent :
- **API de façade** : SLF4J 2.0.12
- **Implémentation** : Apache Log4j2 2.22.1

**Fichier de configuration** : `src/main/resources/log4j2.xml`

### 3.2 Configuration Log4j2 Standardisée

**Tous les modules utilisent strictement la même configuration** (vérifiée identique sur les 5 modules).

#### 3.2.1 Appenders

**1. Console Appender**
```xml
<Console name="Console" target="SYSTEM_OUT">
    <PatternLayout pattern="%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/>
</Console>
```

**Format** : `HH:mm:ss.SSS [thread] LEVEL logger - message`

**2. RollingFile Appender**
```xml
<RollingFile name="RollingFile" fileName="logs/app.log"
             filePattern="logs/$${date:yyyy-MM}/app-%d{MM-dd-yyyy}-%i.log.gz">
    <PatternLayout>
        <Pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n</Pattern>
    </PatternLayout>
    <Policies>
        <TimeBasedTriggeringPolicy />
        <SizeBasedTriggeringPolicy size="10 MB"/>
    </Policies>
    <DefaultRolloverStrategy max="10"/>
</RollingFile>
```

**Format** : `yyyy-MM-dd HH:mm:ss.SSS [thread] LEVEL logger - message`

#### 3.2.2 Politiques de Rotation

| Paramètre | Valeur | Description |
|-----------|--------|-------------|
| Fichier principal | `logs/app.log` | Fichier actif |
| Pattern archivage | `logs/yyyy-MM/app-MM-dd-yyyy-i.log.gz` | Organisation mensuelle |
| Taille maximale | 10 MB | Rotation par taille |
| Fichiers conservés | 10 | Stratégie de rétention |
| Compression | GZ | Format de compression |
| Rotation temporelle | Quotidienne | TimeBasedTriggeringPolicy |

#### 3.2.3 Root Logger

```xml
<Root level="info">
    <AppenderRef ref="Console"/>
    <AppenderRef ref="RollingFile"/>
</Root>
```

**Niveau de log** : `INFO` (standard pour tous les modules)

**Sorties** : Console + Fichier (logs dupliqués)

### 3.3 Utilisation dans le Code Java

**Pattern standardisé dans tous les modules :**

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class MaClasse {
    private static final Logger logger = LoggerFactory.getLogger(MaClasse.class);

    public void maMethode() {
        logger.info("Message informatif");
        logger.warn("Avertissement");
        logger.error("Erreur", exception);
    }
}
```

### 3.4 Niveaux de Log Recommandés

| Niveau | Usage Observé |
|--------|---------------|
| TRACE | Non utilisé (niveau root = INFO) |
| DEBUG | Disponible mais non visible par défaut |
| **INFO** | **Niveau par défaut** - Opérations normales |
| WARN | Situations anormales non critiques |
| ERROR | Erreurs et exceptions |

### 3.5 Structure des Répertoires de Logs

```
[module-root]/
└── logs/
    ├── app.log                    # Fichier actif
    └── YYYY-MM/                   # Archives mensuelles
        ├── app-MM-dd-YYYY-1.log.gz
        ├── app-MM-dd-YYYY-2.log.gz
        └── ...
```

**Note** : Le répertoire `logs/` est créé automatiquement au premier démarrage.

### 3.6 Recommandation : Gitignore

Pour éviter de commiter les logs, ajouter à `.gitignore` :

```
# Logs
logs/
*.log
*.log.gz
```

### 3.7 Conformité Actuelle

**Statut** : ✅ **100% Conforme**

Tous les modules (mpubusiness, mpudriver, sensorsbusiness, urmbusiness, urmdriver) utilisent :
- La même configuration `log4j2.xml` (identique à l'octet près)
- Les mêmes versions de dépendances (SLF4J 2.0.12, Log4j2 2.22.1)
- Le même pattern de log dans le code


**Document généré le** : 2026-01-07
**Dernière mise à jour** : 2026-01-07
**Modules analysés** : mpubusiness, mpudriver, sensorsbusiness, urmbusiness, urmdriver
**Exclusions** : drivertest (comme demandé)
