# REST API: POST rule conditions

Een methode om een conditie voor een regel aan te maken. 
Je kunt de method aanroepen met een HTTP POST request naar de volgende URL:

`https://api.copernica.com/v3/rule/$id/conditions?access_token=xxxx`

De `$id` moet hier vervangen worden door de ID van de regel waaraan je de condition wilt toevoegen.

## Beschikbare parameters

* **type**: Het type van de conditie.

Aan deze call moet tenminste het type meegegeven worden. Daarnaast zijn er 
per conditie verschillende parameters beschikbaar. Je kunt 
precies lezen wat iedere conditie inhoudt door het bijhorende artikel in 
de onderstaande links aan te klikken:

- [Change conditie](./rest-condition-type-change.md)
- [Date conditie](./rest-condition-type-date.md)
- [DoubleField conditie](./rest-condition-type-doublefield.md)
- [E-mail conditie](./rest-condition-type-email.md)
- [Export conditie](./rest-condition-type-export.md)
- [Fax conditie](./rest-condition-type-fax.md)
- [Field conditie](./rest-condition-type-field.md)
- [Interest conditie](./rest-condition-type-interest.md)
- [LastContact conditie](./rest-condition-type-lastcontact.md)
- [MiniView conditie](./rest-condition-type-miniview.md)
- [SMS conditie](./rest-condition-type-sms.md)
- [ToDo conditie](./rest-condition-type-todo.md)
- [Survey conditie](./rest-condition-type-survey.md)
- [Part conditie](./rest-condition-type-part.md)
- [ReferView conditie](./rest-condition-type-referview.md)


## Voorbeeld in PHP

Het volgende PHP script demonstreert hoe de API method te gebruiken is.

```php
// vereiste scripts
require_once('copernica_rest_api.php');

// verander dit naar je access token
$api = new CopernicaRestAPI("your-access-token", 3);

// parameters voor de methode
$data = array(
    'type' => 'date'
);

// voer het verzoek uit en print het resultaat
$api->post("rule/{$regelID}/conditions", array(), $data);

// bij een succesvolle call wordt het id van het aangemaakte verzoek teruggegeven
```

Dit voorbeeld vereist de [REST API klasse](rest-php).

## Meer informatie

* [Overzicht van alle API methodes](rest-api)
* [GET rule](./rest-get-rule)
* [POST view rules](./rest-post-view-rules)
