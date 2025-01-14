## How to set up local environment

### Git clone for docker
```
cd ~

git clone https://github.com/aungkokoye/loadberry-docker-2025.git loadberry

cd loadberry
```

### Git clone for symfony
```
git clone https://github.com/aungkokoye/lodeberry-symfony-2025.git symfony
```


### Symfony set up 

```
docker-compose up --build -d

docker exec -it webapp bash

composer install

```

### Database set up

```
php bin/console doctrine:database:create

php bin/console doctrine:migrations:migrate
```

Run the following command to create a test database. 
It will use the database name specified in the `.env` file and append the `_test` suffix:

```
bin/console   doctrine:database:create  --env=test 

bin/console   doctrine:schema:create  --env=test
```

### Webpack set up 
```
npm install

npm run dev
```

### Create admin user
This command will create admin user ```admin@loadberry.com``` with password ```password```.
```
php  bin/console  app:admin-user-create admin@loadberry.com password 
```

#### Check your website in [here!](http://127.0.0.1:7750) 


### Local env mail catcher 

We are using Schickling Mailcatcher, which captures all emails sent by the application. 

You need to run worker-consume command
```
bin/console messenger:consume
```
Choose ``async``

Quit the worker with ``CONTROL-C``

#### You can access the email interface [here!](http://127.0.0.1:1080)


### Unit Tests

```
   docker exec -it webapp bash

   php vendor/bin/phpunit 
```

