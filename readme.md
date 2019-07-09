# Laravel com API Rest

1. Comandos

1.1. Comandos para configuração

`composer create-project -prefe-dist laravel/laravel .`

`touch database\database.sqlite`

1.2 Comandos para criar banco de dados

`php artisan make:model Product -m -f`

`php artisan make:seeder ProductsTableSeeder`

`php artisan make:resource ProductResource`

2. Instalando JWT

2.1. Execute o comando para instalar a dependencia

` composer require tymon/jwt-auth:dev-develop#d4d5261826f5529198f0a69354c28b3f77dcad5c `

2.2. Altere o formato de autenticação para JWT

` database\auth.php:45 `

2.3. Gerando assinatura

` php artisan jwt:secret `

O arquivo .env possui um novo parâmetro (assinatura) JWT_SECRET.

3. Criando novo usuário

` php artisan make:seeder UsersTableSeeder`

` php artisan migrate:refresh --seed `

4. Criando login

` Alterações no arquivo routes/api.php:29 `

5. Implementando JWT no Laravel

5.1. Implementar a interface JWTSubject na User.php

Consulte o arquivo com as implementações.

5.2 Validar o token (refresh token)

` php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider" `

` app/Http/Kernel.php:64 `

Um arquivo (config\jwt.php) será criado

Esse arquivo se encontra no link https://github.com/tymondesigns/jwt-auth/blob/develop/src/Providers/LaravelServiceProvider.php