FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# Contain the libraries to install to run app
COPY requirements.txt requirements.txt

# Inside Container
# Install the Python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first period means /backend-flask (outside container)
# second period means /backend-flask (inside container)
COPY . .

# Set environment variables (Env Vars)
# Inside the container and remains set when container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]