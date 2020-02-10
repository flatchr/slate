---
title: Flatchr API Documentation
language_tabs:
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2
---


<h1 id="flatchr-api-documentation">Flatchr API Documentation v2</h1>

> Utiliser le menu de droite pour sélectionner le langage qui vous intéresse pour des exemples de code, des exemples de requêtes et de réponses.

### Généralités

Le site flatchr.io met a disposition un système de récupération d’annonces par API. Les partenaires autorisés peuvent ainsi récupérer leurs annonces et les afficher ailleurs que sur le site <a href="https:flatchr.io/">flatchr.io</a>.

Chaque publication d’annonce implique le décrément d’une unité du crédit (nombre d’emplacements libres) du contrat. La publication de l’annonce commence à la date de début de publication et ne s’arrête qu’avec le contrat. En cas de renouvellement du contrat, les annonces en ligne sont prolongées. Pour arrêter la publication d’une annonce, il faut explicitement supprimer (désactiver) la diffusion de cette annonce. Le crédit du contrat est alors re-crédité d’une
unité.

Les web services mis en place sont accessibles en REST retournent des réponses JSON ainsi que des statuts http reflétant l’état de l’exécution de la requête sur la plate-forme flatchr.io.

### Format de la réponse

Les paramètres en entrée et en sortie sont encodés en UTF-8. Il est de la responsabilité du client du web service de s’assurer que les caractères transmis ne contiennent pas de symboles « exotiques » (par exemple, un texte copié/collé à partir de Word contient des caractères comme les « ‘ » ou des puces non supportés par le web service).

### Sécurité

Un enregistrement sur l'adresse IP est fait. L'API est interrogeable uniquement en https.

### Ce que vous devez obtenir auprès de Flatchr
<aside class="notice">
Afin de récupérer vos annonces, vous devez posséder :<br>
• Un compte Flatchr avec un abonnement en cours valide.<br>
• Une annonce publiée avec une diffusion sur le « site carrière » actif.
</aside>

<aside class="success">
Avant toute mise en place, veuillez valider l’adéquation de ce service et votre mode de fonctionnement avec votre interlocuteur Flatchr.<br>
<a href="https://flatchr.io/cgu">Terms of service</a><br>
<a href="mailto:support@flatchr.io">Support flatchr</a><br>
</aside>


<h1 id="authentification">Identification</h1>

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<h1 id="iframe">Iframe et WordPress</h1>

Le code à intégrer à votre page varie selon que l'iframe est publique ou en intranet.


## Mise en place iframe

```
<IFRAME SRC=“HTTPS://CAREERS.FLATCHR.IO/COMPANY/[SLUG]?IFRAME=true” WIDTH=100% HEIGHT=100% FRAMEBORDER=0 MARGINWIDTH=0 MARGINHEIGHT=0></IFRAME>
```

Le site flatchr.io met a disposition un système de récupération d’annonces via Iframe. Ce système
permet l’intégration des annonces du client sur son site sans nécessité de connaissance informatique
et par simple copier-coller. Cet iframe peut être utilisé pour un formulaire de postulation.
Afin de récupérer vos annonces, il faut récupérer votre « slug », c’est la référence unique de votre
entreprise. Elle se trouve dans l’URL de votre site carrière (exemple: dans "https://avivacuisines.flatchr.io", "avivacuisines" est la référence unique ou "slug").

Le code iframe a insérer est indiqué ci-contre.

### Paramètres iframe liste d'annonces

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code||Couleur des boutons|
|background_color|hex code||Couleur du fond|
|submit_text|string||Texte sur les boutons|
|iframe|string|<i class="fas fa-check"></i>|Suppression des styles|

### Paramètres iframe annonce

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code||Couleur des boutons|
|background_color|hex code||Couleur du fond|
|submit_text|string||Texte sur les boutons|
|disable_email|boolean||Désactive l'email obligatoire|
|career_redirect_url|url||Url de redirection vers site carrière|
|response_text|string||Texte de remerciement|
|iframe|boolean||Suppression des styles|
|iframe_redirect_url|boolean||Ouverture dans l'iframe|

## Mise en place iframe Intranet

Le site flatchr.io met a disposition un système de récupération d’annonces via Iframe. Ce système permet l’intégration des annonces du client sur son intranet sans nécessité de connaissance informatique et par simple copier-coller. Dans votre espace flatchr « Paramètres Avancée -> Configuration Intranet », vous devez renseigner l’url de votre site intranet. Votre iframe ne s’affichera que sur les sites ayant été renseignés dans l’espace « restriction web ».

Le code à insérer indiqué ci-contre.

### Paramètres Iframe liste d'annonces

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code||Couleur des boutons|
|background_color|hex code||Couleur du fond|
|submit_text|string||Texte sur les boutons|
|iframe|string|<i class="fas fa-check"></i> |Suppression des styles|


### Paramètres Iframe annonce

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|btn_color|hex code||Couleur des boutons|
|background_color|hex code||Couleur du fond|
|submit_text|string||Texte sur les boutons|
|disable_email|boolean||Désactive l'email obligatoire|
|career_redirect_url|url||Url de redirection vers site carrière|
|response_text|string||Texte de remerciement|
|iframe|boolean||Suppression des styles|
|iframe_redirect_url|boolean||Ouverture dans l'iframe|

