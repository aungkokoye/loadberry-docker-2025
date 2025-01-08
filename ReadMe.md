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


### Set up symfony

```
docker-compose up --build -d
docker exec -it webapp bash
composer install
npm install
npm run dev
```

Check you website in browser http://127.0.0.1:7750/
