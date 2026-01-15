FROM python:3.9
WORKDIR /usr/src/app
RUN pip install fastapi uvicorn 
CMD ["git", "config", "--global", "--add", "safe.directory", "/usr/src/app"]