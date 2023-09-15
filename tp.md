# TP OF (Organisme de Formation)

Prépavenir as besoin d'un système de gestion pour les demande d'inscription aux formations du catalogue.

## Le catalogue 

Faire un formulaire pour toute les formations contenant

- Développeur Web et Web Mobile | Niveau BAC
- Concepteur Développeur d'applications | Niveau BAC
- Webdesigner | Tout niveaux
- Réferencement SEO | Tout niveaux



Le programme programme seta utilisé par 2 types de personnes (un admin et un assistant), l'objectif étant de faciliter la gestion du processus d'inscription des futurs élèves.

---

Prise de notes :

optionnel : Convertion du formulaire en PDF, Alarme qui permet d'avertir la date limite pour laquel il faut repondre à la candidature., Utiliser un numero de suivie envoyé au candidat, avoir des categories par formations.

---

## **Scénario:**

```text
Le candidat clic sur un boutton pour avoir acces au formulaire de candidature, il aura une page qui contiendra un formulaire qu'il devra remplir puis envoyer.

Le formulaire contiendra un selecteur pour les differentes formations qui changera le formulaire en fonction de la formation, des disponibilités de la formation (complet, sessions de recrutement.), ses informations personnels, et une case pour upload les fichier (CV, lettre de motivation).

Lorsque le formulaire est envoyé, le candidat recevra un accusé de reception contenant la vérification de ces informations personnels (peut etre dangereux), ainsi qu'un numéro de suivi ( pour voir où en est ca candidature ). Le mail est donc recu par le client (contact@prepavenir.fr) en pdf et traité.

Une fois que le mail est recu, le client doit avoir dans son espace personnel du site les informations renseigné par le candidat ainsi que les documents qu'il a fourni rangé dans la categorie de la formation en question. Une fois que le client a donné et traité la candidature, elle sera archiver et ne sera plus visible dans les candidature. 
Création d'un rôle Administrateur (admin), et d'un rôle Assistant (assis)
SI rôle == admin
    ALORS
        Afficher bouttons Accepter et Refuser
        SI client.Clicker sur accepter
            ALORS envoyer un mail au candidat qui dit qu'il est accepter

        SINON SI client.Clicker sur refuser
            ALORS envoyer un mail au candidat qui dit qu'il est refuser en lui proposant d'autres formations
SINON SI rôle == assis
    ALORS Afficher d'autres fonctionnalités
```

## **Pseudo-Code:**

```text
Le candidat appuie sur le boutton "Candidater"
Le processus formulaire de candidature se lance
SI candidat.Click sur envoyé
    ALORS le processus vérification du formulaire est lancer
    SI le formulaire est conforme
        ALORS le formulaire est converti en pdf
        ET Le formulaire est envoyé par mail avec le pdf en piece jointe
    SINON 
        Un message indiquant que le formulaire n'est pas conforme est affiché dans les cases concernés
Le client recoit la candidature
client.Envoie de l'accusé de reception aux candidats
client.Notification push/mail aux users
TANT QUE candidature =! "traité"
    ALORS 
        client.Envoyé notification de rappel aux users
users.Traiter la demande
client.Notifier le candidat
client.Mettre à jour le suivi
SI candidats == "non-retenus"
    ALORS 
        client.Notifier le candidat
        client.Archiver le dossier
SINON
    client.Notifier le candidat
    client.Ajouter le candidat à la liste
    SI candidats == "inscription rejeté"
        ALORS  
            client.Notifier le candidat
            client.Archiver le dossier
    SINON
        client.Mettre candidats en tant qu'étudiant

```