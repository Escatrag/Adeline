### Projet d'intelligence artificielle avec reconaissance vocale en Francais
Hey tout le monde, je poste ici un projet amélioré depuis un autre projet de GNU/LINUX Magazine.

Il s'agit d'une IA en python utilisant Tensorflow, avec une reconaissance vocale ainsi qu'une réponse vocale en Francais.

# Comment l'installer ?
Ce programme ne fonctionne qu'avec python3 (idéalement la 3.5)
Pour l'installer, il faut installer les dépendances:
```
sudo apt install python-pyaudio mbrola mbrola-fr1
```
Si vous préferez installer une voix feminine, installez 
```
mbrola-fr4
```
au lieu de mbrola-fr1

Il faut aussi plusieurs dépendances python:
```
sudo pip3 install nltk numpy tensorflow pysttx3 scipy h5py tflearn voxpopuli
```
Ensuite lancer chatbot.py avec 
```
python3 chatbot.py
```

# Comment le configurer ?
La configuration est très simple.
Le fichier rules.json contient toutes les règles à traiter.

Libre à vous de faire vos propres règles en respectant la syntaxe.

Dans le fichier chatbot.py, à la fin, il y a cette ligne:
```
chatbot = Chatbot(verbose=True, talk=True, SpeechRecognition=False)
```
Elle vous sert à définir si vous voulez que le programme affiche les logs (verbose), si vous voulez qu'il parle (talk) et si vous voulez qu'l reconnaisse votre voix.(SpeechRecognition). Pour desactiver une des fonctions mentionnées , il vous suffit de passer de True à False.

La ligne du dessous,
```
chatbot.readRules('rules.json')
```
vous permet de charger votre propre fichier json.

Au premier lancement,le programme va créer des fichiers 'model.tflearn.data-00000-of-00001', 'model.tflearn.index' et 'model.tflearn.index' et 'checkpoint'.
Il va aussi créer un dossier logs et __pycache__.
