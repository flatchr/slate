---
title: Flatchr API Documentation
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="flatchr-api-documentation">Flatchr API Documentation v1.8.2</h1>

> Utiliser le menu de droite pour sélectionner ce qui vous intéresse et reportez-vous à cette section pour des exemples de codes (sélectionnez alors le langage que vous utilisez), des exemples de requêtes et de réponses.

### Généralités

Le site flatchr.io met a disposition un système de récupération d’annonces par API. Les partenaires autorisés peuvent ainsi récupérer leurs annonces et les afficher ailleurs que sur le site <a href="https:flatchr.io/">flatchr.io</a>.

Chaque publication d’annonce implique le décrément d’une unité du crédit (Libellébre d’emplacements libres) du contrat. La publication de l’annonce commence à la date de début de publication et ne s’arrête qu’avec le contrat. En cas de renouvellement du contrat, les annonces en ligne sont prolongées. Pour arrêter la publication d’une annonce, il faut explicitement supprimer (désactiver) la diffusion de cette annonce. Le crédit du contrat est alors re-crédité d’une
unité.

Les web services mis en place sont accessibles en REST retournent des réponses JSON ainsi que des statuts http reflétant l’état de l’exécution de la requête sur la plate-forme flatchr.io.

### Format de la réponse

Les paramètres en entrée et en sortie sont encodés en UTF-8. Il est de la responsabilité du client du web service de s’assurer que les caractères transmis ne contiennent pas de symboles « exotiques » (par exemple, un texte copié/collé à partir de Word contient des caractères comme les « ‘ » ou des puces non supportés par le web service).

### Sécurité

Un enregistrement sur l'adresse IP est fait. L'API est interrogeable uniquement en https. Avant de commencer...

### Ce que vous devez obtenir auprès de Flatchr

Afin de récupérer vos annonces, vous devez posséder :<br>
• Un compte Flatchr avec un abonnement en cours valide.<br>
• Une annonce publiée avec une diffusion sur le « site carrière » actif.

Avant toute mise en place, veuillez valider l’adéquation de ce service et votre mode de fonctionnement avec votre interlocuteur privilégié chez Flatchr <a href="mailto:laura@flatchr.io">Laura</a>.

<a href="https://flatchr.io/cgu">Terms of service</a><br>
<a href="mailto:support@flatchr.io">Support flatchr</a><br>

<h1 id="documentation-wordpress">Documentation WordPress</h1>

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<h1 id="iframe">Iframe</h1>

Le code à intégrer à votre page varie selon que l'iframe est publique ou en intranet.

## Mise en place Iframe

```
<IFRAME SRC=“HTTPS://CAREERS.FLATCHR.IO/COMPANY/[SLUG]?IFRAME=true” WIDTH=[LARGEUR
EN PIXELS] HEIGHT=[HAUTEUR EN PIXELS] FRAMEBORDER=0 MARGINWIDTH=0 MARGINHEIGHT=
0></IFRAME>
```

Le site flatchr.io met a disposition un système de récupération d’annonces via Iframe. Ce système
permet l’intégration des annonces du client sur son site sans nécessité de connaissance informatique
et par simple copier-coller. Cet iframe peut être utilisé pour un formulaire de postulation.
Afin de récupérer vos annonces, il faut récupérer votre « slug », c’est la référence unique de votre
entreprise. Elle se trouve dans l’URL de votre site carrière (exemple: dans "https://avivacuisines.flatchr.io", "avivacuisines" est la référence unique ou "slug").

Le code iframe a insérer est indiqué ci-contre.

### Paramètres Iframe liste d'annonces

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code|Non|Couleur des boutons|
|background_color|hex code|Non|Couleur du fond|
|submit_text|string|Non|Texte sur les boutons|
|iframe|string|true|Suppression des styles|

### Paramètres Iframe annonce

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code|Non|Couleur des boutons|
|background_color|hex code|Non|Couleur du fond|
|submit_text|string|Non|Texte sur les boutons|
|disable_email|boolean|Non|Désactive l'email obligatoire|
|career_redirect_url|url|Non|Url de redirection vers site carrière|
|response_text|string|Non|Texte de remerciement|
|iframe|boolean|Non|Suppression des styles|
|ifram_redirect_url|boolean|Non|Ouverture dans l'iframe|

## Mise en place Iframe Intranet

