# Usage:

```
docker run -it -v $(pwd):/code -w /code -p 8080:8080 cajanzen/fabmanager 
```
## then 
fabmanager create-app


# Standard image approach

You could just run the miniconda image...
```
docker run -it -v $(pwd):/code -w /code -p 8080:8080 continuumio/miniconda3
```

## then: 
 1) pip install flask-appbuilder
 2) fabmanager create-app


# Or build your own

Alternative approach (build your own appbuilder image)

Dockerfile:
```
FROM continuumio/miniconda3
RUN pip install flask-appbuilder
```

## then just:
```
docker build -t yourname/fabmanager .
```

## then run the container:
```
docker run -it -v $(pwd):/code -w /code -p 8080:8080  yourname/fabmanager
```

## and in the container... 
```
fabmanager create-app
```
