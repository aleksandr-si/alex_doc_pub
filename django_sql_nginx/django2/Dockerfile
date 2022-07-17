FROM python:3.9
RUN mkdir /opt/django
WORKDIR /opt/django
COPY ./new_pr ./new_pr
RUN useradd -ms /bin/bash bob && apt -y update  && apt install inetutils-ping
COPY  entry.sh /tmp/entry.sh
RUN chmod +x /tmp/entry.sh
USER bob
RUN pip install --upgrade pip \
    &&  pip install -r /opt/django/new_pr/requirements \
    && pip install mysqlclient
EXPOSE 8100
#ENTRYPOINT ["sleep", "1000"]
#ENTRYPOINT ["python3", "./new_pr/manage.py", "runserver", "0.0.0.0:8100" ]
ENTRYPOINT ["/tmp/entry.sh"]