<h1 id="formulaire-de-candidature">Candidature</h1>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://careers.flatchr.io/vacancy/candidate/json \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://careers.flatchr.io/vacancy/candidate/json',
  method: 'post',
  body: {
  "vacancy": "string",
  "firstname": "string",
  "lastname": "string",
  "api_key": "string",
  "email": "email",
  "phone": "integer",
  "type": "string",
  "resume": {
    "fileName": "test.pdf",
    "data": "base64 data file"
  },
  "comment": "string",
  "offerer_id": "integer",
  "urls": "object",
  "legalNewsletterPartners": true,
  "smilarities": false,
  "response_text": "string",
  },
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "vacancy": "string",
  "firstname": "string",
  "lastname": "string",
  "api_key": "string",
  "email": "email",
  "phone": "integer",
  "type": "string",
  "resume": {
    "fileName": "test.pdf",
    "data": "base64 data file"
  },
  "comment": "string",
  "offerer_id": "integer",
  "urls": "object",
  "legalNewsletterPartners": true,
  "smilarities": false,
  "response_text": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('https://careers.flatchr.io/vacancy/candidate/json',
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


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "vacancy": "string",
  "firstname": "string",
  "lastname": "string",
  "api_key": "string",
  "email": "email",
  "phone": "integer",
  "type": "string",
  "resume": {
    "fileName": "test.pdf",
    "data": "base64 data file"
  },
  "comment": "string",
  "offerer_id": "integer",
  "urls": "object",
  "legalNewsletterPartners": true,
  "smilarities": false,
  "response_text": "string",
}

r = requests.post('https://careers.flatchr.io/vacancy/candidate/json', params={

}, headers = headers)

print r.json()

```

<!-- > Body parameter

```json
{
  "vacancy": "string",
  "firstname": "string",
  "lastname": "string",
  "api_key": "string",
  "email": "email",
  "phone": "integer",
  "lastposition": "string",
  "type": "string",
  "resume": {
            "fileName": "test.pdf",
            "data": "base64 data file"
            },
  "comment": "string",
  "offerer_id": "integer",
  "urls": "object",
  "legalNewsletterPartners": true,
  "smilarities": false,
  "response_text": "string",
  }
``` -->

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

### Formulaire

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|vacancy|string|<i class="fas fa-check"></i> |Identifiant unique de l’annonce|
|firstname|string|<i class="fas fa-check"></i> |Prénom /[a-zA-Z]/|
|lastname|string|<i class="fas fa-check"></i> |Nom /[a-zA-Z]/|
|api_key|string|<i class="fas fa-check"></i> |Clé API. Elle est créée dans l’interface Flatchr|
|email|email||Email|
|phone|integer||Téléphone|
|resume|base64 / hr-xml / url|<i class="fas fa-check"></i> |Type de format pour le CV: document (si cv base64, default), json(si cv, format hr-xml)|
|comment|string||Commentaire du candidat|
|offerer_id|integer||Identifiant Flatchr a demander à l'équipe|
|urls|object||Lien réseaux sociaux {facebook: string, linkedin: string, twitter: string, other: string}|
|legalNewsletterPartners|boolean||Opt-in newsletter|
|similarities|boolean||Retourne offres similaires|
|response_text|string||Texte de retour|

<h1 id="recuperation-des-annonces">Annonces</h1>

Afin de récupérer vos annonces, il faut que vous récupérer votre « slug », c’est la référence unique de votre entreprise. Celui-ci se trouve dans l’URL de votre site carrière.

Exemple: dans https://avivacuisines.flatchr.io, le slug est "avivacuisines".

Le flux JSON peut être récupéré via une requête http GET sur l’URL suivante: https://careers.flatchr.io/company/[slug].json.


## Champs

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/[slug].json \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'https://careers.flatchr.io/company/[slug].json',
  method: 'get',
  headers: headers,
  dataType: 'json',
  success: function(data) {
    console.log(JSON.stringify(data));
  },
  error: function() {

  },
  complete: function(){

  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('https://careers.flatchr.io/company/[slug].json',
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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://careers.flatchr.io/company/[slug].json', params={

}, headers = headers)

print r.json()

```

> Exemples de réponses

```json
{
  "id": "string",
  "offer_id": "string",
  "created_at": "2019-10-24T09:42:10.024Z",
  "vacancy": "string",
  "vacancy_id": "string"
  }
```


