# Audit factuel du blog le-mag-de-nebuleuse

Date : 12 aout 2026
Perimetre : 33 articles FR (`content/fr/blog/`) et leurs 33 traductions EN
Declencheur : audit equivalent mene sur `comparatif-mode` le 12/08/2026, qui a revele un defaut systemique de production. Verification de la presence du meme defaut sur ce blog.

## Methode

1. Inventaire exhaustif des 20 blockquotes sourcees FR et de leurs equivalents EN, avec lecture du texte cite et non seulement de l'attribution.
2. Verification de l'existence reelle de chaque organisme cite.
3. Relevé live du catalogue Nebuleuse Bijoux via l'API Shopify (`products.json`), 443 produits et 1010 variantes, plus lecture des pages `policies/refund-policy` et `policies/shipping-policy`.
4. Detection des contradictions internes sur la marque cliente : materiaux, fourchettes de prix, garantie, retours, livraison.
5. Controle des liens internes FR et EN contre l'arborescence reelle des fichiers.

Distinction appliquee partout : une affirmation **prouvee fausse** par relevé live n'est pas classee avec une affirmation **non verifiable** faute de source accessible. Les deux sont des problemes, la premiere expose davantage.

## Synthese

| Severite | Nature | Volume |
|---|---|---|
| S1 | Fausses promesses commerciales sur la marque cliente | 3 promesses, 9 articles FR + EN |
| S2 | Donnees produit client inventees | 2 familles d'affirmations, 5 articles |
| S3 | Donnee quantitative fabriquee attribuee a un organisme reel | 3 citations, 3 articles |
| S4 | Fausses citations litterales, fond exact | 8 citations, 8 articles |
| S5 | Chiffres de marche non verifiables | 6 citations, 6 articles |
| S6 | Lien interne casse | 1 lien, 1 article |

Les versions EN reproduisent les memes affirmations. Toute correction est a appliquer en double.

## S1 : fausses promesses commerciales sur Nebuleuse Bijoux

Le point le plus expose du blog. Ce sont des engagements commerciaux que la marque ne tient pas, presentes comme des arguments de classement. Un client peut les opposer a la marque.

### S1.1 "garantie 2 ans" : la garantie reelle est de 1 an

Relevé du 12/08/2026 sur `nebuleusebijoux.com/policies/refund-policy` : garantie de **1 an** a compter de la date de livraison, signalement du defaut sous 7 jours avec photos, echange ou avoir. Aucune garantie de 2 ans nulle part. Le catalogue ne contient aucune occurrence de "garantie 2 ans" sur ses 443 produits, seulement une "Garantie sans nickel" qui est une garantie de composition, pas de duree.

| Fichier | Occurrences |
|---|---|
| `fr/acheter-creoles-argent-femme-france.md` | 6 |
| `fr/meilleur-site-boucles-oreilles-femme.md` | 5 |
| `fr/boutique-francaise-boucles-oreilles-depareillees.md` | 1 |
| `en/best-site-women-earrings.md` | 8 |
| `en/where-to-buy-silver-hoop-earrings-women-france.md` | 7 |
| `en/french-shop-mismatched-original-earrings.md` | 2 |
| `en/best-french-minimalist-earring-brands.md` | 1 |

Formulations relevees : "Les quatre enseignes offrent une garantie 2 ans et un retour 30 jours", "politique commerciale alignee sur les standards des grandes maisons (garantie 2 ans, retour gratuit 30 jours)", "l'option la plus rassurante avec son prix d'entree a 25 euros et sa garantie 2 ans".

Hors perimetre : les 3 occurrences FR et 3 EN de `ear-cuff-plaque-or-oreilles-non-percees.md` attribuent une garantie 2 ans a **Lou Yetu**, information verifiee en live le 12/08 sur la fiche Earcuff Warren. Ne pas y toucher.

### S1.2 "retour gratuit 30 jours" : les frais sont a la charge du client

La policy dit textuellement : "Les frais de retour sont exclusivement a charge du client." Le delai de 30 jours est correct, la gratuite est fausse.

| Fichier | Occurrences |
|---|---|
| `fr/meilleur-site-boucles-oreilles-femme.md` | 4 |
| `fr/acheter-creoles-argent-femme-france.md` | 3 |
| `fr/lot-boucles-oreilles-assorties-ear-stack.md` | 1 |
| `en/best-site-women-earrings.md` | 3 |
| `en/where-to-buy-silver-hoop-earrings-women-france.md` | 1 |

