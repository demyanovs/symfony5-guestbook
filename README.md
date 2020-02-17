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

To view maker generators<br/>
``
symfony console list make
``