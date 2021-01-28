
## closing index
POST analyzers_test/_close

## add analyzer
PUT analyzers_test/_settings
{
  "analysis": {
    "analyzer": {
      "french_stop":{
        "type":"standard",
        "stopwords":"_french_"
      }
    }
  }
}


## opening index
POST analyzers_test/_open

