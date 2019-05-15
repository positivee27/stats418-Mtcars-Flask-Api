# stats418-Mtcars-Flask-Api

This is an API that uses the MTCars dataset and implementes a linear regression model predicting `mpg` by using the `disp`, `hp`, `dart`, `wt`, `qsec`.

## Note

- make sure `docker` folder is ready
- make sure `scripts` folder is ready
- make sure to `clone` this repository before using the API

## Step 1

First, change your directory to the `docker` folder and run below conmand line in your terminal

`docker-compose up --build`

Once you see something like below, you are good to move forward to next step!
```
Starting docker_flask_1 ... done
Attaching to docker_flask_1
flask_1  |  * Serving Flask app "server" (lazy loading)
flask_1  |  * Environment: production
flask_1  |    WARNING: Do not use the development server in a production environment.
flask_1  |    Use a production WSGI server instead.
flask_1  |  * Debug mode: on
flask_1  |  * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
flask_1  |  * Restarting with stat
flask_1  |  * Debugger is active!
flask_1  |  * Debugger PIN: 297-591-220
flask_1  | 172.20.0.1 - - [15/May/2019 19:58:05] "GET / HTTP/1.1" 200 -
flask_1  | 172.20.0.1 - - [15/May/2019 20:03:47] "POST /mpg HTTP/1.1" 200 -
```
## Step 2

If it has created the localhost server correctly you will not get your prompt back. You will need to open a new terminal (be in the same directory) and run the following curl command to get a response

`curl http://localhost:5000/`

you will get a response as 

`The server is up!!!`

## Step 3

The most exciting part is to get the prediction value! In order to get that 

`curl -H "Content-Type: application/json" -X POST -d '{"disp":"160.0", "hp":"110", "dart":"3.90", "wt":"2.620", "qsec":"16.46"}' "http://localhost:5000/mpg" `

## Ending 

You may repeat the `step 4` for different input and get the result. Once you are done with this API, to exit your server runing the API, press ctrl-C in your first terminal window. To close your running docker, you could run `docker container ls` and stop any image through `docker container kill <container-name>`  


