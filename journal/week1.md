# Week 1 — App Containerization

Installed docker extension in VS code and also created an account on docker hub.
![image](https://user-images.githubusercontent.com/46797181/221718236-70b19e03-e2ca-4e6e-bd71-c2e84905e433.png)

Watched the videos: `how to ask for technical help`,`Grading homework summaries`, `live stream video` and the other videos mentioned in the checklist and the ones from the exam pro account play list. 

### Creating the Dockerfile 

In the folder `backend-flask` create the file `Dockerfile` which should have the following content 

The comments are optional but recommended 

```
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

```

![image](https://user-images.githubusercontent.com/46797181/221719296-cf484ac5-24a4-4135-a16d-2eb39f226955.png)

