FROM python:3.7-alpine

ENV APP_HOME /app
ENV PORT 8080
WORKDIR $APP_HOME
COPY . ./

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY . .

CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 app:app