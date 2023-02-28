# slim buster is an image from the docker hub
FROM python:3.10-slim-buster

# directory where we want to work
WORKDIR /backend-flask

# copies from outside of container to inside
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

#first period outside the container and the second one is inside 
COPY . .

ENV FLASK_ENV=development

# to expose the port outside the container
EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]