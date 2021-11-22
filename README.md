# README #

This README would normally document whatever steps are necessary to get your application up and running.

## setting repository ssh key ##
```
eval $(ssh-agent)
ssh-add ~/.ssh/bitbucket_rsa
```

## Spacy repository et documentation ##
lien vers la documentation spacy
* https://spacy.io/universe/category/apis
* https://spacy.io/universe/project/spacy-api-docker

la distribution actuellement intégrant le v3 est la suivante : https://github.com/bbieniek/spacy-api-docker

run spacy fr version in docker 
```
% docker run -p "127.0.0.1:8080:80" bbieniek/spacyapi:en_v3
% docker run -p "127.0.0.1:8080:80" bbieniek/spacyapi:fr_v3
```
* puis les requêtes peuvent être lancées via une commande de type : 
```
curl --location --request POST '127.0.0.1:8080/dep' \
--header 'Content-Type: application/json' \
--data-raw '{
  "text": "Je suis très content de faire la fête !",
  "model": "fr_core_news_sm"
}'
```

### Requetes accessibles ###

* http://127.0.0.1:8080/models  (GET)
* autre requete
```
curl --location --request POST '127.0.0.1:8080/dep' \
--header 'Content-Type: application/json' \
--data-raw '{
    "text": "Un tramway nommé désir !!",
    "model":"fr_core_news_sm",
    "collapse_punctuation": false,
    "collapse_phrases": true
}'
```