```
<IFRAME SRC=“[VOTRE URL]?IFRAME=true” WIDTH=[LARGEUR EN PIXELS] HEIGHT=[HAUTEUR
EN PIXELS] FRAMEBORDER=0 MARGINWIDTH=0 MARGINHEIGHT=0></IFRAME>
```

Le site flatchr.io met a disposition un système de récupération d’annonces via Iframe. Ce système permet l’intégration des annonces du client sur son intranet sans nécessité de connaissance informatique et par simple copier-coller. Dans votre espace flatchr « Paramètres Avancée -> Configuration Intranet », vous devez renseigner l’url de votre site intranet. Votre iframe ne s’affichera que sur les sites ayant été renseignés dans l’espace « restriction web ».

Le code à insérer indiqué ci-contre.

### Paramètres Iframe liste d'annonces

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code|Non|Couleur des boutons|
|background_color|hex code|Non|Couleur du fond|
|submit_text|string|Non|Texte sur les boutons|
|iframe|string|Oui|Suppression des styles|


### Paramètres Iframe annonce

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code|Non|Couleur des boutons|
|background_color|hex code|Non|Couleur du fond|
|submit_text|string|Non|Texte sur les boutons|
|disable_email|boolean|Non|Désactive l'email obligatoire|
|career_redirect_url|url|Non|Url de redirection vers site carrière|
|response_text|string|Non|Texte de remerciement|
|iframe|boolean|Non|Suppression des styles|
|ifram_redirect_url|boolean|Non|Ouverture dans l'iframe|

<h1 id="formulaire-de-candidature">Formulaire de candidature</h1>

Le site flatchr.io met à disposition un système de candidature par API.

Les partenaires autorisés peuvent ainsi créer une candidature pour leurs annonces
ailleurs que sur le site flatchr.io.
La création de candidature se fait via une requête http POST multipart/form-data sur
l’URL suivante :<br>
https://careers.flatchr.io/vacancy/candidate/json

Si vous utilisez un formulaire HTML ou un système web, vous devez utiliser l’url:<br>
https://careers.flatchr.io/vacancy/candidate/custom

Vous pouvez tester vos requêtes en utilisant l’url:<br>
https://careers.flatchr.io/vacancy/candidate/test

### Paramètres

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|vacancy|string|Oui|Identifiant unique de l’annonce|
|firstLibellé|string|Oui|PréLibellé /[a-zA-Z]/|
|lastLibellé|string|Oui|Libellé /[a-zA-Z]/|
|api_key|string|Oui|Clé API. Elle est créée dans l’interface Flatchr|
|email|email|Non|Email|
|phone|integer|Non|Téléphone|
|last_position|string|Non|Dernier poste|
|type|string|Non|Permis obligatoire|
|resume|base64 / hr-xml / url|Oui|Type de format pour le CV: document (si cv base64, default), json(si cv, format hr-xml)|
|comment|string|Non|Commentaire du candidat|
|offerer_id|integer|Non|Identifiant Flatchr a demander à l'équipe|
|urls|object|Non|Lien réseaux sociaux {facebook: string, linkedin: string, twitter: string, other: string}|
|legalNewsletterPartners|boolean|Non|Opt-in newsletter|
|similarities|boolean|Non|Retourne offres similaires|
|response_text|string|Non|Texte de retour|

<h1 id="recuperation-des-annonces">Récupération des annonces</h1>

Afin de récupérer vos annonces, il faut que vous récupérer votre « slug », c’est la référence unique de votre entreprise. Celui-ci se trouve dans l’URL de votre site carrière.

Exemple: dans https://avivacuisines.flatchr.io, le slug est "avivacuisines".

Le flux JSON peut être récupéré via une requête http GET sur l’URL suivante: https://careers.flatchr.io/company/[slug].json.


## Champs


|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|id|string|Oui|Clé de la diffusion|
|published|boolean|Oui|Publication active de l'annonce|
|created_at|timestamp|Oui|Date de création de la diffusion|
|vacancy|object|Oui|Détail de l'annonce|


## Annonce (vacancy)

