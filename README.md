(Toda vez que fizer um clone fazer um composer install).
;
(Executar o postgres, descomentar a extensão [extension=pdo_sqlite
extension=pgsql] do php.ini do wampserve) e ativar no Wampserve com o botão esquerdo do mouse->PHP->PHP Extensions.
;
(Alterar a versão do PHP do Laravel (Variável de Ambiente do Sistema = Path(C:\wamp64\bin\php\php8.0.3)).
;
Erro no SCRAM (mudar para Versão do PHP 8.0.3 do WampServe).

# Composer
composer global require laravel/installer
composer require laravel/ui
composer create-project laravel/laravel example-app

# Laravel
laravel new test-app

# Servir estático
src=”{{ asset(‘css/styles.cc’) }}”

# Artisan
php artisan ui vue --auth
php artisan serve
php artisan route:list
php artisan down
php artisan up

php artisan make:controller ClientsController
php artisan make:controller Admin\TestControler
php artisan migrate
php artisan make:migration create_clients_table --create=clients
php artisan migrate:refresh

php artisan make:seeder NomeSeeder
php artisan make:model NomeModel
php artisan make:model StatusOperacao --seed
php artisan db:seed
php artisan db:seed --class=UserSeeder
php artisan migrate:fresh --seed

#consultar registros no banco de dados 
php artisan tinker
\App\Models\Contact::all();

$client = new \App\Models\Client(); 
$client->nome='Welliton Cunha'; 
$client->email='wellitonsousa@live.com'; 
save(); 
$client 

\App\Models\Client::all(); 
$clients = \App\Models\Client::all();
$clients[0] 
$clients = \App\Models\Client::find(1); 
$client->nome = 'Welliton Sousa'; 
$clients->delete(); 

# Implementar Login
composer require laravel/jetstream
php artisan jetstream:install livewire
php artisan migrate


# API
php artisan make:model  Models\Dog -m
php artisan migrate
php artisan make:controller Api\DogController --resouce 

# Telescope
php artisan telescope:publish
On vendor/laravel/telescope/resources/views/layout.blade.php
window.Telescope.path = 'ProjetoCRM/public/telescope';

# Livewire
composer require livewire/livewire
{php artisan livewire:publish (Corrigir erro 404 NOT FOUND)
Abrir config/livewire.php mudar 'asset_url' => env('APP_URL', 'http://localhost'),
.env -> APP_URL=http://projetos-laravel/ProjetoCRM/public}

# Migration Errors
Syntax error or access violation: 1071 Specified key was too long; max key length is 1000 bytes:
Edite o arquivo app\Providers\AppServiceProvider.php
Adicione o namespace use Illuminate\Support\Facades\Schema;
Dentro do método boot adicione Schema::defaultStringLength(191);
