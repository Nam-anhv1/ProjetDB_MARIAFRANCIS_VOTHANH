# ProjetDB_MARIAFRANCIS_VOTHANH
____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

# le prompt : 

Tu travailles dans le domaine de de la gestion d’agence immobilière.
Ton entreprise a comme activité la gestion de biens immobiliers (locations, ventes, gestion locative, suivi des clients et propriétaires, organisation des visites, gestion des contrats et des paiements).
C’est une agence immobilière comme Orpi, Century 21, Laforêt, Foncia, Guy Hoquet, Stéphane Plaza Immobilier, IAD France, SAFTI, Propriétés Privées, Efficity, Nexity, BSK Immobilier, Dr House Immo, 3G Immo-Consultant, BLG Immobilier, Bouygues Immobilier, MegAgence, Medicis Immobilier Neuf, Marignan, My Appart, Expertimo, Utopia, Acheter du Neuf, Cogedim, Lamotte, Réseau Immo-Diffusion, Morning Croissant, Agence Hamilton.
Les données ont été collectées sur les biens immobiliers, les clients, les propriétaires, les mandats, les visites, les contrats, les paiements, les agents, les documents administratifs.
Inspire-toi des sites web suivants : [lebureaudelimmo.fr], [comparergestion.com], [clubproprio.fr], [immobilier...efigaro.fr]
•	Orpi
•	Century 21
•	Laforêt Immobilier
•	Figaro Immobilier
•	SeLoger
•	Bpifrance Création
•	Manda
•	Comparergestion
•	ClubProprio
•	Appvizer
•	100 Jours pour entreprendre
•	Flatsy
•	Keobiz
•	SC Conseil
•	CreateurAgenceImmobiliere
•	MonExpertDigital
•	ClickUp

Ton entreprise veut appliquer MERISE pour concevoir un système d'information. Tu es chargé de la partie analyse, c’est-à-dire de collecter les besoins auprès de l’entreprise. Elle a fait appel à un étudiant en ingénierie informatique pour réaliser ce projet, tu dois lui fournir les informations nécessaires pour qu’il applique ensuite lui-même les étapes suivantes de conception et développement de la base de données. 
D’abord, établis les règles de gestions des données de ton entreprise, sous la forme d'une liste à puce. Elle doit correspondre aux informations que fournit quelqu’un qui connaît le fonctionnement de l’entreprise, mais pas comment se construit un système d’information.

Ensuite, à partir de ces règles, fournis un dictionnaire de données brutes avec les colonnes suivantes, regroupées dans un tableau : signification de la donnée, type, taille en nombre de caractères ou de chiffres. Il doit y avoir entre 25 et 35 données. Il sert à fournir des informations supplémentaires sur chaque donnée (taille et type) mais sans a priori sur comment les données vont être modélisées ensuite.
Fournis donc les règles de gestion et le dictionnaire de données.

__________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________


# REPONSE DE L'IAG : 



