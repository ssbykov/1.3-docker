FROM python:3.8

COPY . requirements.txt /src
RUN pip3 install --no-cache-dir --upgrade -r /src/requirements.txt

COPY . /src
RUN python3 /src/manage.py makemigrations
RUN python3 /src/manage.py migrate
EXPOSE 8000

WORKDIR src

CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]