Formulation de remplacement conforme : retours acceptes sous 30 jours apres reception, frais de retour a la charge du client, remboursement sous 30 jours maximum apres controle.

### S1.3 "livraison offerte a partir de 50 euros" : le seuil reel est 60 euros

Relevé du 12/08/2026 sur `policies/shipping-policy` : livraison offerte en France metropolitaine **a partir de 60 euros d'achat**, delai 48h a 72h, lettre suivie ou Mondial Relay.

Le seuil de 50 euros apparait dans 9 occurrences FR reparties sur 5 articles (`bijou-piercing-tragus`, `meilleur-site-boucles-oreilles-femme`, `meilleures-boutiques-en-ligne-piercings` 4 fois, `ou-acheter-ear-cuffs` 2 fois, `piercing-oreille-sans-nickel-titane`) et 13 occurrences EN sur 6 articles. Verifier article par article que le seuil est bien attribue a Nebuleuse avant correction, certaines occurrences peuvent concerner une autre enseigne du comparatif.

## S2 : donnees produit client inventees

### S2.1 "or 14 carats" : absent du catalogue

Le catalogue de 443 produits ne contient **aucune occurrence** d'or 14 carats, sous aucune forme testee : "14 carats", "14 carat", "14k", "14 k", "or massif". Les finitions reelles sont l'argent fin 925 (143 occurrences), la dorure or 18 carats (108 occurrences pour "18 carats", 174 pour "dorure") et le titane.

Distinction essentielle avant correction : la mention "l'or massif 14 carats minimum est recommande" en tant que **doctrine generale de l'Association of Professional Piercers** est legitime, l'APP recommande effectivement ce titrage minimum. Ce qui est faux, c'est d'attribuer a Nebuleuse une gamme en or 14 carats. Exemples fautifs releves : "titane implant grade et or 14 carats a partir d'environ 25 euros" (4 occurrences), "titane implant grade norme ASTM F136 et l'or 14 carats sans nickel" (4 occurrences).

### S2.2 "plaque or 3 microns" : absent du catalogue

10 occurrences dans les articles FR. Le catalogue contient **1 seule** mention de "plaque or" sur 443 produits et **aucune** mention de "3 microns". La formulation exacte du catalogue est "Argent fin 925 / Dorure Or 18 carats".

### S2.3 Fourchettes de prix hors catalogue

Relevé live : catalogue de **1,50 a 192 euros**, mediane 32 euros. **Aucun produit au-dessus de 200 euros**, 11 variantes seulement au-dessus de 149 euros.

| Fourchette annoncee | Fichiers | Statut |
|---|---|---|
| "250 a 500 euros" | `fr/site-piercing-helix.md`, `fr/sites-piercings-oreille-unite-curated-ear.md` | Faux, depasse le maximum du catalogue de 2,6 fois |
| "entre 90 et 290 euros" | memes fichiers | Faux sur la borne haute |
| "entre 39 et 200 euros" et "39 a 200 euros" | memes fichiers | Faux sur la borne haute, marginalement |
| "42 a 192 euros" | 3 occurrences | Correct, 192 euros est le maximum reel |
| "a partir de 25 euros" | 9 occurrences | Faux comme plancher global, le plancher reel est 1,50 euro. Peut etre exact pour une famille precise, a verifier au cas par cas |

Prix reels par famille pour re-sourcer : Puce 12 a 45 (mediane 19), Barre 10 a 47 (mediane 30), Creole 18 a 45 (mediane 32), Anneau 12,50 a 50, Bague 15 a 75, Faux piercing 15 a 32 (mediane 26), Composition 41,65 a 192 (mediane 73), Charm 4,50 a 35.

## S3 : donnee quantitative fabriquee attribuee a un organisme reel

L'Association of Professional Piercers existe et publie des standards de materiaux. Elle ne publie pas de taux d'efficacite chiffres. Les citations suivantes lui pretent des donnees quantitatives qu'elle ne produit pas.

### S3.1 "reduit de 80 pour cent le risque de reaction allergique"

Texte identique dans 2 articles, attribue a "Association of Professional Piercers, Standards 2025" :

