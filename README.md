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

Generate subscriber<br/>
``
symfony console make:subscriber TwigEventSubscriber
``

Make form class<br/>
``
symfony console make:form CommentFormType Commen
``

``
symfony console make:functional-test Controller\\ConferenceController
``

### Security

User entity<br/>
``
symfony console make:user Admin
``

Hash password<br/>
``
symfony console security:encode-password
``

And insert in DB<br/>
``
symfony run psql -c "INSERT INTO admin (id, username, roles, password) VALUES (nextval('admin_id_seq'), 'admin', '[\"ROLE_ADMIN\"]', '\$argon2id\$v=19\$m=65536,t=4,p=1\$BQG+jovPcunctc30xG5PxQ\$TiGbx451NKdo+g9vLtfkMy4KjASKSOcnNxjij4gTX1s')"
``

Update security config<br/>
``
symfony console make:auth
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

## Tests
``
symfony run bin/phpunit
``

``
symfony run bin/phpunit tests/Controller/ConferenceControllerTest.php
``

###
Load fixtures<br/>
``
symfony console doctrine:fixtures:load
``

## Docker
Run docker containers<br/>
``
docker-compose up -d
``
## Other
View all routes<br/>
``
symfony console debug:router
``

View env vars<br/>
``
symfony var:export
``

``
symfony tunnel:open --expose-env-vars
``


For dev<br/>
``
symfony console secrets:set AKISMET_KEY
``

For prod<br/>
``
symfony var:set --sensitiveAKISMET_KEY=abcdef
``