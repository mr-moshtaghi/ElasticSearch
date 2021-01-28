# Configuring built-in analyzers

## Configuring the `standard` analyzer

```
PUT /existing_analyzer_config
{
  "settings": {
    "analysis": {
      "analyzer": {
        "english_stop": {
          "type": "standard",
          "stopwords": "_english_"
        }
      },
      "filter": {
        "my_stemmer": {
          "type": "stemmer",
          "name": "english"
        }
      }
    }
  }
}
```

## Testing the custom analyzer

```
POST /existing_analyzer_config/_analyze
{
  "analyzer": "english_stop",
  "text": "I'm in the mood for drinking semi-dry red wine!"
}
```

```
POST /existing_analyzer_config/_analyze
{
  "tokenizer": "standard",
  "filter": [ "my_stemmer" ],
  "text": "I'm in the mood for drinking semi-dry red wine!"
}
```