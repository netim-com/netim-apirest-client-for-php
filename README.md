# APIRest-client-php

## Description
Ce client est conçu pour communiquer avec l'api netim REST.
Il peut être intégré à tous vos projets php.

## Configuration
La configuration se fait via le fichier conf.xml où vous pouvez y spécifier l'url de l'API, votre login, le secret et la langue de votre choix.
Pour le login et le secret vous pouvez aussi les outrepasser à l'instanciation de l'objet en donnant le login et le secret au constructeur

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <url>http://ote.rest.netim.com/1.0/</url>
    <login>login</login>
    <secret>secret</secret>
    <language>EN</language>
</configuration>
```

## Utilisation
Pour communiquer avec l'API, instanciez un objet APIRest et utilisez ses méthodes pour communiquer.

```php
include 'APIRest.php';

$api = new APIRest();

//Exemple
$api->hello();

```
Par défaut la session est fermée à la destruction de l'objet. Il est conseillé de fermer manuellement la session quand vous n'en avez plus besoin si vous instanciez plusieurs fois l'objet, afin de ne pas dépasser votre quota de sessions.

```php
$api = new APIRest();

$api->hello();

$api->sessionClose();

//À partir d'ici la session est fermée. Si vous voulez réutiliser la session ultérieurement il faudra faire api.sessionOpen()
```