##Règles de gestion
- Chaque bien immobilier est enregistré avec son adresse précise, type (appartement, maison), surface habitable en m², nombre de pièces, étage, et description détaillée pour les annonces.
- Les propriétaires sont identifiés par nom, prénom, date de naissance, téléphone, email, et adresse postale ; un propriétaire peut détenir plusieurs biens.
- Les clients potentiels (acheteurs ou locataires) sont saisis avec nom, prénom, téléphone, email, budget maximum recherché, critères de recherche (ville, surface min, type de bien).
- Un mandat écrit est obligatoire pour chaque bien à vendre ou louer, précisant le type (simple, exclusif, semi-exclusif), durée (généralement 3 mois renouvelable), honoraires en % ou montant fixe, et numéro d'enregistrement chronologique dans le registre des mandats tenu 2 ans. [service-public.gouv](https://www.service-public.gouv.fr/particuliers/vosdroits/F2954)
- Les visites sont organisées par un agent pour un client sur un bien spécifique ; le client signe un bon de visite daté pour preuve, sans valeur de mandat ni honoraires associés. [service-public.gouv](https://www.service-public.gouv.fr/particuliers/vosdroits/F2954)
- Un contrat de location ou de vente est généré après accord, incluant dates de début/fin, loyer ou prix de vente TTC, mode de paiement, diagnostics obligatoires (DPE, électricité, etc.), et signatures des parties.
- Les paiements mensuels de loyers sont attendus le 5 du mois ; retards génèrent relances automatiques par email puis courrier, avec calcul de pénalités de 10% après 10 jours.
- Chaque agent possède une carte professionnelle T ou G, avec nom, prénom, téléphone interne, email, et commissions calculées sur honoraires perçus (part fixe + %).
- Les documents administratifs (mandats, contrats, quittances, diagnostics) sont numérisés et archivés par type, avec date d'émission et statut (actif, expiré, archivé).
- Le suivi locatif inclut les quittances de loyer émises mensuellement, état des lieux d'entrée/sortie avec photos, et déclarations fiscales annuelles aux propriétaires.
- Pour les ventes, un compromis est signé après offre acceptée, suivi d'acte notarié ; honoraires payés à la signature définitive par vendeur ou acquéreur selon mandat. [service-public.gouv](https://www.service-public.gouv.fr/particuliers/vosdroits/F2954)
- Les biens vacants sont listés quotidiennement pour propositions aux clients ; historique des occupations n'est pas conservé au-delà de 5 ans.
- Chaque interaction (appel, email, visite) est tracée avec date, agent concerné, et résumé pour conformité RGPD et transparence. [aumans-avocats](https://aumans-avocats.com/obligations-rgpd-agents-immobiliers/)
- Les commissions agents sont versées mensuellement après encaissement honoraires, avec décompte détaillé par transaction.
- En cas d'indivision, tous les propriétaires doivent signer le mandat et contrats.

##Dictionnaire de données brutes

| Donnée | Signification | Type | Taille |
|--------|---------------|------|--------|
| ID_Bien | Identifiant unique du bien immobilier | Alphanumérique | 10 caractères |
| Adresse_Bien | Rue, numéro, code postal, ville du bien | Alphanumérique | 100 caractères |
| Type_Bien | Appartement, maison, terrain, etc. | Alphabétique | 20 caractères |
| Surface_Habitable | Superficie en mètres carrés | Numérique | 5 chiffres (2 décimales) |
| Nb_Pieces | Nombre de pièces principales | Numérique entier | 2 chiffres |
| Etage | Numéro d'étage ou RDC | Numérique entier | 2 chiffres |
| Description_Bien | Détails descriptifs du bien | Alphanumérique | 500 caractères |
| Prix_Vente | Prix demandé en euros TTC | Numérique | 10 chiffres (2 décimales) |
| Loyer_Mensuel | Montant du loyer mensuel en euros | Numérique | 8 chiffres (2 décimales) |
| ID_Proprietaire | Identifiant unique du propriétaire | Alphanumérique | 10 caractères |
| Nom_Proprietaire | Nom de famille du propriétaire | Alphabétique | 50 caractères |
| Prenom_Proprietaire | Prénom du propriétaire | Alphabétique | 50 caractères |
| Date_Naissance_Prop | Date de naissance du propriétaire | Date | JJ/MM/AAAA |
| Tel_Proprietaire | Numéro de téléphone mobile/fixe | Numérique | 15 chiffres |
| Email_Proprietaire | Adresse email du propriétaire | Alphanumérique | 100 caractères |
| ID_Client | Identifiant unique du client | Alphanumérique | 10 caractères |
| Nom_Client | Nom de famille du client | Alphabétique | 50 caractères |
| Prenom_Client | Prénom du client | Alphabétique | 50 caractères |
| Tel_Client | Numéro de téléphone du client | Numérique | 15 chiffres |
| Email_Client | Adresse email du client | Alphanumérique | 100 caractères |
| Budget_Max_Client | Budget maximum recherché en euros | Numérique | 10 chiffres |
| ID_Mandat | Identifiant unique du mandat | Alphanumérique | 10 caractères |
| Type_Mandat | Simple, exclusif, semi-exclusif | Alphabétique | 15 caractères |
| Date_Debut_Mandat | Date de début du mandat | Date | JJ/MM/AAAA |
| Date_Fin_Mandat | Date de fin du mandat | Date | JJ/MM/AAAA |
| Honoraires_Mandat | Montant ou % des honoraires | Alphanumérique | 20 caractères |
| ID_Visite | Identifiant unique de la visite | Alphanumérique | 10 caractères |
| Date_Visite | Date et heure de la visite | Date/Heure | JJ/MM/AAAA HH:MM |
| ID_Contrat | Identifiant unique du contrat | Alphanumérique | 10 caractères |
| Type_Contrat | Location, vente, compromis | Alphabétique | 15 caractères |
| Date_Signature | Date de signature du contrat | Date | JJ/MM/AAAA |
| ID_Paiement | Identifiant unique du paiement | Alphanumérique | 10 caractères |
| Montant_Paiement | Montant payé en euros | Numérique | 10 chiffres (2 décimales) |
| Date_Paiement | Date d'encaissement | Date | JJ/MM/AAAA |
| ID_Agent | Identifiant unique de l'agent | Alphanumérique | 10 caractères |
| Nom_Agent | Nom de l'agent immobilier | Alphabétique | 50 caractères   |
















