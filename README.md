# README

This service used for replicate confluent issue that need to connect to multiple broker node

Detail framework
- rails 6
- karafka 1.4

Environment variable file `.env`, we can follow the env sample in `.env sample`


kafka consumer
start by 
1. `bundle install`
2. `bundle exec karafka s`


api server
1. `bundle install`
2. `rails s`

ruby-kafka consumer
1. `bundle install`
2. `ruby ruby_kafka.rb`

to produce message we can use the api server and call api kafka producer by this curl
```
curl --location --request POST 'localhost:3000/produce_message' \
--header 'Content-Type: application/json' \
--data-raw '{
    "topic_name": "user"
}'
```

the consumer and producer will have a prefix of happyfresh