|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|id|string|<i class="fas fa-check"></i> |Clé de la diffusion|
|offer_id|integer|<i class="fas fa-check"></i> |Identifiant offre jobboard |
|created_at|timestamp|<i class="fas fa-check"></i> |Date de création de la diffusion|
|vacancy|[Vacancy](#schemamodel_9)|<i class="fas fa-check"></i> |Détail de l'annonce|
|vacancy_id|integer|<i class="fas fa-check"></i> |Identifiant de l'annonce|


<h1 id="flatchr-api-documentation-calendars">Calendriers</h1>

## Entreprise

<a id="opIdgetCompanyCompanyCalendars"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/calendars \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/calendars', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/calendars`

Obtenir tous les évènements d'un calendrier d'une entreprise.

<h3 id="getcompanycompanycalendars-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|

> Exemples de réponses

```json
 {
  "date": "string",
  "description": "string",
  "done": true,
  "id": "string",
  "type": "string",
  "value": "url"
  }
```



<h3 id="getcompanycompanycalendars-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|string|Date|
|description|string|Description|
|done|boolean|Evènement passé|
|id|string|Identifiant|
|type|string|Exemple: "calendar"|
|value|url|Adresse url|


## Candidat

<a id="opIdgetCompanyCompanyApplicantApplicantCalendars"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/calendars \
  -H 'Accept: */*'

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


```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/calendars', params={

}, headers = headers)

print r.json()

```


`GET /company/{company}/applicant/{applicant}/calendars`

Obtenir tous les évènements d'un calendrier d'un candidat.

<h3 id="getcompanycompanyapplicantapplicantcalendars-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses

```json
 {
  "date": "string",
  "description": "string",
  "done": false,
  "id": "string",
  "type": "string",
  "value": "url"
  }
```


<h3 id="getcompanycompanyapplicantapplicantcalendars-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|string|Date|
|description|string|Description|
|done|boolean|Evènement passé|
|id|string|Identifiant|
|type|string|Exemple: "calendar"|
|value|url|Adresse url|


<h1 id="flatchr-api-documentation-applicants">CVthèque</h1>


## Informations candidat

<a id="opIdgetCompanyCompanyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant} \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/applicant/{applicant}`

Obtenir des informations sur un candidat de la CVthèque.

<h3 id="getcompanycompanyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses

```json
{
  "id": "string",
  "vacancy_id": "string",
  "column_id": "integer",
  "score": "integer",
  "comment": "string",
  "created_at": "integer",
  "status": "integer",
  "seen": true,
  "candidate": {
    "email": "email",
    "firstname": "string",
    "lastname": "string",
    "phone": "string",
    "cv": "",
   }
  }
```

<h3 id="getcompanycompanyapplicantapplicant-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string|Identifiant|
|vacancy_id|string|Identifiant de l'annonce|
|column_id|integer|Identifiant de la colonne|
|score|integer|Score du candidat|
|comment|string|Commentaire sur le candidat|
|created_at|integer|Date de création|
|status|integer|Statut du candidat|
|seen|boolean|Vu|
|candidate|[Candidate](#schemamodel_12)|Détails candidats|

## Créer un profil candidat

<a id="opIdpostVacancyVacancyCandidate"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/vacancy/{vacancy}/candidate \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/vacancy/{vacancy}/candidate',
  method: 'post',
  body: {
  "firstname": "string",
  "lastname": "string",
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
  "answers": [
    "string"
  ],
  "api_key": "string"
  },
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "firstname": "string",
  "lastname": "string",
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


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "firstname": "string",
  "lastname": "string",
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
  "answers": [
    "string"
  ],
  "api_key": "string"
}

r = requests.post('https://flatchr.io/vacancy/{vacancy}/candidate', params={

}, headers = headers)

print r.json()

```


`POST /vacancy/{vacancy}/candidate`

Créer un nouveau candidat dans la CVthèque.

<h3 id="postvacancyvacancycandidate-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|vacancy|path|string|<i class="fas fa-check"></i>|Annonce|
|firstname||string|<i class="fas fa-check"></i>|Prénom|
|lastname||string|<i class="fas fa-check"></i>|Nom|
|api_key||string|<i class="fas fa-check"></i>|Clé API|
|email||string||Email|
|phone||string||Téléphone|
|type||string||Type|
|resume||base64 / hr-xml||CV|
|comment||string||Commentaire|
|note||string||Note|
|urls||string||Urls|
|offerer_id||integer||Identifiant jobboard|
|user_id||string||Identifiant utilisateur|
|answers||string||Réponse|

> Exemples de réponses

```json
{
  "action": "string",
  "status": "integer",
  "anonym": true
  },

```

<h3 id="postvacancyvacancycandidate-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|action|string|Action|
|status|integer|Statut du candidat|
|anonym|boolean|Statut anonyme|


## Effacer un profil candidat

<a id="opIddeleteCompanyCompanyVacancyVacancyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```


`DELETE /company/{company}/vacancy/{vacancy}/applicant/{applicant}`

Effacer un candidat de la CVthèque.

<h3 id="deletecompanycompanyvacancyvacancyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|vacancy|path|string|<i class="fas fa-check"></i> |Annonce|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|api_key||string|<i class="fas fa-check"></i>|Clé API|
|disable_mail|query|boolean||Désactiver l'e-mail obligatoire|

> Exemples de réponses

```json
 {"message": "Applicant deleted"}
```


<h3 id="deletecompanycompanyvacancyvacancyapplicantapplicant-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|

## Modifier un profil candidat

<a id="opIdputCompanyCompanyVacancyVacancyApplicantApplicant"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X PUT https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}',
  method: 'put',
  body: {
  "vacancy_id": "string",
  "column_id": 0,
  "score": 0,
  "firstname": "string",
  "lastname": "string",
  "email": "string",
  "status": 1
  }
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
  "firstname": "string",
  "lastname": "string",
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "vacancy_id": "string",
  "column_id": 0,
  "score": 0,
  "firstname": "string",
  "lastname": "string",
  "email": "string",
  "status": 1
}

r = requests.put('https://flatchr.io/company/{company}/vacancy/{vacancy}/applicant/{applicant}', params={

}, headers = headers)

print r.json()

