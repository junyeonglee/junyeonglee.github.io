# GraphQL

GraphQL is a query language for APIs that give clients exactly the date they request.

Service is created by defining types and fields

```yaml
type Query {
    me: User
}

type User {
    id: ID
    name: string
}
```

## Queries and Mutations

**[Fields]**: fields on objects

<details>
  <summary>Example</summary>
  
```yaml
## Query
{
    hero {
        name
    }
}

## Result
{
    "data": {
        "hero": {
            "name": "R2-D2"
        }
    }
}
### query has exactly the same shape as the result
```

</details></br>

**[Arguments]**: every field and nested object can get its own set of arguments

<details>
  <summary>Example</summary>
  
```yaml
## Query
{
    human(id: "1000") {
        name
        height(unit: FOOT)
    }
}

## Result
{
    "data": {
        "hero": {
            "name": "Luke Skywalker"
            "height": 5.6430448
        }
    }
}
```

</details></br>

**[Aliases]**: rename the result of a field

<details>
  <summary>Example</summary>
  
```yaml
## Query
{
    empireHero: hero(episode: EMPIRE) { name }
    jediHero: hero(episode: JEDI) { name }
}

## Result
{
    "data": {
        "empireHero": { "name": "Luke Skywalker" }
        "jediHero": { "name": "R2-D2" }
    }
}
### you can't directly query for the same field with different arguments
```

</details></br>

**[Fragments]**: construct sets of fields

<details>
  <summary>Example</summary>
  
```yaml
## Query
{
    left: hero(episode: EMPIRE) { ...comparisonFields }
    right: hero(episode: JEDI) { ...comparisonFields }
}

fragment comparisonFields on Character {
    name
    appearsIn
}

## Result
{
    "data": {
        "empireHero": { "name": "Luke Skywalker", "appearsIn": [] }
        "jediHero": { "name": "R2-D2", "appearsIn": [] }
    }
}
```

</details></br>

**[Operation name]**: meaningful name for your operation

<details>
  <summary>Example</summary>
  
```yaml
## Query
query HeroNameAndFriends {
    hero {
        name
        friends {
            name
        }
    }
}
```

</details></br>

**[Variables]**: pass dynamic arguments

<details>
  <summary>Example</summary>
  
```yaml
## Query
query HeroNameAndFriends($episode: Episode)
{
    hero(episode: $episode) {
        name
        friends {
            name
        }
    }
}

{
    "episode": "JEDI"
}
```

</details></br>