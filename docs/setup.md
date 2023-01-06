# Initial Setup  

## 1. Create a directory
All software assets will be created in this directory

```
C:\Users\aniru\workspace\docker> mkdir python-docker-compose
```

## 2. Create application files 
### 2.1 Create app.py file 
app.py is the main python file. `redis` is the hostname of the redis container. 

```
import time

import redis
from flask import Flask

app = Flask(__name__)
cache = redis.Redis(host='redis', port=6379)

def get_hit_count():
    retries = 5
    while True:
        try:
            return cache.incr('hits')
        except redis.exceptions.ConnectionError as exc:
            if retries == 0:
                raise exc
            retries -= 1
            time.sleep(0.5)

@app.route('/')
def hello():
    count = get_hit_count()
    return 'Hello hee haw ....again counter:{}\n'.format(count)
```
### 2.2 Create requirements.txt 
