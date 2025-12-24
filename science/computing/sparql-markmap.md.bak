# SPARQL

## Theory

- Web 3.0
  - Semantic web
  - Documents → Knowledge
- RDF
  - Resource Description Framework
  - Triple-based data model
  - Example: Mona Lisa
    - Painted with oil
    - On poplar wood
- SPARQL
  - Query language for RDF
  - Questions
    - Which character is portrayed by most actors?
    - Which authors' works entered public domain this year?

## Wikidata

- Wikipedia for Web 3.0
- Semantic database
- CC 1.0 license
- Structured data
- SPARQL endpoint

## Query model

### Basic structure

```sparql
# Query template
SELECT ?a ?b ?c
WHERE 
{ 
    x y ?a.
    m n ?b.
    ?b f ?c.
}
```

### Variables

- `?a`, `?b`, `?c`
  - Target variables
  - Prefixed with `?`
- SELECT clause
  - Variables to return
  - Can use `*` for all

### Triples

- Subject-Predicate-Object
- Pattern matching
- Restrictions in `{}`
- Chaining triples
  - `;` for same subject
  - `,` for same subject and predicate

### Theoretical example

```sparql
SELECT ?fruit
WHERE
{
    ?fruit hasColor yellow;
           tastes sour,
                  sweet.
}
```

## Query types

- SELECT
  - Return variables
  - Table format
- CONSTRUCT
  - Build RDF graph
  - New triples
- ASK
  - Boolean result
  - Yes/no queries
- DESCRIBE
  - RDF data about resource
  - Implementation-dependent

## Common patterns

### Filtering

```sparql
FILTER (?year > 2000)
FILTER (LANG(?label) = "en")
```

### Optional patterns

```sparql
OPTIONAL { ?person birthPlace ?place }
```

### Union

```sparql
{ ?x type Author }
UNION
{ ?x type Painter }
```

### Aggregation

- COUNT
- SUM
- AVG
- MIN, MAX
- GROUP BY
- HAVING

### Ordering

```sparql
ORDER BY DESC(?date)
LIMIT 10
OFFSET 20
```

## Wikidata-specific

### Entities

- Items: Q-numbers
  - Q5: human
  - Q42: Douglas Adams
- Properties: P-numbers
  - P31: instance of
  - P106: occupation

### Service

```sparql
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX wdt: <http://www.wikidata.org/prop/direct/>

SELECT ?person ?personLabel
WHERE {
  ?person wdt:P31 wd:Q5;
          wdt:P106 wd:Q36180.
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "en". 
  }
}
LIMIT 10
```

## Best practices

- Use LIMIT for testing
- Add labels service
- Filter early
- Use specific properties
- Check query performance
- Leverage prefixes
