FROM python:3-slim-buster
WORKDIR /usr/src/app
COPY requirements.txt ./
COPY entry_point.sh /usr/local/bin/
RUN pip install -r requirements.txt
COPY . .
RUN chmod +x entry_point.sh
CMD [ "./entry_point.sh" ]
