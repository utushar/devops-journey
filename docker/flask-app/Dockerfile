#use official Python image
FROM python:3.11-slim

#set working directory
WORKDIR /app

#copy files
COPY . .

#Install Dependencies
RUN pip install -r requirements.txt

#expose port
EXPOSE 5000

#run the app
CMD ["python", "app.py"]
