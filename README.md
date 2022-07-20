# Zagrabi

Zagrabi is Full Stack Application.

* [Installation & Setup](#installation--setup)
    *[Configuring A Bash Alias](#configuring-a-bash-alias)
* [Technology stack](#technology-stack)
* [Topology](#topology)
    * [Database: Topology](#database-topology)
* [Useful Commands](#useful-commands)

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Installation & Setup

Before we start and [install](https://laravel.com/docs/9.x/installation) a new Laravel application on your Windows machine, make sure to install [Docker Desktop](https://www.docker.com/products/docker-desktop). Next, you should ensure that Windows Subsystem for Linux 2 (WSL2) is installed and enabled.  

Laravel Sail is automatically installed with all new Laravel applications.

### Configuring A Bash Alias  

```
vim ~/.bashrc
alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
alias sail='bash vendor/bin/sail'
alias art='sail php artisan'
source ~/.bashrc
```

## Technology Stack

<!---GraphQL -Lighthouse-php -->
RestAPI

## Topology

### Database: Topology

![database schema](https://raw.githubusercontent.com/mmatokovi/zagrabi/master/storage/app/images/database_schema.png)

## Useful Commands

```
sail up d
sail php artisan route:list
sail php artisan make:policy UserPolicy --model=User
sail php artisan make:model StorageArea -mc f
sail php artisan make:seeder ItemSeeder
sail php artisan db:seed --class=ItemSeeder
sail php artisan migrate:fresh
sail php artisan db:seed
sail php artisan thinker
sail php artisan test
sail php artisan --version
```

## Useful Commands
Possible problem fix for:  
`Module source URI is not allowed in this document: “http://0.0.0.0:5173/@vite/client”. login:19:1`

`Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at http://0.0.0.0:5173/resources/js/app.js. (Reason: CORS request did not succeed). Status code: (null).`

`Module source URI is not allowed in this document: “http://0.0.0.0:5173/resources/js/app.js”.`

<details>
    <summary>Solution</summary>

![laravel-vite-issue](https://laracasts.com/discuss/channels/vite/laravel-vite-issue?page=1&replyId=807498)

```md
I found the issue with myself was that you have to be editing the files in the docker container and running npm run dev on the same connection

I simply connected to the docker container with VS Code (plus docker ext), ran the vite within the VS Code terminal and then when I edit and save a file it automatically updated

```
</details>



<!---
composer require nuwave/lighthouse

composer require --dev mbezhanov/laravel-faker-provider-collection
php artisan vendor:publish --tag=lighthouse-schema
-->


<!--- 0Auth.zagrabi.com/token
Header-
    Account
Body-
    client_id
    client_Secret
    grant_type
res-
    access_token
    token_type:Berier
    expires_in:3600
-->