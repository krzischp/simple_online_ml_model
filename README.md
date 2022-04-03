*This project uses the following Docker image:*  
https://hub.docker.com/r/tiangolo/uvicorn-gunicorn-fastapi  



# Packaging your application


### Build your docker image

```
docker build -t krzischp/xgb-rest-predictor:sample .
```

### Run your docker image

```
docker run -d --name xgb -p 80:80 krzischp/xgb-rest-predictor:sample 
```

### Check your container logs

```
docker logs xgb 
```

### Test your service

```
curl -X 'POST' \
  'http://localhost/predictions' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "instance": [
    4.7, 4.0, 0.6, 0.6
  ]
}'
```

Once your container is running, you can also see the [automatic interactive API documentation](http://127.0.0.1/docs#/default/dispatch_predictions_predictions_post) (provided by Swagger UI) and test the application.

# Application

With this **API**, you can send the following **Iris** flower dimensions ['sepal length (cm)', 'sepal width (cm)', 'petal length (cm)', 'petal width (cm)'] as a request input, and receive the answer wether the specy is 'setosa' (0), 'versicolor' (1) or 'virginica' (2).