<a id="opIdgetVacancyVacancy"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/vacancy/{vacancy} \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/vacancy/{vacancy} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/vacancy/{vacancy}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/vacancy/{vacancy}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/vacancy/{vacancy}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/vacancy/{vacancy}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/vacancy/{vacancy}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/vacancy/{vacancy}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /vacancy/{vacancy}`


Récupérer les détails d'une annonce.

<h3 id="getvacancyvacancy-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|vacancy|path|string|Oui||
|fields|query|string|Non||
|similarity|query|boolean|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getvacancyvacancy-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Clé de l'annonce|
|slug|string|Identifiant unique|
|reference|string|Référence interne|
|title|string|Titre|
|description|text|Description du poste|
|mission|text|Mission du poste|
|profile|text|Profil du poste|
|driver_license|boolean|Permis obligatoire|
|experience|integer|Année d'experience|
|contract_type|string|Contrat|
|education_level|string|Niveau d'éducation|
|activity|string|Activité du poste|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## Adresse (address)

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|location_lat|decimal|Oui|Coordonnées GPS latitude|
|location_lng|decimal|Oui|Coordonnées GPS longitude|
|postal_code|integer|Oui|Code Postal|
|route|string|Oui|Rue|
|street_number|integer|Oui|Numéro de rue|
|locality|string|Oui|Ville|
|administrative_area_level_1|string|Oui|Département|
|administrative_area_level_2|string|Oui|Région|
|formatted_address|string|Oui|Adresse complète|
|country|string|Oui|Pays|


## Entreprise (company)

<a id="opIdgetCompanyCompanyVacancyVacancy"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/vacancy/{vacancy} \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/vacancy/{vacancy} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/vacancy/{vacancy}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/vacancy/{vacancy}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/vacancy/{vacancy}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/vacancy/{vacancy}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/vacancy/{vacancy}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/vacancy/{vacancy}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/vacancy/{vacancy}`

Récupérer des informations sur l'entreprise de l'annonce.

<h3 id="getcompanycompanyvacancyvacancy-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|vacancy|path|string|Oui||
|fields|query|string|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyvacancyvacancy-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Clé de l'entreprise|
|Libellé|string|DéLibelléination|
|description|string|Description de l'entreprise|
|slug|string|Identifiant unique|
|size|integer|Libellébre d'employés|
|email|string|E-mail de contact|
|web|string|Site web|
|phone|string|Téléphone|
|status|integer|Status|
|siren|string|Code SIREN|
|vat_number|string|Numéro de TVA|
|activity|string|Activité|
|logo|string|Logo|
|retention_policy|string|Mentions légales pour postuler|
|address|string|Adresse de l'entreprise|
|created_at|timestamp|Date de création|


<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-tasks">Tâches (tasks)</h1>

## GET

<a id="opIdgetCompanyCompanyTasks"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/tasks \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/tasks HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/tasks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/tasks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/tasks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/tasks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/tasks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/tasks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/tasks`


Obtenir toutes les tâches d'un utilisateur.

<h3 id="getcompanycompanytasks-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|fields|query|string|Non||
|date|query|string(date)|Non||
|delay|query|number|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanytasks-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostCompanyCompanyTaskUserUser"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/task/user/{user} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/company/{company}/task/user/{user} HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/task/user/{user}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/task/user/{user}',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/company/{company}/task/user/{user}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/company/{company}/task/user/{user}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/task/user/{user}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/company/{company}/task/user/{user}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /company/{company}/task/user/{user}`

Créer une tâche d'utilisateur.

> Body parameter

```json
{
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
}
```

