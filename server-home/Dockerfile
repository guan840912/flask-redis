FROM python:alpine
WORKDIR /app
COPY app.py app.py
RUN pip3 install redis flask requests --no-cache-dir
CMD [ "python", "app.py" ]