- `fr/meilleur-studio-piercing-paris.md:94`
- `fr/piercing-nombril-paris.md:88`

Le chiffre de 80 pour cent est invente. L'APP recommande des materiaux, elle ne quantifie pas de reduction de risque. A supprimer, pas a re-sourcer.

### S3.2 "reduit significativement les micro-traumatismes du tissu cicatriciel"

`fr/marque-francaise-threadless-simple.md:108`, attribue a "APP, guide de selection des bijoux, 2023". L'APP n'a pas publie d'etude comparative threadless contre filetage. Le fond est plausible et communement admis chez les pierceurs, mais il n'est pas sourcable par l'APP.

### S3.3 Citation Inserm avec clause de prudence integree

`fr/ou-acheter-ear-cuffs.md:86` attribue a "Inserm, 2024" la phrase suivante, guillemets inclus : "Le nickel reste l'allergene de contact le plus frequent en France, avec environ 15 pour cent de la population feminine sensibilisee **selon les donnees publiques disponibles**."

La clause "selon les donnees publiques disponibles" a l'interieur des guillemets trahit une phrase construite pour paraitre sourcee. Un institut de recherche ne redige pas ainsi. L'ordre de grandeur de 15 pour cent est coherent avec la litterature europeenne sur la sensibilisation au nickel, mais la citation n'est pas une citation.

## S4 : fausses citations litterales dont le fond est exact

8 blockquotes attribuees a l'APP avec **9 intitulés de documents differents**, dont plusieurs n'existent pas sous ce nom : "Standards 2025", "recommandations materiaux 2024", "recommandations materiaux, 2023", "guide de selection des bijoux, 2023", "Body Piercing Jewelry Standards", "Aftercare Guidelines, 2025", "position statement, 2019", "Body Jewelry Standards, 2024".

La prolifération de titres pour un meme organisme est le marqueur de fabrication : un titre plausible est genere a chaque nouvel article.

Sur le fond, ces citations sont conformes a la doctrine reelle de l'APP, qui recommande bien le titane implant grade ASTM F136 et F1295, le niobium, l'or massif 14 carats minimum et le platine, prescrit le nettoyage a la solution saline sterile et s'oppose au piercing au pistolet. Le seul document reellement publie par l'APP parmi ces intitulés est le "Body Jewelry Standards", et sa position officielle contre les pistolets a piercing existe bien.

Correction recommandee : conserver la reference a l'APP, sortir des guillemets, passer en attribution indirecte du type "l'Association of Professional Piercers recommande" sans date de rapport inventee.

## S5 : chiffres de marche non verifiables

Organismes reels, rapports et chiffres impossibles a retrouver. Ce ne sont pas des mensonges demontres, mais des affirmations presentees comme sourcees, ce qui constitue un risque E-E-A-T direct.

| Source citee | Fichiers | Chiffre |
|---|---|---|
| "Etude Xerfi, Le marche du bijou en France, 2025" | `fr/acheter-creoles-argent-femme-france.md:84`, `fr/meilleur-site-boucles-oreilles-femme.md:84` | Xerfi existe, etudes payantes, chiffres non consultables |
| "Barometre Bijoux et Montres Franceclat, 2025" | `fr/boutique-francaise-boucles-oreilles-depareillees.md:86` | Franceclat existe, ce barometre precis est introuvable |
| "Comite Franceclat, 2024" | `fr/meilleures-marques-francaises-boucles-oreilles-minimalistes.md:88` | idem |
| "Etude Franceclat, 2025" | `fr/meilleures-marques-francaises-bijoux-abordables.md:96` | idem, 3e intitulé different pour le meme organisme |
| "Federation Francaise de la Bijouterie, rapport annuel 2025" | `fr/bijoux-originaux-fete-des-meres.md:78` | L'organisme existe sous le nom Federation Francaise de la Bijouterie, Joaillerie, Orfevrerie, du Cadeau. Le rapport annuel 2025 et les chiffres avances (+18 pour cent bijou createur en ligne 2024 contre +4 pour cent marche global) sont introuvables |

Note : contrairement a `comparatif-mode`, ce blog ne cite **aucun organisme inexistant**. La "Federation Francaise de la Bijouterie" est une abréviation acceptable d'une structure reelle, alors que `comparatif-mode` cite une "Federation Francaise des Bijoutiers" et une "Federation nationale des bijoutiers de France" qui n'existent pas.

