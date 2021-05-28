# Projet Le Blog de Batman

## Installation

### Cloner le projet
```
git clone https://github.com/Anthony-Dmn/leblogdebatman_sf5.git
```

### Modifier les paramètres d'environnement dans le fichier .env (changer user_db et password_db, ainsi que les clés Recaptcha)
```
DATABASE_URL="mysql://user_db:password_db@127.0.0.1:3306/le_blog_de_batman?serverVersion=8.0.12"

# Clés Google Recaptcha à changer
GOOGLE_RECAPTCHA_SITE_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXX
GOOGLE_RECAPTCHA_PRIVATE_KEY=XXXXXXXXXXXXXXXXXXXXXXXXXXXX

```

### Déplacer le terminal dans le dossier cloné
```
cd leblogdebatman_sf5
```

### Taper les commandes suivantes :
```
composer install
php bin/console doctrine:database:create
php bin/console make:migration
php bin/console doctrine:migrations:migrate
php bin/console ckeditor:install
php bin/console assets:install public
php bin/console doctrine:fixtures:load
```
Les fixtures créeront :
* Un compte admin  (email: a@a.a , password: aaaaaaaaA7/)
* 50 comptes utilisateurs  (email alétoire, password : aaaaaaaaA7/)
* 200 articles
* entre 0 et 10 commentaires par article