FROM python:3.8-slim-buster

# build - create directory and cd in
ARG APP_DIR=/app

WORKDIR ${APP_DIR}

# copy files from local into the image
ADD main.py /app
ADD utils.py /app
ADD requirements.txt /app
ADD public /app/public
ADD templates /app/templates

# install dependencies
RUN pip install -r requirements.txt

# environment variables
# ENV APP_DIR=/app
# ENV PORT=3000

# EXPOSE ${PORT}
# WORKDIR ${APP_DIR}

# run the app - ENTRYPOINT and CMD will be combined
# CMD ["python3", "-m" , "flask", "run", "--host=0.0.0.0"]
ENTRYPOINT [ "python", "main.py"]

# CMD [ "app.py" ]