```


`PUT /company/{company}/vacancy/{vacancy}/applicant/{applicant}`

Modifier les informations d'un candidat de la CVthèque.

<h3 id="putcompanycompanyvacancyvacancyapplicantapplicant-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|vacancy|path|string|<i class="fas fa-check"></i> |Annonce|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|api_key||string|<i class="fas fa-check"></i>|Clé API|
|disable_mail|query|boolean||Désactiver l'e-mail obligatoire|
|vacancy_id||string||Identifiant annonce|
|column_id||integer||Identifiant colonne|
|score||integer||Score|
|firstname||string||Prénom|
|lastname||string||Nom|
|email||string||Email|
|status||integer||Statut|

> Exemples de réponses

```json
{
  "id": "string",
  "vacancy_id": "string",
  "column_id": "integer",
  "score": "integer",
  "comment": "string",
  "created_at": "integer",
  "status": "integer",
  "seen": false,
  "candidate": {
    "email": "email",
    "firstname": "string",
    "lastname": "string",
    "phone": "string",
    "cv": ""
  }
}  
```



<h3 id="putcompanycompanyvacancyvacancyapplicantapplicant-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string|Identifiant|
|vacancy_id|string|Identifiant de l'annonce|
|column_id|integer|Identifiant de la colonne|
|score|integer|Score du candidat|
|comment|string|Commentaire sur le candidat|
|created_at|integer|Date de création|
|status|integer|Statut du candidat|
|seen|boolean||
|candidate|[Candidate](#schemamodel_12)|Détails candidats|
|foreigner|boolean|Candidat de nationalité étrangère|
|count_message|integer|Nombre de messages|
|count_message_new|boolean|Présence de nouveaux messages|
|count_comment|integer|Nombre de commentaires|
|count_comment_new|boolean|Présence de nouveaux messages|


## Trouver un candidat

<a id="opIdgetCompanyCompanySearchApplicants"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/search/applicants \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/search/applicants', params={

}, headers = headers)

print r.json()

```


`GET /company/{company}/search/applicants`

Chercher un candidat dans la CVthèque.

<h3 id="getcompanycompanysearchapplicants-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|term|query|string|||
|email|query|string||E-mail du candidat|
|vacancy|query|number||Annonce|
|column|query|number||Nom de la colonne concernée|
|status|query|number||Statut du candidat|
|offerer|query|number||Nom de la source|
|tag|query|string||Nom du tag|
|start|query|string||Date de début à partir de laquelle chercher|
|end|query|string||Date de fin|

> Exemples de réponses

```json
{
  "vacancy": "string",
  "column": "string",
  "firstname": "string",
  "lastname": "string",
  "created_at": "string",
  "source": "string"
}
```


<h3 id="getcompanycompanysearchapplicants-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|vacancy|string|Annonce|
|column|string|Colonne concernée|
|firstname|string|Prénom du candidat|
|lastname|string|Nom du candidat|
|created_at|timestamp|Date de la création du candidat|
|source|string|Origine du candidat|


<h1 id="flatchr-api-documentation-ratings">Evaluations</h1>



## Score candidat

<a id="opIdgetCompanyCompanyApplicantApplicantRatings"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/ratings \
  -H 'Accept: */*'

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


```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/ratings', params={

}, headers = headers)

print r.json()

```


`GET /company/{company}/applicant/{applicant}/ratings`


Obtenir les évaluations d'un candidat.

<h3 id="getcompanycompanyapplicantapplicantratings-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses

```json
{
  "id": "string",
  "value": "integer",
  "created_at": "2019-09-24T09:42:10.024Z",
  "updated_at": "2019-10-24T09:42:10.024Z",
  "score": "string",
  "score_tag": "string"
}
```


