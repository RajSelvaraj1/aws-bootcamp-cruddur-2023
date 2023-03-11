FROM python:3.10-slim-buster

# Container or Guest OS [Inside Container]
WORKDIR /backend-flask

# Outside Container -> Inside Container
# Why copy - this contains the libraries we want to install in order to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Inside Container
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flask (inside container)
COPY . .

# Set envrionment variables (Env Vars)
# Get set inside the container and remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]