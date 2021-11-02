FROM python:3.7-alpine

# creating and setting workdir
RUN mkdir /app
WORKDIR /app

# installing pip
RUN python -m ensurepip --upgrade

# coppying and installing dependencies:
COPY requirements.txt /app
RUN pip3 install -r requirements.txt 

# copying app files 
COPY main.py /app/
COPY templates /app/templates

#setting default command of containe to flask run
CMD ["gunicorn", "-w 4", "-b", "0.0.0.0:8000", "main:app"] 


