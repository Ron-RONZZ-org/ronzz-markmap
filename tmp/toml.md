# TOML
{Alt} Tom's Obvious Minimal Language

## Syntax de base

```toml
# Se concentrer sur les humains
# Facile à lire

str1 = "Bonjour!"
str2 = "Vous pouvez \"me citer\"." # échappement
str3 = "Nom\tJos\u00E9\nLieu\tSF." # Caractères spéciaux

str4 = """
Les roses sont rouges
Les violettes sont bleues"""

str5 = """\
    Le rapide renard brun \
    saute par-dessus \
    le chien paresseux.\
    """

#---#

# hexadécimal avec préfixe `0x`
hex1 = 0xDEADBEEF

# octal avec préfixe `0o`
oct1 = 0o755

# binaire avec préfixe `0b`
bin1 = 0b11010110

# flottant
float1 = 6.626e-34

# séparateurs
float2 = 224_617.445_991_228
hex3 = 0xdead_beef

# infini
infini2 = +inf # infini positif
infini3 = -inf # infini négatif

# pas un nombre
pas1 = nan

#---#

# date locale
date_locale1 = 1979-05-27

# heure locale
heure_locale1 = 07:32:00

# datetime local
datetime_local1 = 1979-05-27T07:32:00

# datetime avec décalage
datetime_offset1 = 1979-05-27T07:32:00Z
datetime_offset2 = 1979-05-27T00:32:00-07:00
datetime_offset3 = 1979-05-27T00:32:00.999999-07:00

entiers = [ 1, 2, 3 ]
entiers1 = [
    1,
    2, # ceci est correct
]
couleurs = [ "rouge", "jaune", "vert" ]
tableau_mélangé_nesté = [ [ 1, "a", 1.5], [2, "b", "c"] ]
tableau_de_chaines = [ "toutes", 'les chaînes', """sont identiques""", '''de type''' ] # Les tableaux de type mixte sont autorisés
personne = [
    "Foo Bar <foo@example.com>",
    { nom = "Baz Qux", email = "bazqux@example.com", url = "https://example.com/bazqux" }
]
```

## Clés

```TOML
name = "Orange"
physical.color = "orange"
physical.shape = "round"
site."google.com" = true
```

```JSON
// JSON équivalent

{
  "name": "Orange",
  "physical": {
    "color": "orange",
    "shape": "round"
  },
  "site": {
    "google.com": true
  }
}
```

## Tables

```TOML
[table-1]
key1 = "some string"
key2 = 123

# Équivalent

table-2 = { key1 = "some string", key2 = 123 }

[table-3]
key1 = "another string"
key2 = 456
```

```TOML
[dog."tater.man"]
type.name = "pug"
```

```JSON
// JSON équivalent
{ "dog": { "tater.man": { "type": { "name": "pug" } } } }
```

```TOML
[[products]]
name = "Hammer"
sku = 738594937

[[products]]  #table vide dans le tableau

[[products]]
name = "Nail"
sku = 284758393

color = "gray"
```

```JSON
// JSON équivalent
{
  "products": [
    { "name": "Hammer", "sku": 738594937 },
    { },
    { "name": "Nail", "sku": 284758393, "color": "gray" }
  ]
}
```

## Bibliographie

[TOML Docs](https://toml.io/fr/v1.0.0)