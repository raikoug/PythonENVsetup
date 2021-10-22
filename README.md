# PythonENVsetup
Guida per i corsi su come impostare l'ambiente Python

# Per chi è questa guida
Questa guida è per chi deve ancora installare Python da 0 sul proprio sistema.

# Obiettivi della gudia
* Aveere python installato su sistema
* Ambiente JupyterHub con Lab
* Comprensione di come gestire il funzionamento dell'ambiente

# Installare Python
Scaricare l'ultima versione stabile da: https://www.python.org/
## Installazione
Durante l'installazione mantenere le impostazioni come da screenshot:
* Installare per tutti gli utenti
* Aggiungere Python 3.10 ai PATH

![1](https://user-images.githubusercontent.com/12453509/138486903-01596329-f751-48a2-849a-092d8d463b5c.png)

Cliccare Install Now 

## Verificare il funzionamento
Aprire una console (powershell o CMD) e provare a dare i seguenti comandi:
```
 python --version
 python -m pip --version
```
Il risultato, a seconda della versione, sarà come questo:

![2](https://user-images.githubusercontent.com/12453509/138487650-55865f84-e55d-49b9-864b-ae76af23e25f.png)

Nel caso non funzioni, si deve provare a sloggare e riloggare per far si che i path dell'utente si aggiornino.

# Installare Jupyter
Jupyter è una piattaforma molto comoda per gestire i progetti con annessa documentazione.

Da linea di comando diamo il comando:
```
pip install jupyterhub jupyterlab
```

## Verificare che funzioni
Da linea di comando provare:
```
jupyterhub --version
```
Se il comando non da errori, ha funzionato.

## Configurare HUB per andare con LAB e default folder.  
La cartella di default di jupyuter sarà la cartella utente.  
Normalmente si vuole crearne una nuova come base dei progetti.  
Per comodità l'ho creata nella mia cartella utente come "jupyterhub" e sarà: `C:\Users\Raikoug\jupyterhub\`  
Creare sempre nella propria cartella utente, la cartella: `.jupyterhub` (sì, col punto davanti!)  
Dentro questa apriamo un prompt (SHIFT+CLickDestro --> Apri finestra di comando qua)  
Diamo il comando:  
```jupyterhub --generate-config```
La riposta sarà:  
```Writing default config to: jupyterhub_config.py```

All'ìinterno della cartella ora ci sarà il file `jupyterhub_config.py`.  
Apriamolo con une ditor testuale qualsiasi, ed in fondo al file scriviamo:

```
c.Spawner.cmd=["jupyter-labhub"]
c.Spawner.notebook_dir = 
```

Testiamop il funzionamento sempre dallo stesso terminale aperto in precedenza dentro la cartella `.jupyterhub`
```
jupyterhub
```
