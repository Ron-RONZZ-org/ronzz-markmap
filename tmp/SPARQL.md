# SPARQL

## Theory

- Web 3.0
    - Sémantique
        - documents > connaisance
            - RDF
                - Mona Lisa
                    - peinte à la peinture à l'huile
                    - sur du bois de peuplier
                - requête 
                    - SPARQL
                        - Quel caractère est répresanté par la plus d'acteurs?
                        - Quelles oeuvres d'auteurs sont entrées dans le domaine publique cette année?
- Wikidata
    - Wikipedia en Web 3.0
    - CC 1.0

## Utilisation

### modèle

```SPARQL
# modèle de requête
SELECT ?a ?b ?c
WHERE 
{ 
    x y ?a.
    m n ?b.
    ?b f c?.
}
```
### triplets

- `?a,?b?c` sont les variables ciblé
- `{}` contient des restrictions
    - principlement triplets
        - ![triplet](assets/images/presentations/triplet.svg)
            - ![triplet-example](assets/images/presentations/triplet-examples.svg)
### exemple theoretique

```SPARQL
SELECT ?fruit
WHERE
{
    ?fruit hasColor yellow;
    tastes sour,
    sweet.
}
# La nom de les variables est arbitraire et cosmétique. `?fruit` peut être `?plant`. 
# `;` signifie que une déclaration de la même sujet suivre en ligne suivant, et `,` signifie une déclaration de la même sujet et predicat suivant, et `.` signifie completion de la groupe de déclaration sur la sujet.
```

### identifiant

- pas humain lisible
    - unique pour chaque concept
        - Q élément
            - Q142: France
        - P: propriété
            - P276:location

### exemple pratique

```SPARQL
SELECT ?child
WHERE
{
    ?child wdt:P276 wd:Q142.
}
# wdt: et wd: sont préfixe syntaxtique pour les proprétié et éléments
```

### Montrer les étiquettes

```SPARQL
SELECT ?child ?childLabel
# l'addition de childLabel se demander de récupérer les étiquette des 'child's également 
WHERE
{
    ?child wdt:P276 wd:Q142.
    SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
# `bd:serviceParam` est préfixe pour configuration de wikibase. 
# `[AUTO_LANGUAGE]`: specifié la langue de système d'utilisateur sera detecté automatiquement
# `mul`: specifie résultat dans peu importe quelle langue sont fornir si il y a pas un disponible en [AUTO_LANGUAGE].
# `en`: langue de secours ultime, si [AUTO_LANGUAGE] pas disponible.
```

### Trucs

#### l'Autocomplétion

- `CTRL+SPACE`
    - pour syntaxe
    - pour les identifiants
        - appuyer juste après `wd:` ou `wdt:`

#### indentation

- pas interpreté
- essentiel pour lisibilité

### Exemple plus complexe

#### 

```SPARQL
#e1
SELECT ?country ?countryLabel
WHERE 
{
  ?country wdt:P163 ?flag.
  ?flag wdt:P180 ?element
  ?element wdt:P279 wd:Q729
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
  }
# Cela sélectionne tous les pays dont le drapeau (P163) représente un objet (P180) qui est (P279) un animal (Q729).
```

```SPARQL
#equivalent à e1
SELECT ?country ?countryLabel
WHERE 
{
  ?country wdt:P163 [wdt:P180 [ wdt:P279 wd:Q729]].
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
  }
# Cela sélectionne tous les pays dont le drapeau représente un animal également.
# `[]` est équivalent de 'qui' ou 'lequel' en français.
```

#### Essaie! 

