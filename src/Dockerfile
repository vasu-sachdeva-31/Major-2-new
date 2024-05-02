FROM python:3-slim-buster
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN pip install -r requirements.txt
COPY . .
RUN python manage.py makemigrations
RUN python manage.py migrate
RUN python manage.py migrate --fake sessions zero
RUN python manage.py migrate --fake-initial
RUN python manage.py shell < init_admin.py
RUN python manage.py makemigrations app
RUN python manage.py migrate app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
