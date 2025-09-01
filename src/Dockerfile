FROM python:3.11-alpine
LABEL maintainer="Meghana"
WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
EXPOSE 8080
ENTRYPOINT ["python"]
CMD ["src/app.py"]