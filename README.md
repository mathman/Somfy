Cette application permet de gerer les équipements Somfy via l'API [Somfy Open API](https://developer.somfy.com/)

### Installation

```
npm install
```

## Configuration
```
const port = ''; // Port d'écoute du serveur web
const consumeKey = ''; // Clé à récuperer sur le site de Somfy lorsque vous avez crée un compte et une application lié à votre compte
const secret = ''; // Clé à récuperer sur le site de Somfy lorsque vous avez crée un compte et une application lié à votre compte
const ip_address = ''; // Adresse IP de la machine qui executera l'application

```

## Démarrage

```
node index.js
```

## Utilisation

L'application crée une api web afin de récupérer les informations via des requetes http.

Dans un premier temps il faut demander un code d'authentification sur le site de Somfy.
```
http://ip_address:port/auth
```
Lorsque cette autorisation est faite un fichier avec le token récupéré sera enregistré à la racine de l'application.

- Récupere tous les sites Somfy liés à votre compte
```
Méthode GET
http://ip_address:port/allsites
```

- Récupere le site renseigné via son id
```
Méthode GET
http://ip_address:port/site/:siteid
```

- Récupere tous les équipements du site renseigné via son id
```
Méthode GET
http://ip_address:port/site/:siteid/device
```

- récupere l'équipement renseigné via son id
```
Méthode GET
http://ip_address:port/device/:deviceid
```

- Exécute une action sur l'équipement renseigné via son id
```
Méthode POST
http://ip_address:port/device/:deviceid/exec

data:
{
    "name": "",
    "parameters": [
        {
            "name": "",
            "value": "object"
        }
    ]
}
```

## Informations

Pour plus d'informations vous pouvez visiter le site de Somfy [Documentation de l'API](https://developer.somfy.com/apis-docs)
