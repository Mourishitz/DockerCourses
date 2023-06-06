# Create Network
```docker
docker network create flasknetowrk
```

# Build MySQL image
```docker
docker build -t mysqlnetworkapi ./mysql/
```
## Run MySQL container
```docker
docker run -d -p 3306:3306 --name mysql_api_container --rm --network flasknetwork -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysqlapinetwork
```

# Build Flask image
```docker
docker build -t flaskexterna ./flask/
```

## Run Flask container
```docker
docker run -d -p 5000:5000 --name flaskexterna_container --rm --network flasknetwork flaskexterna:latest 
```