# Algorithme DAB

Conception d'un algorithme DAB<sup>1</sup>, sous forme de pseudo-code.

*<sup>1</sup> Distributeur Automatique de Billets*

---

```text
Le client insère sa carte dans le distributeur
Le processus de vérification de la carte est lancé
    SI la carte n'est pas conforme
        ALORS le distributeur rejette la carte
        Le programme s'arrête
    SINON SI la carte est bloquée
        ALORS le distributeur avale la carte
        Le programme s'arrête
    SINON // Est ce qu'on pourrai pas l'enlevé ? //
        la carte est valide
        Lancer la demande du code de la carte
Le distributeur affiche un message "demande le code de la carte"
Le client tape un code
    SI le code est incorrect
        ALORS le distributeur affiche un message "code incorrect"
        ET le compteur de tentative est incrémenté de 1
        SI le compteur de tentative est égale a 3
            ALORS le distributeur avale la carte
            Le programme s'arrête
        Lancer la demande du code de la carte
    SINON
        Le code est correct
        Lancer la demande du montant à retirer
        client.Choisir un montant
        Le processus de vérification du soldeClient est lancé
        SI le soldeClient est non-valide
            ALORS le distributeur affiche un message informant de la non-validité du soldeClient
            client.Choisir un montant
        SINON SI le soldeClient est valide
            ALORS le processus vérification du soldeDab est lancé
            SI le DAB n'a pas les fonds
                ALORS le distributeur affiche le message de limitation de retrait
            SINON 
                client.Récuperé l'argent
                client.Récuperé la carte
                le programme s'arrête
```

*note pour moi-même: **peut être manque-il des "Tant que"***