added app.py

where pyton application is written

created requirement 

1) python flask 
2) in memory db named as redis

# added docker file to 

FROM python:3.4-alpine  # image name
ADD . /code   # program to be added host to server
WORKDIR /code # server working directory
RUN pip install -r requirements.txt # install requirement during image build
CMD ["python", "app.py"] # run of program call first python the run app.py on it

Finaly to automate it 

docker-compose yaml file is there to build image ,tag , and create container and expose to localhost all configuration is written at yaml file
sample


version: '3'    #file version
services:       # what type of service it will run
  web:          # tag name docker build tag with web 
    build: .    # docker build command
    ports:      # exposed port host to web server
     - "5000:5000"
  redis:        # db servier image name
    image: "redis:alpine"  # between them network is auto created and attached to web + db while dockercompose up    # Creating network "application-deployment_default" with the default driver



# docker-compose up