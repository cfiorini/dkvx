#### Intro

In order to run these containers you need to not have busy this tcp port:

- 80
- 1025
- 1080
- 3035
- 5432

#### 1. Run the containers

```
git pull origin git@github.com:cfiorini/dkvx.git

cd dkvx

# edit line 18 of docker-compose.yml to change your local computer path of appvx and save

docker-compose up --build
```

#### 2. Bootstrap server

```
docker exec -it dkvx_web_1 bash
cd web

bundle install

RAILS_ENV=production rake db:create

RAILS_ENV=production rake db:migrate

RAILS_ENV=production rake db:seed

yarn add bootstrap@4.3.1 jquery popper.js

RAILS_ENV=production bundle exec rails assets:precompile

bundle exec rails s -b 0.0.0.0 -p 80 -e production
```

Open the application at http://localhost 

#### 3. Check emails

Open the browser to `http://localhost:1080`