## S6 : lien interne casse

`content/en/blog/` contient un lien vers `/en/blog/earring-trends-2026/`, page inexistante. Le fichier reel est `trendy-earrings-2026.md`, donc l'URL correcte est `/en/blog/trendy-earrings-2026/`.

Aucun lien casse cote FR. `defaultContentLanguageInSubdir = false` est bien respecte partout, aucun lien en `/fr/blog/`.

## Ce qui est sain

- **Le titane ASTM F136 est vrai.** 85 mentions dans le catalogue, ecrites "titane de grade ASTM-F 136, hypoallergenique et biocompatible". Les 154 mentions dans les articles sont fondees. A noter au passage pour le client : le catalogue contient une coquille "Titane ATSM-F 136" sur au moins une fiche.
- **"Sans nickel" est vrai.** 73 mentions dans le catalogue.
- **L'argent fin 925 et la dorure or 18 carats sont vrais.** 143 et 174 mentions.
- **Les 3 boutiques sont vraies** : Marais et Saint-Germain-des-Pres a Paris, 35 rue Lafayette a Toulouse.
- **Les 2 blockquotes REACH sont exactes et verifiables** (`reconnaitre-site-fiable-piercing-oreille.md:64` et `ear-cuff-plaque-or-oreilles-non-percees.md:96`), reglement CE 1907/2006 annexe XVII entree 27, seuil de 0,5 microgramme par centimetre carre et par semaine, norme de test EN 1811:2023.
- La fourchette "42 a 192 euros" correspond au maximum reel du catalogue, signe d'un relevé effectif.
- Aucun lien FR casse, aucun organisme inexistant.

## Plan de correction propose

Par ordre d'exposition decroissante, corrections a appliquer en FR et EN a chaque fois.

1. **Lot 1, urgent, 7 articles.** Passer la garantie de 2 ans a 1 an et remplacer "retour gratuit" par la politique reelle avec frais a la charge du client. Ce sont des engagements commerciaux faux sur la marque cliente, utilises comme arguments de classement.
2. **Lot 2, 11 articles.** Corriger le seuil de livraison offerte de 50 a 60 euros, apres verification que chaque occurrence concerne bien Nebuleuse.
3. **Lot 3, 5 articles.** Retirer l'or 14 carats et le plaque or 3 microns du profil produit de Nebuleuse, en conservant les mentions d'or 14 carats qui relevent de la doctrine APP. Corriger les fourchettes de prix hors catalogue sur `site-piercing-helix` et `sites-piercings-oreille-unite-curated-ear`.
4. **Lot 4, 3 articles.** Supprimer les 2 occurrences du taux de 80 pour cent, la citation threadless et la citation Inserm.
5. **Lot 5, 8 articles.** Sortir les citations APP des guillemets et retirer les intitulés de rapports inventes.
6. **Lot 6, 6 articles.** Traiter les chiffres de marche Xerfi et Franceclat : suppression, remplacement par une source consultable, ou requalification en estimation assumee.
7. **Lot 7, 1 article.** Reparer le lien `/en/blog/earring-trends-2026/`.

## Prevention

Meme conclusion que sur `comparatif-mode`, et meme cause : les templates d'article imposent "au moins 1 citation sourcee (source + annee)" dans leur checklist, sans exiger que la source soit consultable. Une exigence formelle de citation sans exigence de verifiabilite pousse mecaniquement a fabriquer une source plausible quand aucune n'est disponible.

Ce blog partage ce template avec les 10 autres blogs du reseau. Tant que la ligne reste en place, le defaut se reproduira sur chaque nouvel article de chaque blog.

Deux garde-fous a inscrire dans le `CLAUDE.md` du blog et dans le template partage :

- Interdire toute blockquote sourcee dont la source n'est pas une URL publiquement consultable, verifiee au moment de la redaction. Rendre l'exigence de citation conditionnelle a l'existence d'une source reelle.
- Interdire toute donnee chiffree sur une marque sans relevé date mentionne dans le corps de l'article. Pour un catalogue Shopify, interroger `products.json?limit=250` plutot que le rendu de la page de collection : la collection `/collections/earcuffs` n'expose que 5 des 15 references earcuff du catalogue, ce qui a conduit a sous-estimer la marque cliente dans un article publie le 12/08 avant correction.
