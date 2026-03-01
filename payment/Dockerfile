FROM python:3.9

WORKDIR /opt/server

COPY *.py .

COPY requirements.txt .

COPY payment.ini .

RUN pip install -r requirements.txt

ENV CART_HOST=cart \
    USER_HOST=user \
    AMQP_HOST=rabbitmq

EXPOSE 8080

CMD ["uwsgi","--ini","payment.ini"]