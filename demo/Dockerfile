# base image  
FROM python:3.8   

# Install the Django
RUN python -m pip install Django

# setup environment variable  
ENV DockerHOME=/home/app/webapp  

# set work directory  
RUN mkdir -p $DockerHOME  

# where your code lives  
WORKDIR $DockerHOME  

# set environment variables  
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1  

# install dependencies  
RUN pip install --upgrade pip  

# install coralogix  
RUN pip install coralogix_logger

# copy whole project to your docker home directory
COPY . $DockerHOME

# port where the Django app runs  
EXPOSE 8000  

# start server  
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]   