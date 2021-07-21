---
description: Dans ce tutoriel, nous couvrerons la configuration de base pour le Raspberry Pi et Linux
---

# Configurer le Raspberry Pi

## Résumé <a id="h.vrhvb96nxxe9"></a>

1. Télécharger un système d'exploitation \\(OS\\). Pour ce tutoriel, nous allons utiliser le Raspberry Pi OS.
2. Installez Raspberry Pi OS en utilisant Raspberry Pi Imager
3. Flasher le système d'exploitation sur la carte SD
4. Démarrez le Pi et configurez les paramètres
5. Insérez un SSD externe et copiez la carte SD
6. Arrêter et redémarrer à partir du SSD

{% hint style="info" %}
### NE PASSEZ PAS CETTE ÉTAPE
{% endhint %}

### **Première partie:**

### Installation du système d'exploitation Raspberry Pi Debian « buster » <a id="h.lpv6ciisjqp3"></a>

Nous allons maintenant télécharger la dernière version officielle de Raspberry Pi 64 bits Debian OS. C'est la distribution officielle de Linux 64bit OS qui est conçue pour le Raspberry Pi et son processeur ARM64. Cela le rend stable et très facile de commencer avec le Raspberry Pi.

**1. Téléchargez l'image du système d'exploitation Debian Raspberry Pi 64 bits** [**ici**](https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2020-08-24/2020-08-20-raspios-buster-arm64.zip) **et sauvegardez-la dans un endroit accessible pour le moment sur votre ordinateur.**

**2. Ensuite, téléchargez le logiciel Raspberry Pi Imager que nous utiliserons pour installer l’OS sur notre Raspberry Pi. Ce logiciel est situé sur le site** [**Raspberry Pi**](https://www.raspberrypi.org/software/)**. Veuillez télécharger la version correcte pour votre ordinateur.**

![](../../.gitbook/assets/screen-shot-2021-03-12-at-5.36.30-pm.png)

**3. Insérez la carte SD dans votre ordinateur et ouvrez le "Raspberry Pi Imager".**

* **Cliquez sur "CHOOSE OS" puis trouvez le fichier "2020-08-20-raspios-buster-arm64.zip" que vous avez téléchargé à l'étape \(1\) de ce tutoriel et sélectionnez-le.**
* **Ensuite, cliquez sur "CHOISIR SD" et trouvez la carte SD que vous avez insérée dans l'ordinateur**
* **Maintenant, le bouton "WRITE" apparaîtra et vous pouvez cliquer dessus pour commencer à écrire/vérifier le système d'exploitation sur la carte SD.**
* **Enfin, une fois le processus d'écriture et de vérification terminé, vous verrez une fenêtre pop-up indiquant que l'OS a été correctement écrit sur la carte SD, cliquez sur « CONTINUER » et retirez votre carte SD de l'ordinateur.**

{% hint style="info" %}
#### **Si vous avez encore des problèmes en suivant les instructions écrites,** [**ici**](https://www.youtube.com/watch?v=J024soVgEeM) **se trouve une courte vidéo de ce processus.**
{% endhint %}

### Partie 2:

### Configuration du Raspberry Pi

La première chose que nous voulons faire est de faire démarrer le Raspberry Pi et de le configurer pour notre utilisation.

Pour ce faire, nous devrons insérer la carte SD que nous avons flashée plus tôt avec le Raspberry Pi OS dans le bas du Raspberry Pi. Puis nous pouvons insérer notre HDMI, Clavier, Souris et alimentation électrique.

Une fois que le démarrage du Raspberry Pi est terminé et que vous voyez l'écran de bureau Raspberry Pi OS, nous pouvons maintenant commencer à modifier notre configuration et nos paramètres Raspberry Pi.

{% hint style="info" %}
Si c'est la première fois que vous démarrez le Raspberry Pi OS, vous aurez à suivre quelques configurations initiales listées ci-dessous
{% endhint %}

* [ ] Tout d'abord, vous devez changer le nom d'hôte et le mot de passe du Raspberry Pi cela vous assurera que vous n'utilisez pas seulement les informations de base de connexion.
* [ ] Entrer les informations de connexion au Wifi \(**vous** **pouvez** **sauter cela si vous utilisez Ethernet**\)
* Régler le fuseau horaire.
* [ ] Choisir la langue et les paramètres du clavier.
* [ ] Mettre à jour le Raspberry Pi \(sauter ceci si vous désirez mettre à jour via la ligne de commande\)

{% hint style="success" %}
#### Une fois que vous avez terminé ces étapes initiales, Il est temps de procéder pour que le Rasberry Pi démarre à partir de son port USB afin que nous puissions utiliser notre SSD externe.
{% endhint %}

### Partie 3:

### Forcer le démarrage du RPI à partir du port USB

**Il s'agit de la dernière étape de ce tutoriel. Nous allons tout d'abord insérer notre SSD externe dans l'une des fentes USB 3.0 marquées en bleues.**

![](../../.gitbook/assets/pi4.jpeg)

Ouvrez le menu des applications Raspberry Pi, puis cliquez sur l'application **SD Card Copier**.

![](../../.gitbook/assets/screen-shot-2021-03-29-at-9.11.39-pm%20%281%29.png)

Ensuite, nous voulons sélectionner **COPY FROM DEVICE** - **\(mmcblk0\) SD CARD.**

Ensuite, sélectionnez **COPY TO DEVICE - \(sda\) SSD Device.**

Une fois le processus de copie terminé, ouvrez une nouvelle fenêtre de terminal et entrez la commande suivante:

```text
sudo raspi-config
```

Cela vous ramènera aux paramètres de configuration système du Raspberry Pi où vous pourrez accéder aux **Options Avancées.**

![](../../.gitbook/assets/screen-shot-2021-03-29-at-10.13.19-pm.png)

Sélectionnez ensuite **Boot Order.**

![](../../.gitbook/assets/screen-shot-2021-03-29-at-10.13.40-pm%20%281%29.png)

\*\*\*\*

Choisissez ensuite **USB Boot**.

![](../../.gitbook/assets/screen-shot-2021-03-29-at-10.14.05-pm%20%281%29.png)

Vous pouvez maintenant sélectionner **&lt;Ok&gt;** puis **&lt;Finish&gt;**, fermer le menu de configuration du système Raspberry Pi et redémarrer le Pi.

Vous devriez maintenant pouvoir éteindre le Pi après le redémarrage, retirer la carte SD, vous pouvez alors allumer le Raspberry Pi et il devrait démarrer à partir de votre périphérique de stockage USB externe.

{% hint style="success" %}
#### Maintenant que nous avons terminé la majeure partie de la configuration initiale, nous pouvons continuer à préparer le Pi et passer au [tutoriel](tutorial-2-relaynode.md) suivant.
{% endhint %}
