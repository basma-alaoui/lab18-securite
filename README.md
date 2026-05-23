# LAB 18 : FireStorm – Résolution détaillée étape par étape

**Cours : Sécurité des applications mobiles**  
**Niveau : Medium**  
**Techniques : Reverse Android (Jadx), Hooking Java (Frida), Authentification Firebase**

---

## 1. Objectif du challenge

L’application Android `FireStorm` contient une fonction `Password()` qui génère un mot de passe utilisé pour se connecter à une base de données Firebase.  
**Cette fonction n’est jamais appelée** dans le flux normal de l’application.  
L’objectif est de :

1. Forcer l’exécution de `Password()` avec **Frida** pour obtenir le mot de passe.
2. Utiliser ce mot de passe pour s’authentifier sur Firebase.
3. Récupérer le `flag` stocké dans la base de données.

![Objectif](Capture%20d'écran%202026-05-23%20110929.png)

---

## 2. Étape 1 : Préparation de l’environnement

Outils nécessaires :

- **Jadx** – décompilation de l’APK
- **Frida** – instrumentation dynamique
- **Python 3** avec `pyrebase` ou `firebase-admin`
- **ADB** (Android Debug Bridge) – pour lancer l’application sur un émulateur ou un vrai appareil

Vérifier que l’appareil (ou émulateur) est détecté :
```bash
adb devices



```bash
adb devices
