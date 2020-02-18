# Symfony5-Guestbook

## Symfony local server
Start server<br/>
``
symfony server:start -d
``

Open in browser<br/>
``
symfony open:local
``

## SymfonyCloud
Init SymfonyCloud project<br/>
``
symfony project:init
``

Create SymfonyCloud project<br/>
``
symfony project:create --title="Guestbook"--plan=development
``

Deploy to SymfonyCloud<br/>
``
symfony deploy
``

Open in browser<br/>
``
symfony open:remote
``

Delete SymfonyCloud project<br/>
``
project:delete
``

Open SSH-tunnel<br/>
``
symfony tunnel:open --expose-env-vars
``

Connect to DB<br/>
``
symfony run psql
``

Close tunnel<br/>
``
symfony tunnel:close
``

## Logging
View last logs<br/>
``
symfony server:log
``

In production<br/>
``
symfony logs
``

``
symfony ssh
``

## Maker bundle
To view maker generators list<br/>
``
symfony console list make
``

Create controller<br/>
``
symfony console make:controller ConferenceController
``

## Doctrine
Create entity<br/>
``
symfony console make:entity Conference
``

Create migration<br/>
``
symfony console make:migration
``

Run migration</br>
``
symfony console doctrine:migrations:migrate
``

## DataBase
Start DB<br/>
``
docker-compose up -d
``

``
symfony run psql
``

or

``
docker exec -it symfony5-guestbook_database_1 psql -U main -W main
``

## Other
View env vars<br/>
``
symfony var:export
``

``
symfony tunnel:open --expose-env-vars
``