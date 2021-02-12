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