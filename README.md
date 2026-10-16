# Lab 2 – Prise en main et utilisation de Jenkins (Pipeline CI/CD)

Étudiant : Ferid SAAD
Enseignant : Wahid Hamdi

Ce compte rendu décrit la construction d'un pipeline CI/CD avec Jenkins (Jenkinsfile) pour une application Spring Boot : clone du dépôt, build Maven, construction de l'image Docker et déploiement du conteneur.

- Application de départ : <https://github.com/wahid007/Jenkins-Demo>
- Mon fork de l'application : <LIEN_DE_TON_FORK>

## 1. Environnement

VM Ubuntu Server 26.04 avec Java 21, Maven, Docker, K3s et Jenkins (service sur le port 8080).

> Capture : version des outils et page d'accueil de Jenkins

![Environnement](images/environnement.png)

## 2. Préparation du projet

Fork du dépôt `wahid007/Jenkins-Demo` sur mon compte GitHub. L'application affiche une page HTML sur le port **2222**.

> Capture : le fork sur mon compte GitHub

![Fork](images/fork.png)

## 3. Configuration de Jenkins

### 3.1 Plug-ins

Plug-ins installés (Administrer Jenkins → Plugins) : Kubernetes CLI, Maven Integration, Docker.

![Plugins](images/plugins.png)

### 3.2 Outils : JDK, Maven, Docker

Administrer Jenkins → Configuration globale des outils.

| Outil | Nom de la configuration | Valeur |
|---|---|---|
| JDK | `...` | `JAVA_HOME = ...` |
| Maven | `...` | `...` |
| Docker | `MyDocker` | `...` |

Les noms saisis ici doivent correspondre exactement à ceux utilisés avec `tool` dans le Jenkinsfile.

![Outils](images/outils.png)

### 3.3 Cloud Docker

Administrer Jenkins → Nodes et Clouds → Configure Clouds.

![Cloud Docker](images/cloud-docker.png)

## 4. Création du pipeline

Nouveau Item → nom du pipeline → type **Pipeline**.

- Général : **GitHub project**, avec l'URL de mon fork.
- Définition : **Pipeline script from SCM**, avec l'URL de mon fork et la branche `main`.

![Configuration du pipeline](images/pipeline-config.png)

## 5. Le Jenkinsfile

```groovy
// Coller ici le Jenkinsfile réellement utilisé
```

Rôle de chaque étape :

| Stage | Rôle |
|---|---|
| Clone Repo | Clone le dépôt GitHub |
| Build Project | Compile et empaquette avec Maven |
| Initialize Docker | Relie l'outil Docker configuré à Jenkins |
| Build Docker Image | Construit l'image à partir du Dockerfile |
| Deploy Docker Image | Lance le conteneur sur le port 2222 |

Dockerfile utilisé :

```dockerfile
// Coller ici le Dockerfile réellement utilisé
```

## 6. Exécution du pipeline

Lancer un build depuis le tableau de bord du pipeline.

> Captures : vue des stages, console du build (`Finished: SUCCESS`), application sur `http://IP_VM:2222`

![Stages](images/stages.png)

![Console](images/console.png)

![Application](images/application.png)

## 7. Difficultés rencontrées et solutions

| # | Problème | Cause | Solution |
|---|---|---|---|
| 1 | | | |

## 8. Conclusion

À compléter.