<h3 id="getcompanycompanyapplicantapplicantratings-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string|Identifiant|
|value|string|Valeur|
|created_at|timestamp|Date de création|
|updated_at|timestamp|Date de dernière modification|
|score|string|Score du candidat|
|score_tag|string|Tag de score|
|author|[Author](#schemamodel_16)||


<h1 id="flatchr-api-documentation-medias">Fichiers</h1>

## Récupérer des PJ

<a id="opIdgetCompanyCompanyApplicantApplicantMedias"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/medias \
  -H 'Accept: */*'

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


```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/medias', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/applicant/{applicant}/medias`

Obtenir les fichiers liés à un candidat. 

<h3 id="getcompanycompanyapplicantapplicantmedias-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses


```json
{
  "tag": "string",
  "created_by": "string",
  "created_at": "string",
  "author": {
           "id": "string",
           "firstname": "string",
           "lastname": "string",
           "picture": "string"
            },
  "attachment": {
            "id": "string",
            "name": "string",
            "url": "string",
            "created_at": "2019-10-24T09:42:10.024Z"
              }
}
```


<h3 id="getcompanycompanyapplicantapplicantmedias-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|integer|Identifiant|
|created_by|integer|Créateur de la réponse|
|created_at|timestamp|Date de création du fichier|
|author|[Author](#schemamodel_13)||
|attachment|[Attachment](#schemamodel_14)||



## Ajouter une PJ

<a id="opIdpostCompanyCompanyApplicantApplicantMedia"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/applicant/{applicant}/media \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/media',
  method: 'post',
  body: {
  "company": "string",
  "applicant": "string",
  "file": "fichier"
  }
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company": "string",
  "applicant": "string",
  "file": "fichier"
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "company": "string",
  "applicant": "string",
  "file": "fichier"
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/media', params={

}, headers = headers)

print r.json()

```


`POST /company/{company}/applicant/{applicant}/media`

Ajouter un fichier à un candidat.

<!-- > Body parameter

```json
{
  "file": "string"
}
```
 -->
<h3 id="postcompanycompanyapplicantapplicantmedia-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|file||string||Fichier|

> Exemples de réponses

```json
{
  "tag": "string",
  "created_by": "string",
  "created_at": "string",
  "author": {
           "id": "string",
           "firstname": "string",
           "lastname": "string",
           "picture": "string"
            },
  "attachment": {
            "id": "string",
            "name": "string",
            "url": "string",
            "created_at": "2019-10-24T09:42:10.024Z"
              }
}
```



<h3 id="postcompanycompanyapplicantapplicantmedia-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|integer|Identifiant|
|created_by|integer|Créateur de la réponse|
|created_at|timestamp|Date de création du fichier|
|author|[Author](#schemamodel_13)||
|attachment|[Attachment](#schemamodel_14)||



## Effacer une PJ

<a id="opIddeleteCompanyCompanyApplicantApplicantMediaMedia"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/applicant/{applicant}/media/{media} \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/applicant/{applicant}/media/{media}', params={

}, headers = headers)

print r.json()

```


`DELETE /company/{company}/applicant/{applicant}/media/{media}`

Effacer un fichier lié à candidat.

<h3 id="deletecompanycompanyapplicantapplicantmediamedia-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|media|path|integer|<i class="fas fa-check"></i> |Fichier|

> Exemples de réponses

```json
 {"message": "Media deleted"}
```

<h3 id="deletecompanycompanyapplicantapplicantmediamedia-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|


<h1 id="flatchr-api-documentation-messages">Messages</h1>

## Messages candidat

<a id="opIdgetCompanyCompanyApplicantApplicantMessages"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/messages \
  -H 'Accept: */*'

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


```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/messages', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/applicant/{applicant}/messages`

Obtenir tous les messages d'un candidat.

<h3 id="getcompanycompanyapplicantapplicantmessages-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses

```json
{
  "id": "string",
  "created_by": "string",
  "mail": {
    "subject": "string",
    "text": "string",
    "html": "string",
    "status": ""
  },
  "delivered": true,
  "deliver_at": "2019-10-24T09:42:10.024Z",
  "author": {
    "id": "string",
    "firstname": "string",
    "lastname": "string",
    "picture": "string"
  },
  "picture": "string"
}

```


<h3 id="getcompanycompanyapplicantapplicantmessages-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string|Identifiant|
|created_by|string|Nom du créateur du message|
|created_at|timestamp|Date de création du message|
|mail|[Mail](#schemamodel_15)||
|delivered|boolean|Message délivré|
|deliver_at|timestamp|Date à laquelle le message a été délivré|
|author|[Author](#schemamodel_13)||
|picture|string|url de l'image|

<h1 id="flatchr-api-documentation-comments">Commentaires</h1>

## Obtenir des commentaires

<a id="opIdgetCompanyCompanyApplicantApplicantComments"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/applicant/{applicant}/comments \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/applicant/{applicant}/comments', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/applicant/{applicant}/comments`

Obtenir tous les commentaires sur un candidat.

<h3 id="getcompanycompanyapplicantapplicantcomments-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|

> Exemples de réponses

```json
{
    "author": {
      "id": "string",
      "firstname": "string",
      "lastname": "string",
      "picture": "string"
    },
    "created_at": "2019-10-24T09:42:10.024Z",
    "created_by": "2019-10-24T09:42:10.024Z",
    "id": "string",
    "private": true,
    "ratings": "query",
    "text": "string"
}
```


<h3 id="getcompanycompanyapplicantapplicantcomments-responses">Réponses</h3>

|Libellé|Obligatoire|Description|
|---|---|---|
|author|[Author](#schemamodel_13)||
|created_at|timestamp|Date de création du commentaire|
|created_by|integer|Nom du créateur du commentaire|
|id|integer|Identifiant|
|private|boolean|Commentaire privé|
|ratings|query|Score|
|text|string|Contenu du commentaire|



## Créer des commentaires

<a id="opIdpostCompanyCompanyApplicantApplicantComment"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/applicant/{applicant}/comment \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/applicant/{applicant}/comment',
  method: 'post',
  body: {
  "applicant": "string",
  "company": "string",
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": true
  },
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "applicant": "string",
  "company": "string",
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "applicant": "string",
  "company": "string",
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": True
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/comment', params={

}, headers = headers)

print r.json()

```



`POST /company/{company}/applicant/{applicant}/comment/{comment}`

Créer un commentaire à propos d'un candidat.

<!-- > Body parameter

```json
{
  "text": "string",
  "file": "string",
  "mentions": "string",
  "private": true
}
``` -->

<h3 id="postcompanycompanyapplicantapplicantcomment-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|text||string|<i class="fas fa-check"></i> |Texte|
|file||string||Fichier|
|mentions||string||Mentions|
|private||boolean||Caractère privé|

> Exemples de réponses

```json
{
  "created_at": "2019-10-24T09:42:10.024Z",
  "created_by":"string",
  "id":"string",
  "private":true,
  "ratings":"string",
  "text":"string"
}
```


<h3 id="postcompanycompanyapplicantapplicantcomment-responses">Réponses</h3>

|Libellé|Type|Description
|---|---|---|---|
|author|[Author](#schemamodel_13)||
|created_at|timestamp|créé à (date)|
|created_by|string|créé par (utilisateur)|
|id|string|identifiant|
|private|boolean|privé|
|ratings|string|note (évaluation)|
|text|string|texte|


## Effacer des commentaires

<a id="opIddeleteCompanyCompanyApplicantApplicantCommentComment"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment} \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/applicant/{applicant}/comment/{comment}', params={

}, headers = headers)

print r.json()

```


`DELETE /company/{company}/applicant/{applicant}/comment/{comment}`

Effacer un commentaire de candidat.

<h3 id="deletecompanycompanyapplicantapplicantcommentcomment-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i>|Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i>|Nom du candidat|
|comment|path|integer|<i class="fas fa-check"></i>|Contenu du commentaire|

> Exemples de réponses

```json
 {"message": "Media deleted"}
```


<h3 id="deletecompanycompanyapplicantapplicantcommentcomment-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|


<h1 id="flatchr-api-documentation-response">Réponse</h1>

## Créer une réponse

<a id="opIdpostApplicantApplicantAnswer"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/applicant/{applicant}/answer \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/applicant/{applicant}/answer',
  method: 'post',
  body: {
  "applicant": "string",
  "value": "string",
  "type": "string",
  "question": {}
  },
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "applicant": "string",
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "applicant": "string",
  "value": "string",
  "type": "string",
  "question": {}
}

r = requests.post('https://flatchr.io/applicant/{applicant}/answer', params={

}, headers = headers)

print r.json()

```


`POST /applicant/{applicant}/answer`

Créer une réponse à une question.

<!-- > Body parameter

```json
{
  "applicant": "string",
  "value": "string",
  "type": "string",
  "question": {}
}
``` -->

<h3 id="postapplicantapplicantanswer-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|value||string|<i class="fas fa-check"></i> |Valeur|
|type||string|<i class="fas fa-check"></i> |Type|
|question|||||

> Exemples de réponses

```json
{
  "id":"string",
  "question":"string",
  "type":"string",
  "value":"string"
}
```


<h3 id="postapplicantapplicantanswer-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Identifiant|
|question|string|Intitulé de la question|
|type|string|Exemple: "text"|
|value|string|Contenu de la réponse|

<h1 id="flatchr-api-documentation-tasks">Tâches</h1>

## Entreprise

<a id="opIdgetCompanyCompanyTasks"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X GET https://flatchr.io/company/{company}/tasks \
  -H 'Accept: */*'

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

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('https://flatchr.io/company/{company}/tasks', params={

}, headers = headers)

print r.json()

```



`GET /company/{company}/tasks`


Obtenir toutes les tâches d'une entreprise.

<h3 id="getcompanycompanytasks-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|date|query|string(date)||Date à partir de laquelle obtenir les tâches|
|delay|query|number||Sur quelle durée obtenir les tâches|

> Exemples de réponses

```json
{
  "date": "2019-10-24T09:42:10.024Z",
  "description": "string",
  "done": true,
  "id": "string",
  "type": "string"
}
```


<h3 id="getcompanycompanytasks-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|

## Créer une tâche utilisateur

<a id="opIdpostCompanyCompanyTaskUserUser"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X POST https://flatchr.io/company/{company}/task/user/{user} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/task/user/{user}',
  method: 'post',
  body: {
  "company": "string",
  "user": "string",
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
  }
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company": "string",
  "user": "string",
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "company": "string",
  "user": "string",
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
}

