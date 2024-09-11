
# La gestion des fichiers en Python

La gestion des fichiers en Python consiste à ouvrir, lire, écrire et manipuler des fichiers (comme les fichiers texte ou binaire) à l'aide de plusieurs fonctions et méthodes intégrées. Python offre une approche simple et efficace pour manipuler les fichiers.

## Principales opérations sur les fichiers

### 1. Ouvrir un fichier
La fonction intégrée `open()` permet d'ouvrir un fichier. Voici les modes couramment utilisés :

- `'x'`: Create | crée un fichier, échoue si le fichier existe déjà.
- `'w'`: write | écrire dans un fichier (écrase le fichier existant).
- `'a'`: append | ajouter à un fichier existant.
- `'r'`: read  | lire un fichier (lecture seule, par défaut).
- `'r+'`:  read and write | lecture et ecriture .

### 2. crée un fichier
crée un fichier, échoue si le fichier existe déjà, vous devez utiliser les modes  `'x'`.

Exemple  créetion :
```python
open('exemple.txt', 'x')
```

### 2. Écrire dans un fichier
Pour écrire ou ajouter du contenu dans un fichier, vous devez utiliser les modes `'w'`, `'a'`.

Exemple d'écriture :
```python
fichier = open('exemple.txt', 'w')
fichier.write("Ceci est un texte exemple.\n")
```

Exemple pour ajouter du contenu :
```python
fichier = open('exemple.txt', 'a')
fichier.write("Nouvelle ligne ajoutée.\n")
```

### 3. Fermer un fichier
Il est essentiel de fermer le fichier après utilisation pour libérer les ressources :
```python
fichier.close()
```

### 4. Lire un fichier
Une fois le fichier ouvert, voici les méthodes pour lire son contenu :
- `read()`: lire tout le fichier.
- `readline()`: lire une seule ligne.
- `readlines()`: lire toutes les lignes dans une liste.

Exemple :
```python
contenu = fichier.read()   # lire tout le fichier
ligne = fichier.readline() # lire une ligne
lignes = fichier.readlines() # lire toutes les lignes
```

### 5. Utiliser un gestionnaire de contexte
Le mot-clé `with` est une méthode élégante et sécurisée pour manipuler les fichiers :
```python
with open('exemple.txt', 'r') as fichier:
    contenu = fichier.read()
```

## Manipulation avancée des fichiers

Python offre des bibliothèques comme `os` et `shutil` pour des opérations plus complexes.

### Supprimer un fichier :
```python
import os
os.remove('fichier.txt')
```

### Renommer un fichier :
```python
os.rename('ancien_nom.txt', 'nouveau_nom.txt')
```

### Copier un fichier :
```python
import shutil
shutil.copy('source.txt', 'destination.txt')
```

## Gestion des répertoires

### Créer un dossier :
```python
import os
os.mkdir('nouveau_dossier')
```

### Supprimer un dossier vide :
```python
os.rmdir('dossier_a_supprimer')
```

### Supprimer un dossier non vide :
```python
import shutil
shutil.rmtree('dossier_non_vide')
```

### Lister le contenu d'un dossier :
```python
contenu = os.listdir('dossier_existant')
```

### Naviguer dans les répertoires :
```python
os.chdir('nouveau_dossier')
repertoire_actuel = os.getcwd()
```

### Créer des répertoires intermédiaires :
```python
os.makedirs('parent/enfant', exist_ok=True)
```

### Copier un dossier :
```python
shutil.copytree('dossier_source', 'dossier_destination')
```

### Déplacer un dossier :
```python
shutil.move('dossier_source', 'nouvel_emplacement/dossier_destination')
```

---

# Installation des bibliothèques

### Installation de `colorama`
```bash
pip install colorama
```

### Installation de la bibliothèque `FileMa`
```bash
pip install FileMa
```

## Utilisation de FileMa

### 1. Création & Suppression de fichiers
```python
FileMa.touch('fichier.txt')  # Crée ou met à jour un fichier
FileMa.rm('fichier.txt')     # Supprime un fichier
```

### 2. Lecture & Écriture de fichiers
```python
FileMa.nano('fichier.txt', 'w', 'Contenu')  # Écrire ou ajouter
FileMa.cat('fichier.txt')                    # Lire le contenu
```

### 3. Opérations sur les fichiers
```python
FileMa.ren('ancien.txt', 'nouveau.txt')      # Renommer
FileMa.mv('source.txt', 'destination.txt')   # Déplacer
FileMa.copy('source.txt', 'dest.txt', 'w')   # Copier
```

### 4. Gestion des répertoires
```python
FileMa.mkdir('dossier')        # Créer un dossier
FileMa.rmdir('dossier')        # Supprimer un dossier
FileMa.mkdirs('parent/enfant') # Créer des répertoires intermédiaires
FileMa.rmdirs('chemin_dossier') # Supprimer des répertoires récursivement
```

### 5. Navigation & Liste des répertoires
```python
FileMa.cd('chemin')              # Changer de répertoire
FileMa.pwd()                     # Afficher le répertoire actuel
FileMa.ls('chemin')              # Lister le contenu
```

### 6. Métadonnées des fichiers
```python
FileMa.istime('nom_fichier')     # Heure d'accès
FileMa.size('nom_fichier')       # Taille du fichier
```

### 7. Informations système
```python
FileMa.get_info()                # Variables d'environnement
FileMa.get_path()                # Chemins des exécutables
```

---

Cet aperçu vous offre une vue d'ensemble sur la gestion des fichiers en Python ainsi que sur l'utilisation de la bibliothèque `FileMa`.