<h3 id="postcompanycompanytaskuseruser-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|true||
|user|path|string|true||
|body|body|[Model_3](#schemamodel_3)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postcompanycompanytaskuseruser-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## DELETE

<a id="opIddeleteCompanyCompanyTaskTask"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/task/{task} \
  -H 'Accept: */*'

```

```http
DELETE https://flatchr.io/company/{company}/task/{task} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/task/{task}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/task/{task}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.delete 'https://flatchr.io/company/{company}/task/{task}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/task/{task}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/task/{task}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://flatchr.io/company/{company}/task/{task}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /company/{company}/task/{task}`

Effacer une tâche d'utilisateur.

<h3 id="deletecompanycompanytasktask-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|task|path|string|Oui||

> Exemples de réponses

> Réponse par défaut

<h3 id="deletecompanycompanytasktask-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## PUT

<a id="opIdputCompanyCompanyTaskTask"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X PUT https://flatchr.io/company/{company}/task/{task} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT https://flatchr.io/company/{company}/task/{task} HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/task/{task}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "done": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/task/{task}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put 'https://flatchr.io/company/{company}/task/{task}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('https://flatchr.io/company/{company}/task/{task}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/task/{task}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://flatchr.io/company/{company}/task/{task}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /company/{company}/task/{task}`

Mettre à jour ou modifier une tâche d'utilisateur.

> Body parameter

```json
{
  "done": true
}
```

<h3 id="putcompanycompanytasktask-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|task|path|string|Oui||
|body|body|[Model_7](#schemamodel_7)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="putcompanycompanytasktask-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-members">Utilisateurs (members)</h1>

## GET

<a id="opIdgetCompanyCompanyCalendars"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/calendars \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/calendars HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/calendars',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/calendars',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/calendars',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/calendars', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/calendars");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/calendars", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/calendars`

Obtenir tous les évènements d'un calendrier d'un utilisateur.

<h3 id="getcompanycompanycalendars-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanycalendars-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-applicants">Candidats CVthèque (applicants)</h1>

## GET

<a id="opIdgetCompanyCompanySearchApplicants"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/search/applicants \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/search/applicants HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/search/applicants',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/search/applicants',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/search/applicants',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/search/applicants', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/search/applicants");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/search/applicants", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/search/applicants`

Chercher un candidat dans la CVthèque.

<h3 id="getcompanycompanysearchapplicants-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|term|query|string|Non||
|email|query|string|Non||
|vacancy|query|number|Non||
|column|query|number|Non||
|status|query|number|Non||
|offerer|query|number|Non||
|tag|query|string|Non||
|start|query|string|Non||
|end|query|string|Non||
|p|query|number|Non||
|limit|query|number|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanysearchapplicants-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|vacancy|string||
|column|string||
|firstname|string||
|lastname|string||
|created_at|timestamp||
|source|string||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant} \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}`

Obtenir des informations sur un candidat de la CVthèque.

<h3 id="getcompanycompanyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|fields|query|string|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicant-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string||
|vacancy_id|string||
|column_id|integer||
|score|integer||
|comment|string||
|created_at|integer||
|status|integer||
|seen|boolean||
|candidate/email|string||
|canidate/firstname|string||
|candidate/phone|||
|candidate/cv|string|url|
|foreigner|boolean||
|count_message|integer||
|count_message_new|boolean||
|count_comment|integer||
|count_comment_new|boolean||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostVacancyVacancyCandidate"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/vacancy/{vacancy}/candidate \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/vacancy/{vacancy}/candidate HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/vacancy/{vacancy}/candidate',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "phone": "string",
  "last_position": "string",
  "type": "json",
  "resume": {
    "path": "string",
    "key": "string"
  },
  "comment": "string",
  "note": "string",
  "urls": "string",
  "offerer_id": 0,
  "user_id": "string",
  "creator": "string",
  "hash": "stringstringst",
  "import": true,
  "external_id": "string",
  "disable_mail": true,
  "answers": [
    "string"
  ],
  "api_key": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/vacancy/{vacancy}/candidate',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/vacancy/{vacancy}/candidate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/vacancy/{vacancy}/candidate', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/vacancy/{vacancy}/candidate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/vacancy/{vacancy}/candidate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /vacancy/{vacancy}/candidate`

Créer un nouveau candidat dans la CVthèque.

> Body parameter

```json
{
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "phone": "string",
  "last_position": "string",
  "type": "json",
  "resume": {
    "path": "string",
    "key": "string"
  },
  "comment": "string",
  "note": "string",
  "urls": "string",
  "offerer_id": 0,
  "user_id": "string",
  "creator": "string",
  "hash": "stringstringst",
  "import": true,
  "external_id": "string",
  "disable_mail": true,
  "answers": [
    "string"
  ],
  "api_key": "string"
}
```

