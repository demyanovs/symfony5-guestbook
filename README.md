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

Create dump<br/>
``
symfony run pg_dump --data-only > dump.sql
``

Restore dump<br/>
``
symfony run psql < dump.sql
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

## Messenger
Get messages<br/>
``
symfony console messenger:consume async -vv
``

Run as demon<br/>
``
symfony run -d --watch=config,src,templates,vendor symfony console messenger:consume async
``

View failed queue<br/>
``
symfony console messenger:failed:show
``

Retry failed queue<br/>
``
symfony console messenger:failed:retry
``

View worker's logs
``
symfony logs --worker=messages all
``

### RabbitMQ
View web interface (guest/guest)<br/>
``
symfony open:local:rabbitmq
``

## Workflow
Visualize<br/>
``
symfony console workflow:dump comment | dot -Tpng -o workflow.png
``

## Webmail
Email catcher<br/>
``
symfony open:local:webmail
``

## Docker
Run containers<br/>
``
docker-compose up -d
``

Stop containers<br/>
``
docker-compose stop
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

View rabbitmq ui
``
symfony tunnel:open
``

``
symfony open:remote:rabbitmq
``

when done

``
symfony tunnel:close
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