FROM python:3.10-slim-buster

#Inside container
#make a new folder inside container
WORKDIR /backend-flask

#Outside container -> inside container
#this contains libraries we want to install to run the app
COPY requirements.txt requirements.txt

#Inside container
#Install python libraries used for the app
RUN pip3 install -r requirements.txt

#Outside container -> inside container
#. means everything in the current directory
# first period . -/backend-flask (outside container)
# second period . -/backend-flask (inside container)
COPY . .

#Set Environment Variables (Env Vars)
#Inside container and will remain set when the container is running

ENV FLASK_ENV=development

EXPOSE ${PORT}

#CMD (Command)
#python3 -m flask run --host=0.0.0.0 --port=4567 
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]