r = requests.post('https://flatchr.io/company/{company}/task/user/{user}', params={

}, headers = headers)

print r.json()

```


`POST /company/{company}/task/user/{user}`

Créer une tâche d'utilisateur.

<!-- > Body parameter

```json
{
  "company": "string",
  "user": "string",
  "description": "string",
  "date": "2020-01-16",
  "value": [
    "string"
  ],
  "email": true
}
``` -->

<h3 id="postcompanycompanytaskuseruser-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|user|path|string|<i class="fas fa-check"></i> |Nom de l'utilisateur|
|description||string|<i class="fas fa-check"></i>|Description|
|date||string(date)|<i class="fas fa-check"></i>|Date|
|value||string||Contenu|
|email||boolean||Email|

> Exemples de réponses

```json
{
  "date": "2019-10-24T09:42:10.024Z",
  "description": "integer",
  "done": true,
  "id": "string",
  "type": "string"
}  
```


<h3 id="postcompanycompanytaskuseruser-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|



## Effacer une tâche utilisateur

<a id="opIddeleteCompanyCompanyTaskTask"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X DELETE https://flatchr.io/company/{company}/task/{task} \
  -H 'Accept: */*'

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


```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('https://flatchr.io/company/{company}/task/{task}', params={

}, headers = headers)

print r.json()

