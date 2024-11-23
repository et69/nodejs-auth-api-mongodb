# NodeJS Auth API and MongoDB with docker compose

NodeJS Auth API app that connects to MongoDB that new users can register and login to get the jwt token.

### Building and running your application

>Before starting the app, make sure change the **mongo.env.example** file to **mongo.env** and **.env.example** file in app/ dir to **.env**, and change the password values inside.

When you're ready, start your application by running:

`$ docker compose up -d`

Your application will be available at http://localhost:3000.

### Register new
``$ curl -X POST http://localhost:5000/register -H "Content-Type: application/json" -d '{"username": "john_doe", "password": "password123"}'``

### Login the existing user
``$ curl -X POST http://localhost:5000/login -H "Content-Type: application/json" -d '{"username": "john_doe", "password": "password123"}'``

### Note to Remember

1. For Python app:
    >To connect to MongoDB, mongodb_uri need to be like this "**MONGO_URI=mongodb://root:12349876@mongodb:27017/auth-db?authSource=admin**", ending with "**?authSource=admin**".

    >Errors can happen a lot. Most of them are due to dependency version.
    
2. For MongoDB:
    >db.env file store env variables for username and password, creating new mongodb admin user. Healthcheck can be done ```mongosh -u $${MONGO_INITDB_ROOT_USERNAME} -p $${MONGO_INITDB_ROOT_PASSWORD} --eval "db.stats().ok"```. Env variables need to be called by double dollar sign(\$\$). 


