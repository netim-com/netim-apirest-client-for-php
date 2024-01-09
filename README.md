## Description
This client is designed to communicate with the netim Rest API.
It can be integrated into all your PHP projects.

## Configuration
The configuration is done via the conf.xml file where you can specify the API URL, your login, the secret and the language of your choice.
For the login and the secret you can also override them at the instantiation of the object by giving the login and the secret to the constructor

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <url>http://oterest.netim.com/1.0/</url>
    <login>login</login>
    <secret>secret</secret>
    <preferences>
		<lang>EN</lang>
	</preferences>
</configuration>
```

## Usage
To communicate with the API, instantiate an APIRest object and use its methods to communicate.

```php
include 'APIRest.php';

$api = new APIRest();

//Exemple
$api->hello();

```
By default, the session is closed when the object is destroyed. It is advisable to manually close the session when you no longer need it if you instantiate the object several times, so as not to exceed your session quota.

```php
$api = new APIRest();

$api->hello();

$api->sessionClose();

//À partir d'ici la session est fermée. Si vous voulez réutiliser la session ultérieurement il faudra faire api.sessionOpen()
```