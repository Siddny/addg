FROM python:3

# Set environment variables
ENV PYTHONUNBUFFERED 1

COPY requirements.txt /

# Install dependencies.
RUN pip install -r /requirements.txt

# Set work directory.
RUN mkdir /code
WORKDIR /code

# Copy project code.
COPY . /code/

RUN ls -la /code

EXPOSE 80

CMD ["uwsgi", "--http", ":8080", "--ini", "./uwsgi/uwsgi.ini"]