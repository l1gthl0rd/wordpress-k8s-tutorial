FROM alpine:latest
RUN apk add --no-cache python3-dev \
    && apk add --no-cache py-pip
WORKDIR /appCOPY . /app
RUN pip3 --no-cache install Flask
EXPOSE 5002
ENTRYPOINT ["python3"]
CMD ["main.py"]