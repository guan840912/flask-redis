## Python Redis Sample 

To Use

```bash
git clone https://github.com/guan840912/flask-redis.git

cd flask-redis

docker-compose build 

docker-compose up -d 
Creating network "flask-redis_default" with the default driver
Creating movie.internal-bookingapp.com ... done
Creating home                          ... done
Creating redis                         ... done

docker-compose ps -a
            Name                           Command               State            Ports         
------------------------------------------------------------------------------------------------
home                            python app.py                    Up      0.0.0.0:5000->5000/tcp 
movie.internal-bookingapp.com   python app.py                    Up      0.0.0.0:55005->5000/tcp
redis                           docker-entrypoint.sh redis ...   Up      0.0.0.0:6379->6379/tcp 

docker-compose logs api

docker-compose logs home

docker-compose logs redis

docker-compose ps -a
Stopping redis                         ... done
Stopping home                          ... done
Stopping movie.internal-bookingapp.com ... done
Removing redis                         ... done
Removing home                          ... done
Removing movie.internal-bookingapp.com ... done
Removing network flask-redis_default
```

To Test
```bash
curl http://localhost:5000/home
<html>Welcome to BookingApp - Home Page - on node 857ac76502c3.<br \>Hit count = 145.<br \>Response from movie.internal-bookingapp.com service: b'<html>Welcome to Movie Booking Page Version 1.0 - on node 62cb97297ca1. Hit count = 146'
```

## Use Redis Container
```bash
docker network create redislab

docker run -d --network redislab --name redis --rm -p 6379:6379 redis

docker run -it --network redislab --rm redis redis-cli -h redis
redis:6379> ping
PONG
redis:6379> get hits
(nil)
redis:6379> set hits 1
OK
redis:6379> get hits
"1"
redis:6379> exit
```