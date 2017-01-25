# BaseURL, PrettyURL and remove /web


### in web/.htaccess file

> Options +FollowSymLinks
> IndexIgnore */*
> RewriteEngine on
> RewriteCond %{REQUEST_FILENAME} !-f
> RewriteCond %{REQUEST_FILENAME} !-d
> RewriteRule . index.php

###  in root .htaccess

> Options -Indexes
> RewriteEngine on
> RewriteRule ^(.*)$ web/$1 [L]

### In config/web.php

> 'components' => [
>        'urlManager' => [
>            'class' => 'yii\web\UrlManager',
>            'enablePrettyUrl' => true,
>            'showScriptName'  => false,
>            'baseUrl' => '/',
>        ],