- [WDQS](https://query.wikidata.org/#SELECT%20%3Fcountry%20%3FcountryLabel%20WHERE%20%7B%0A%20%20%3Fcountry%20wdt%3AP163%20_%3Ab22.%0A%20%20_%3Ab22%20wdt%3AP180%20_%3Ab21.%0A%20%20_%3Ab21%20wdt%3AP279%20wd%3AQ729.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cmul%2Cen%22.%20%7D%0A%7D)

    - *Survolez les éléments ou cliquer cliquez sur le bouton info pour voir leur signification.*
    - ![WDQS screen capture](assets/images/presentations/WDQS.png)

### Résumé

| **Langage naturel** | **Exemple** | **SPARQL** | **Exemple** |
|---------------------|------------|------------|------------|
| **Phrase simple** | `Juliet loves Romeo.` | **Point (`.`)** | `juliet loves romeo.` |
| **Conjonction (proposition)** | `Romeo loves Juliet and kills himself.` | **Point-virgule (`;`)** | `romeo loves juliet; kills romeo.` |
| **Conjonction (nom)** | `Romeo kills Tybalt and himself.` | **Virgule (`,`)** | `romeo kills tybalt, romeo.` |
| **Proposition relative** | `Juliet loves someone who kills Tybalt.` | **Crochets (`[]`)** | `juliet loves [ kills tybalt ].` |

### Travaux en cours

- Loin d'être complet
    - e1 a-t-il fonctionné comme prévu ?

### Propriétiés

- un instance de (P31)
- une sous-classe de (P279)

### Syntaxes avancé (pseudo-Regex)

```SPARQL
#equivalent à e1
SELECT ?country ?countryLabel
WHERE 
{
  ?country wdt:P163/wdt:P180/wdt:P279 wd:Q729.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
  }
# Cela sélectionne tous les pays dont le drapeau représente un animal également.
# `/` est équivalent de '[]'.
```

```SPARQL
SELECT ?descendent ?descendentLabel
WHERE
{
    wd:Q22686 wdt:P40+ ?descendent.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
#  Cela sélectionne tous les descendents de Donald Trump, présidente americaine.
```

| **Opérateur** | **Description** | **Exemple SPARQL** |
|-------------|----------------|----------------|
| **`/` (Slash)** | Chemin direct ou intermédiaire | `?person wdt:P25/wdt:P22 ?grandfather.` |
| **`\|` (Pipe)** | Alternative (OU logique) | `?city wdt:P31/(wdt:P279 \| wdt:P131) ?region.` |
| **`*` (Étoile)** | Répétition 0 ou plusieurs fois | `?person wdt:P40* ?ancestor.` |
| **`+` (Plus)** | Répétition 1 ou plusieurs fois | `?person wdt:P40+ ?ancestor.` |
| **`?` (Point d'interrogation)** | Optionnel (0 ou 1 occurrence) | `?person wdt:P26? ?spouse.` |

### Qualifier et value

```SPARQL
SELECT ?painting ?paintingLabel ?material ?materialLabel
WHERE
{
  ?painting wdt:P31/wdt:P279* wd:Q3305213;
            p:P186 [ ps:P186 ?material; pq:P518 wd:Q861259 ].
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
# `ps:` a une valeur
# `pq:` dans __ partie du sujet
# Les requêtes permettent de connaître le matériau de toutes les peintures
```

### `LIMIT` et `ORDER`

####
- `ORDER`
    - `ASC(?something)`
    - `DESC(?something)`
- `LIMIT <number>`

####
```SPARQL
SELECT ?item ?itemLabel ?population WHERE {
  ?item wdt:P31 wd:Q3624078;
        wdt:P1082 ?population
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
ORDER BY ASC(?population)
LIMIT 10
```

### `FILTER`

####
```SPARQL
FILTER ( ?item not in ( wd:Q4115189,wd:Q13406268,wd:Q15397819 ) )
FILTER(YEAR(?dob) = 2015)
FILTER("2015-01-01"^^xsd:dateTime <= ?dob && ?dob < "2016-01-01"^^xsd:dateTime).
# Les opérateurs logique `&& || = > < >= <= !=` sont disponble
```
####
Voir [Guide de Wikidata](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial#Expressions,_FILTER_and_BIND) pour tout les options

####
```SPARQL
SELECT ?human ?label
WHERE
{
  ?human wdt:P31 wd:Q15632617;
         rdfs:label ?label.
  FILTER(LANG(?label) = "en").
  FILTER(STRSTARTS(?label, "Mr. ")).
}
# `rdfs:label retourner les étiquettes attachées à sujet pour la filtre. 
# `LANG()` retouner langue d'une chaîne de texte
#`STRSTARTS(variable, constant)` vérifier la début de la chaîne de texte.
```

####

- évaluations disponible
    - `LANG()`
    - `CONTAINS()`
        - `STRSTARTS()`
        - `STRENDS()`
        - `!REGEX(STR(?string), "^[A-Za-z][-.0-9A-Za-z]{1,}$")`
    - not in
        - `FILTER ( ?item not in ( wd:Q4115189,wd:Q13406268,wd:Q15397819 ) )`
    - not exist
        - `FILTER NOT EXISTS { ?person wdt:P26 ?spouse. }  # No spouse. (P26: is spouse of)`

### `IF`, `BIND`, `BOUND`

####
```SPARQL
IF(condition,thenExpression,elseExpression)
BIND(expression AS ?variable) # Déclarer les variable comme ça en SPARQL
BOUND( ?variable) # Tester si ?variable est déja assigné
```

####
```SPARQL
# Recherche les âges des victimes de la peine de mort.
SELECT ?person ?personLabel ?age
WHERE
{
  ?person wdt:P31 wd:Q5;
          wdt:P569 ?born;
          wdt:P570 ?died;
          wdt:P1196 wd:Q8454.
  BIND(?died - ?born AS ?ageInDays).
  BIND(?ageInDays/365.2425 AS ?ageInYears).
  BIND(FLOOR(?ageInYears) AS ?age).
  # alternatifment, en une seul ligne:
  #BIND(FLOOR((?died - ?born)/365.2425) AS ?age).
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```
    
### Aggregate

#### `GROUP BY`
```SPARQL
SELECT ?country ?countryLabel (MAX(?population) AS ?maxPopulation)
WHERE
{
  ?city wdt:P31/wdt:P279* wd:Q515;
        wdt:P17 ?country;
        wdt:P1082 ?population.
        SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }

}
GROUP BY ?country ?countryLabel # Nous connais les deux sont 1-1 correspondent, mais SPARQL pas. Si nous filtre seulement par ?country, erreur `Bad Aggregate` est produit.
```
####

- `MAX(?variable), MIN(?variable)`  
- `SUM(DINSTINCT ?variable), AVG(DISTINCT ?variable)`: `DISTINCT` est pour éviter les duplicat. 
    - Duplicats sont fréquennement résultat des pseudo-regex
        - plusieur chemins (des arc) entre deux entité
            - Charles Darwin is Emma Wedgwood's romantic partner
            - Charles Darwin is Emma Wedgwood's cousin
            - Gerty Cori is wife of Carl Cori
            - Gerty Cori is colleague of Carl Cori  
- `COUNT(DISTINCT ?vaiable)`: compter combien. 
- `SAMPLE`: retourner un élément aléatoire si il y a plusieur.
- `GROUP_CONCAT(?variable, SEPARATOR="")`: enchaîner tout les éléments. e.g., 
    -  ![example](assets/images/presentations/GROUP_CONCAT.png)

### `HAVING`

```SPARQL
SELECT ?publisher ?publisherLabel (AVG(?pages) AS ?avgPages)
WHERE
{
  ?book wdt:P123 ?publisher;
        wdt:P1104 ?pages.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
GROUP BY ?publisher ?publisherLabel
HAVING(COUNT(?book) > 1) # Pour utilise les aggreates en les filtres, utilise `HAVING` au lieu de `FILTER`.
ORDER BY DESC(?avgPages)
```


### Les étiquettes enchaîné

```SPARQL
SELECT ?person ?personLabel (group_concat(?citizenshipLabel;separator="/") AS ?citizenships) {
  ?person wdt:P106 wd:Q3400985 ;
          wdt:P27  ?citizenship .
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". 
    ?citizenship rdfs:label ?citizenshipLabel .
    ?person      rdfs:label ?personLabel .
  }
} GROUP BY ?person ?personLabel HAVING (count(?citizenship) > 2)
# `?citizenship rdfs:label ?citizenshipLabel` déclarer la variable intermediare `?citizenshipLabel` pour `group_concat(?citizenshipLabel;separator="/")`. 
# On peut alternativement ajouter `citizenshipLabel` vers `SELECT`, mais cela afficher `?citizenshipLabel` et `?citizenships`, quelle fornir la même information.
```

### `VALUES` et `OPTIONAL`

```SPARQL
SELECT ?item ?itemLabel ?mother ?motherLabel WHERE {
  VALUES ?item { wd:Q937 wd:Q1339 } # VALUES:  déclarer un array (des valeurs).
  OPTIONAL { ?item wdt:P25 ?mother. } # OPTIONAL: retourner si existe.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

```SPARQL
SELECT ?item ?itemLabel ?mother ?motherLabel ?ISNI WHERE {
  VALUES ?ISNI { "000000012281955X" "0000000122764157" }
  ?item wdt:P213 ?ISNI.
  OPTIONAL { ?item wdt:P25 ?mother. }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

```SPARQL
SELECT ?item ?customItemLabel ?mother ?motherLabel WHERE {
  VALUES (?item ?customItemLabel) { (wd:Q937 "Einstein") (wd:Q1339 "Bach") } #   étiquettes personnalisées
  OPTIONAL { ?item wdt:P25 ?mother. }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],mul,en". }
}
```

## Bibliographie et Plus

Immense gratitude to the WIKIDATA tutorial contributors!

[SPARQL Tutoriel à WIKIDATA](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial#See_also)

[Partticiper!](https://www.wikidata.org/wiki/Wikidata:Tools/Edit_items/fr)!

Un outil Python sympa pour wikidata: [pywikibot](https://www.mediawiki.org/wiki/Manual:Pywikibot) 