<h3 id="postvacancyvacancycandidate-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|vacancy|path|string|Oui||
|body|body|[Model_2](#schemamodel_2)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postvacancyvacancycandidate-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|action|string||
|status|integer||
|anonym|boolean||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## DELETE

<a id="opIddeleteCompanyCompanyVacancyVacancyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} \
  -H 'Accept: */*'

```

```http
DELETE https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.delete 'https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /company/{company}/vacancy/{vacancy}/applicant/{applicant}`

Effacer un candidat de la CVthèque.

<h3 id="deletecompanycompanyvacancyvacancyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|vacancy|path|string|Oui||
|applicant|path|string|Oui||
|disable_mail|query|boolean|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="deletecompanycompanyvacancyvacancyapplicantapplicant-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## PUT

<a id="opIdputCompanyCompanyVacancyVacancyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X PUT https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "vacancy_id": "string",
  "column_id": 0,
  "score": 0,
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "status": 1
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.put 'https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /company/{company}/vacancy/{vacancy}/applicant/{applicant}`

Modifier les informations d'un candidat de la CVthèque.

> Body parameter

```json
{
  "vacancy_id": "string",
  "column_id": 0,
  "score": 0,
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "status": 1
}
```

<h3 id="putcompanycompanyvacancyvacancyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|vacancy|path|string|Oui||
|applicant|path|string|Oui||
|disable_mail|query|boolean|Non||
|body|body|[Model_8](#schemamodel_8)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="putcompanycompanyvacancyvacancyapplicantapplicant-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-traits">Traits</h1>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicantCalendars"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/calendars \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant}/calendars HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/calendars',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/calendars',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}/calendars',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/calendars', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/calendars");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}/calendars", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}/calendars`

Obtenir tous les évènements d'un calendrier d'un candidat.

<h3 id="getcompanycompanyapplicantapplicantcalendars-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicantcalendars-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicantRatings"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/ratings \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant}/ratings HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/ratings',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/ratings',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}/ratings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/ratings', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/ratings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}/ratings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}/ratings`


Obtenir les évaluations d'un candidat.

<h3 id="getcompanycompanyapplicantapplicantratings-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|fields|query|string|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicantratings-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostApplicantApplicantAnswer"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/applicant/{applicant}/answer \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/applicant/{applicant}/answer HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/applicant/{applicant}/answer',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "value": "string",
  "type": "string",
  "question": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/applicant/{applicant}/answer',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/applicant/{applicant}/answer',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/applicant/{applicant}/answer', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/applicant/{applicant}/answer");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/applicant/{applicant}/answer", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /applicant/{applicant}/answer`

Créer une réponse à une question.

> Body parameter

```json
{
  "value": "string",
  "type": "string",
  "question": {}
}
```

<h3 id="postapplicantapplicantanswer-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|applicant|path|string|Oui||
|body|body|[Model_1](#schemamodel_1)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postapplicantapplicantanswer-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostCompanyCompanyApplicantApplicantTrait"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/applicant/{applicant}/trait \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/company/{company}/applicant/{applicant}/trait HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/trait',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "tag": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/trait',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/company/{company}/applicant/{applicant}/trait',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/trait', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/trait");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/company/{company}/applicant/{applicant}/trait", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /company/{company}/applicant/{applicant}/trait`

Créer un tag candidat.

> Body parameter

```json
{
  "tag": "string",
  "value": "string"
}
```

<h3 id="postcompanycompanyapplicantapplicanttrait-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|body|body|[Model_6](#schemamodel_6)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postcompanycompanyapplicantapplicanttrait-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string||
|tag_id|string||
|value|string||


<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-medias">Fichiers (medias)</h1>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicantMedias"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/medias \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant}/medias HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/medias',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/medias',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}/medias',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/medias', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/medias");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}/medias", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}/medias`

Obtenir les fichiers liés à un candidat. Pour les commentaires/notes, mails ou sms, reportez-vous aux sections adéquates.

<h3 id="getcompanycompanyapplicantapplicantmedias-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|fields|query|string|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicantmedias-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|integer||
|created_by|integer||
|created_at|timestamp||
|author/id|string||
|author/firstname|string||
|author/lastname|string||
|author/picture|string|url|
|attachment/id|string||
|attachment/name|string||
|attachment/url|string||
|attachment/created_at|timestamp||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostCompanyCompanyApplicantApplicantMedia"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/applicant/{applicant}/media \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/company/{company}/applicant/{applicant}/media HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/media',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "file": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/media',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/company/{company}/applicant/{applicant}/media',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/media', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/media");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/company/{company}/applicant/{applicant}/media", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /company/{company}/applicant/{applicant}/media`

Ajouter un fichier à un candidat.

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="postcompanycompanyapplicantapplicantmedia-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|body|body|[Model_5](#schemamodel_5)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postcompanycompanyapplicantapplicantmedia-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|integer||
|created_by|integer||
|created_at|timestamp||
|author/id|string||
|author/firstname|string||
|author/lastname|string||
|author/picture|string|url|
|attachment/id|string||
|attachment/name|string||
|attachment/url|string||
|attachment/created_at|timestamp||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## DELETE

