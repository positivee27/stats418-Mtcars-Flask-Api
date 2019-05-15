# stats418-Mtcars-Flask-Api

This is an API that uses the MTCars dataset and implementes a linear regression model predicting `mpg` by using the `disp`, `hp`, `dart`, `wt`, `qsec`.

## Note

- make sure `docker` folder is ready
- make sure `scripts` folder is ready
- make sure to `clone` this repository before using the API

## Step 1

First, change your directory to the `docker` folder and run below conmand line in your terminal

`docker-compose up --build`

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

## Step 2




This is a more advanced example of an actual model deployed locally through a Flask API. The environment again is created through a docker-compose command, that again references the corresponding Dockerfile and requirements.txt file.

First as usual you will need to sync your repo to pull the new files. To run this API, change your directory to the docker folder and run:

docker-compose up

If it has created the localhost server correctly you will not get your prompt back. You will need to open a new terminal (be in the same directory) and run the following curl command to get a response

curl http://localhost:5000/

Finally, let's test out some predictions. If you open the prediction.py script you can see that the inputs into the model are "grade", "lat", "long", "sqft_living", "waterfront" and "yr_built". We will pass these through a json formatted input through a curl POST request to the API. This is done as

curl -H "Content-Type: application/json" -X POST -d '{"grade":"10.0","lat":"47.5396","long":"-122.073","sqft_living":"4495.0","waterfront":"0.0","yr_built":"2007.0"}' "http://localhost:5000/predict_price"

You can change some of the values to see the prediction change. Both of the curl commands can be found in the file curl_test.sh. To stop your server running the API, type ctrl-C. As usual, check to see if you have any docker containers running using docker container ls and stop them through docker container kill <container-name>