```


`DELETE /company/{company}/task/{task}`

Effacer une tâche d'utilisateur.

<h3 id="deletecompanycompanytasktask-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|task|path|string|<i class="fas fa-check"></i> |Nom de la tâche|

> Exemples de réponses

```json
{"message": "Task deleted"}
```


<h3 id="deletecompanycompanytasktask-responses">Réponses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|Successful|string|



## Modifier une tâche utilisateur

<a id="opIdputCompanyCompanyTaskTask"></a>

> Extraits de code

```shell
# Vous pouvez également utiliser wget
curl -X PUT https://flatchr.io/company/{company}/task/{task} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'https://flatchr.io/company/{company}/task/{task}',
  method: 'put',
  body: {
  "company": "string",
  "tasks": "string,"
  "done": true
  },
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company": "string",
  "tasks": "string,"
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


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "company": "string",
  "tasks": "string,"
  "done": True
}

r = requests.put('https://flatchr.io/company/{company}/task/{task}', params={

}, headers = headers)

print r.json()

```


`PUT /company/{company}/task/{task}`

Mettre à jour ou modifier une tâche d'utilisateur.

<!-- > Body parameter

```json
{
  "done": true
}
``` -->

<h3 id="putcompanycompanytasktask-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|task|path|string|<i class="fas fa-check"></i> |Nom de la tâche|
|done||boolean|<i class="fas fa-check"></i> |aucune|Effectué|

> Exemples de réponses

```json
{
  "date": "2019-10-24T09:42:10.024Z",
  "description": "integer",
  "done": false,
  "id": "string",
  "type": "string"
}  
```


<h3 id="putcompanycompanytasktask-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|---|
|date|timestamp|Date|
|description|string|Description|
|done|boolean|Indique si la tâche a été effectuée|
|id|string|Identifiant unique de la tâche|
|type|string|Type de tâche|

<h1 id="flatchr-api-documentation-tag">Tag</h1>

## Créer un tag candidat

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
  body: {
  "company": "string",
  "applicant": "string",
  "tag": "string",
  "value": "string"
  }
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "company": "string",
  "applicant": "string",
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

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

body = {
  "company": "string",
  "applicant": "string",
  "tag": "string",
  "value": "string"
}

r = requests.post('https://flatchr.io/company/{company}/applicant/{applicant}/trait', params={

}, headers = headers)

print r.json()

```


`POST /company/{company}/applicant/{applicant}/trait`

Créer un tag candidat.

<!-- > Body parameter

```json
{
  "company": "string",
  "applicant": "string",
  "tag": "string",
  "value": "string"
}
``` -->

<h3 id="postcompanycompanyapplicantapplicanttrait-parameters">Paramètres</h3>

|Libellé|In|Type|Obligatoire|Description|
|---|---|---|---|---|
|company|path|string|<i class="fas fa-check"></i> |Nom de l'entreprise|
|applicant|path|string|<i class="fas fa-check"></i> |Nom du candidat|
|tag||string|<i class="fas fa-check"></i> |Tag|
|value||string||Contenu|

> Exemples de réponses


```json
{
  "id": "string",
  "tag_id": "string",
  "value": "string"
}
```

<h3 id="postcompanycompanyapplicantapplicanttrait-responses">Réponses</h3>

|Libellé|Type|Description|
|---|---|---|
|id|string|Identifiant|
|tag_id|string|Identifiant du tag|
|value|string|Contenu|




# Modèles


<h2 id="tocSmodel_9">Vacancy</h2>

<a id="schemamodel_9"></a>

```json
{
  "id": "string",
  "vacancy_id": "string",
  "slug": "string",
  "reference": "string",
  "title": "string",
  "description": "string",
  "experience": 1,
  "mission":"string",
  "profile":"string",
  "salary":20000,
  "status": 2,
  "language":"string",
  "contract_type_id": 3,
  "education_level_id": 5,
  "activity_id": 21,
  "channel_id": 11,
  "metier_id": 15,
  "company_id": 103,
  "mensuality": 1800,
  "apply_url":"string",
  "created_at":"2019-10-24T09:42:10.024Z",
  "updated_at":"2019-11-24T09:42:10.024Z",
  "start_date":"timestamp",
  "end_day":"timestamp",
  "semantic":"boolean",
  "driver_license":"boolean",
  "meta_title":"string",
  "meta_description":"string",
  "meta_tags": "string",
  "options":"string",
  "contract_type":"string",
  "education_level":"string",
  "activity":"string",
  "channel":"string",
  "metier":"string",
  "address":{
    "location_lat": 47.889,
    "location_lng": 15.43,
    "postal_code": 75016,
    "route":"string",
    "street_number": 10,
    "locality":"string",
    "administrative_area_level_1":"string",
    "administrative_area_level_2":"string",
    "formated_address":"string",
    "country":"string"
  },
  "company":{
    "id":"string",
    "name": "string",
    "description":"string",
    "slug":"string",
    "size": 30,
    "email":"string",
    "web":"sting",
    "phone":"string",
    "status":"integer",
    "siren":"string",
    "vat_number":"string",
    "activity":"string",
    "logo": "string",
    "retention":"string",
    "address":"string",
    "created_at":"2019-10-24T09:42:10.024Z"
  }
}

```