<a id="opIddeleteCompanyCompanyApplicantApplicantMediaMedia"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/applicant/{applicant}/media/{media} \
  -H 'Accept: */*'

```

```http
DELETE https://flatchr.io/company/{company}/applicant/{applicant}/media/{media} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.delete 'https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /company/{company}/applicant/{applicant}/media/{media}`

Efface un fichier lié à candidat.

<h3 id="deletecompanycompanyapplicantapplicantmediamedia-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|media|path|integer|Oui||

> Exemples de réponses

> Réponse par défaut

<h3 id="deletecompanycompanyapplicantapplicantmediamedia-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-comments">Notes (comments)</h1>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicantComments"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/comments \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant}/comments HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/comments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/comments',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}/comments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/comments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/comments");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}/comments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}/comments`

Obtenir tous les commentaires sur un candidat.

<h3 id="getcompanycompanyapplicantapplicantcomments-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|fields|query|string|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicantcomments-responses">Réponses</h3>

|Libellé|Obligatoire|Description|
|---|---|---|
|author/id|string||
|author/firstname|string||
|author/lastname|string||
|author/picture|string|url|
|created_at|timestamp||
|created_by|integer||
|id|integer||
|private|boolean||
|ratings|query||
|text|string||

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## POST

<a id="opIdpostCompanyCompanyApplicantApplicantComment"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/applicant/{applicant}/comment \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST https://flatchr.io/company/{company}/applicant/{applicant}/comment HTTP/1.1
Host: flatchr.io
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/comment',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/comment',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*'
}

result = RestClient.post 'https://flatchr.io/company/{company}/applicant/{applicant}/comment',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/comment', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/comment");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://flatchr.io/company/{company}/applicant/{applicant}/comment", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /company/{company}/applicant/{applicant}/comment`

Créer un commentaire à propos d'un candidat.

> Body parameter

```json
{
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": true
}
```

<h3 id="postcompanycompanyapplicantapplicantcomment-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui||
|applicant|path|string|Oui||
|body|body|[Model_4](#schemamodel_4)|Non||

> Exemples de réponses

> Réponse par défaut

<h3 id="postcompanycompanyapplicantapplicantcomment-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

## DELETE

<a id="opIddeleteCompanyCompanyApplicantApplicantCommentComment"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment} \
  -H 'Accept: */*'

```

```http
DELETE https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment} HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.delete 'https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /company/{company}/applicant/{applicant}/comment/{comment}`

Effacer un commentaire de candidat???

<h3 id="deletecompanycompanyapplicantapplicantcommentcomment-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|true||
|applicant|path|string|true||
|comment|path|integer|true||

> Exemples de réponses

> Réponse par défaut

<h3 id="deletecompanycompanyapplicantapplicantcommentcomment-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

<h1 id="flatchr-api-documentation-messages">Messages</h1>

## GET

<a id="opIdgetCompanyCompanyApplicantApplicantMessages"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/messages \
  -H 'Accept: */*'

```

```http
GET https://flatchr.io/company/{company}/applicant/{applicant}/messages HTTP/1.1
Host: flatchr.io
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/messages',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://flatchr.io/company/{company}/applicant/{applicant}/messages',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*'
}

result = RestClient.get 'https://flatchr.io/company/{company}/applicant/{applicant}/messages',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/messages', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://flatchr.io/company/{company}/applicant/{applicant}/messages");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"*/*"},

    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://flatchr.io/company/{company}/applicant/{applicant}/messages", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /company/{company}/applicant/{applicant}/messages`

Get all messages from a candidate

<h3 id="getcompanycompanyapplicantapplicantmessages-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|Oui|aucune|
|applicant|path|string|Oui|aucune|
|fields|query|string|Non|aucune|

> Exemples de réponses

> Réponse par défaut

<h3 id="getcompanycompanyapplicantapplicantmessages-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string||
|created_by|string||
|created_at|timestamp||
|mail/subject|string||
|mail/text|string||
|mail/html|string||
|mail/status|||
|delivered|boolean||
|deliver_at|||
|author/firstname|string||
|author/lastname|string||
|picture|string|url|


<aside class="success">
Cette opération ne requiert pas d'authentification
</aside>

# Schemas


<h2 id="tocSresume">resume</h2>

<a id="schemaresume"></a>

