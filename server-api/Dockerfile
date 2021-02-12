FROM python:alpine
WORKDIR /app
COPY app.py app.py
RUN pip3 install redis flask 
CMD [ "python", "app.py" ]