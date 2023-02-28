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

Now lets install the requirements for our application with `pip3 install -r requirements.txt`

![image](https://user-images.githubusercontent.com/46797181/221723586-647948f2-b6c2-4895-a147-d708dfe46066.png)

Then we run the server with `python3 -m flask run --host=0.0.0.0 --port=4567`
![image](https://user-images.githubusercontent.com/46797181/221750324-2d08d683-684c-4483-8219-56377bc8c8df.png)

The application to work needs to have the following env variables set up
```
export FRONTEND_URL="*"
export BACKEND_URL="*"
```
Then we can run the application
![image](https://user-images.githubusercontent.com/46797181/221751795-a3f8f170-9dca-4328-8fec-998623d8a974.png)
