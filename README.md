# README
1. docker-compose run web rails new . -d mysql --skip-bundle
2. docker-compose build
3. a. docker-compose up -d (without realtime logs) 
3. b. docker-compose up (with realtime logs) 
4. copy the content of database.yml.sample into config/database.yml
5. docker-compose exec web rails db:create

Additional info

1. docker-compose logs -f (to view realtime logs)
2. docker-compose exec web is required to run rails commands
   - Examples
    1. docker-compose exec web rails routes (to check routes)
    2. docker-compose exec web rails g controller controller-name (to create controller)
3. When installing gems you need to rebuild the container
    1. docker-compose down
    2. docker-compose build
    3. a. docker-compose up -d (without realtime logs) 
    3. b. docker-compose up (with realtime logs)
4. Include this in development.rb
    config.web_console.whitelisted_ips = ["192.0.0.1/2","172.25.0.1/16", "172.0.0.1/2"]
