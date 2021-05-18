# ctm-elections-2021

En dehors des programmes, pour la plupart indisponibles et difficilement comparables, est-il possible, ce qui est différent de souhaitable ou de préférable, de réduire drastiquement la liste des candidats ([16 candidats déclarés au 7 mai 2021](https://www.rci.fm/martinique/infos/Politique/Deja-16-candidats-declares-aux-elections-territoriales-de-juin-2021)).

Ce dépôt fait suite au tweet sur la définition d'un ensemble de [critères objectifs CTM 2021](https://twitter.com/guillem_lefait/status/1390022053588307969).
Ces critères sont forcément subjectifs et peut-être pas les plus pertinents.
Néanmoins, les données collectés sont ouvertes, libre à chacun de les réutiliser et/ou de les compléter.
Ou pas.

## Utilisation

### Tableur
Les fichiers CSV s'importent facilement dans tous les tableurs.

### En ligne
Pour des requêtes en ligne, il est possible d'utiliser [sqliteviz](https://lana-k.github.io/sqliteviz/) en chargeant l'un des fichiers CSV.

Une requête de ce type:

    SELECT candidat, age, avg_age_tete_de_liste, percent_femme_tete_liste, vacciné, position_vaccin
    FROM csv_import 
    WHERE depot_liste IS NULL OR depot_liste != 'non'
    ORDER BY percent_femme_tete_liste DESC, vacciné DESC, position_vaccin, age

permet d'obtenir un tableau, trié en fonction des différents critères.