```json
{
  "path": "string",
  "key": "string"
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|path|string|Oui|aucune|aucune|
|key|string|Oui|aucune|aucune|

<h2 id="tocSanswers">answers</h2>

<a id="schemaanswers"></a>

```json
[
  "string"
]

```

### Properties

*aucune*

<h2 id="tocSmodel_1">Model_1</h2>

<a id="schemamodel_1"></a>

```json
{
  "value": "string",
  "type": "string",
  "question": {}
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|value|string|Oui|aucune||
|type|string|Oui|aucune||
|question|[question](#schemaquestion)|Non|aucune||

<h2 id="tocSmodel_2">Model_2</h2>

<a id="schemamodel_2"></a>

```json
{
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "phone": "string",
  "last_position": "string",
  "type": "json",
  "resume": {
    "path": "string",
    "key": "string"
  },
  "comment": "string",
  "note": "string",
  "urls": "string",
  "offerer_id": 0,
  "user_id": "string",
  "creator": "string",
  "hash": "stringstringst",
  "import": true,
  "external_id": "string",
  "disable_mail": true,
  "answers": [
    "string"
  ],
  "api_key": "string"
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|firstLibellé|string|Oui|aucune||
|lastLibellé|string|Oui|aucune||
|email|string|Non|Oui||
|phone|string|Non|Oui||
|last_position|string|Non|aucune||
|type|string|Non|aucune|aucune|
|resume|[resume](#schemaresume)|Non|aucune||
|comment|string|Non|aucune||
|note|string|Non|aucune||
|urls|string|Non|aucune||
|offerer_id|integer|Non|aucune||
|user_id|string|Non|aucune||
|creator|string|Non|aucune||
|hash|string|Non|aucune||
|import|boolean|Non|aucune||
|external_id|string|Non|aucune||
|disable_mail|boolean|Non|aucune||
|answers|[answers](#schemaanswers)|Non|aucune||
|api_key|string|Non|aucune||

#### Enumerated Values

|Property|Value|
|---|---|
|type|json|
|type|document|

<h2 id="tocSmodel_3">Model_3</h2>

<a id="schemamodel_3"></a>

```json
{
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|description|string|Oui|aucune|aucune|
|date|string(date)|Oui|aucune|aucune|
|value|[answers](#schemaanswers)|Non|aucune|aucune|
|email|boolean|Non|aucune|aucune|

<h2 id="tocSmodel_4">Model_4</h2>

<a id="schemamodel_4"></a>

```json
{
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": true
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|text|string|Oui|aucune|aucune|
|file|string|Non|aucune|aucune|
|mentions|string|Non|aucune|aucune|
|private|boolean|Non|aucune|aucune|

<h2 id="tocSmodel_5">Model_5</h2>

<a id="schemamodel_5"></a>

```json
{
  "file": "string"
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|file|string|Non|aucune|aucune|

<h2 id="tocSmodel_6">Model_6</h2>

<a id="schemamodel_6"></a>

```json
{
  "tag": "string",
  "value": "string"
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|tag|string|Oui|aucune|aucune|
|value|string|Non|aucune|aucune|

<h2 id="tocSmodel_7">Model_7</h2>

<a id="schemamodel_7"></a>

```json
{
  "done": true
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|done|boolean|Oui|aucune|aucune|

<h2 id="tocSmodel_8">Model_8</h2>

<a id="schemamodel_8"></a>

```json
{
  "vacancy_id": "string",
  "column_id": 0,
  "score": 0,
  "firstLibellé": "string",
  "lastLibellé": "string",
  "email": "string",
  "status": 1
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|vacancy_id|string|Non|aucune|aucune|
|column_id|integer|Non|aucune|aucune|
|score|integer|Non|aucune|aucune|
|firstLibellé|string|Non|aucune|aucune|
|lastLibellé|string|Non|aucune|aucune|
|email|string|Non|aucune|aucune|
|status|integer|Non|aucune|aucune|

#### Enumerated Values

|Property|Value|
|---|---|
|status|1|

<h2 id="tocSschema1">schema1</h2>

<a id="schemaschema1"></a>

```json
{
  "path": "string",
  "key": "string"
}

```

### Properties

|Libellé|Type|Obligatoire|Restrictions|Description|
|---|---|---|---|---|
|path|string|Oui|aucune|aucune|
|key|string|Oui|aucune|aucune|

<h2 id="tocSschema2">schema2</h2>

<a id="schemaschema2"></a>

```json
{}

```

### Properties

*aucune*