|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|id|string||Identifiant|
|vacancy_id|string||Identifiant de l'annonce|
|slug|string||référence unique entreprise|
|reference|string||Référence|
|title|string||Titre de l'annonce|
|description|string||Description|
|experience|integer||Nombre d'années d'expérience requis|
|mission|string||Description des missions du poste|
|profile|string||Description du profil recherché|
|salary|integer||Salaire annuel|
|status|integer||Statut|
|language|string||Compétences linguistiques|
|contract_type_id|integer||Identifiant du type de contrat|
|education_level_id|integer||Identifiant du niveau de formation|
|activity_id|integer||Identifiant du domaine de l'activité de l'entreprise|
|channel_id|integer||Identifiant du secteur du poste|
|metier_id|integer||Identifiant du métier|
|company_id|integer||Identifiant de l'entreprise|
|mensuality|string||Salaire mensuel|
|apply_url|string||Url du formulaire de candidature à remplir par le candidat|
|created_at|timestamp||Date de la création de l'annonce|
|updated_at|timestamp||Date de la mise à jour de l'annonce|
|start_date|timestamp||Date de début du contrat|
|end_day|timestamp||Date de fin du contrat|
|semantic|boolean||Sémantique|
|driver_license|boolean||Détention du permis de conduire requise|
|meta_title|string||Titre|
|meta_description|string||Description|
|meta_tags|string||Tags|
|options|string||Options|
|contract_type|string||Type de contrat|
|education_level|string||Niveau de diplôme|
|activity|string||Domaine d'activité de l'entreprise|
|channel|string||Secteur du métier|
|metier|string||Métier|
|address|[Address](#schemamodel_10)|||
|addressFormated|string||Adresse|
|company|[Company](#schemamodel_11)|||

<h2 id="tocSmodel_10">Address</h2>

<a id="schemamodel_10"></a>

```json
{
  "location_lat": 47.889,
  "location_lng": 15.43,
  "postal_code": 75016,
  "route":"string",
  "street_number": 10,
  "locality":"string",
  "administrative_area_level_1":"string",
  "administrative_area_level_2":"string",
  "formated_address":"string",
  "country":"string"
}
```

|Libellé|Type|Obligatoire|Description|
|---|---|---|---|
|location_lat|decimal|<i class="fas fa-check"></i> |Coordonnées GPS latitude|
|location_lng|decimal|<i class="fas fa-check"></i> |Coordonnées GPS longitude|
|postal_code|integer|<i class="fas fa-check"></i> |Code Postal|
|route|string|<i class="fas fa-check"></i> |Rue|
|street_number|integer|<i class="fas fa-check"></i> |Numéro de rue|
|locality|string|<i class="fas fa-check"></i> |Ville|
|administrative_area_level_1|string|<i class="fas fa-check"></i> |Département|
|administrative_area_level_2|string|<i class="fas fa-check"></i> |Région|
|formated_address|string|<i class="fas fa-check"></i> |Adresse complète|
|country|string|<i class="fas fa-check"></i> |Pays|


<h2 id="tocSmodel_11">Company</h2>

<a id="schemamodel_11"></a>

```json
{
  "id":"string",
  "name": "string",
  "description":"string",
  "slug":"string",
  "size": 30,
  "email":"string",
  "web":"sting",
  "phone":"string",
  "status":"integer",
  "siren":"string",
  "vat_number":"string",
  "activity":"string",
  "logo": "string",
  "retention":"string",
  "address":"string",
  "created_at":"2019-10-24T09:42:10.024Z"
}
```

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Clé de l'entreprise|
|name|string|Dénomination|
|description|string|Description de l'entreprise|
|slug|string|Identifiant unique|
|size|integer|Nombre d'employés|
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


<h2 id="tocSmodel_12">Candidate</h2>

<a id="schemamodel_12"></a>

```json
{
  "email":"string",
  "firstname":"string",
  "lastname":"string",
  "phone":"string",
  "cv":""
}
```

|Libellé|Type|Description|
|---|---|---|---|
|email|string|Email|
|firstname|string|Prénom|
|lastname|string|Nom|
|phone||Téléphone|
|cv|string|url|

<h2 id="tocSmodel_13">Author</h2>

<a id="schemamodel_13"></a>

```json
{
  "id":"string",
  "firstname":"string",
  "lastname":"string",
  "picture":"string"
}
```

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Identifiant de l'auteur|
|firstname|string|Prénom de l'auteur|
|lastname|string|Nom de l'auteur|
|picture|string|url|

<h2 id="tocSmodel_14">Attachment</h2>

<a id="schemamodel_14"></a>

```json
{
  "id":"string",
  "name":"string",
  "url":"string",
  "phone":"string",
  "created_at":"2019-10-24T09:42:10.024Z"
}
```

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Identifiant|
|name|string|Nom|
|url|string|Url|
|created_at|timestamp||


<h2 id="tocSmodel_15">Mail</h2>

<a id="schemamodel_15"></a>

```json
{
  "subject":"string",
  "text":"string",
  "html":"string",
  "status":"string"
}
```

|Libellé|Type|Description|
|---|---|---|---|
|subject|string|Objet du mail|
|text|string|Contenu du mail|
|html|string||
|status|string|Statut|

<h2 id="tocSmodel_16">Author</h2>

<a id="schemamodel_16"></a>

```json
{
  "id":"string",
  "firstname":"string",
  "lastname":"string",
  "email":"string"
}
```

|Libellé|Type|Description|
|---|---|---|---|
|id|string|Identifiant de l'auteur|
|firstname|string|Prénom de l'auteur|
|lastname|string|Nom de l'auteur|
|email|string|Adresse mail|
