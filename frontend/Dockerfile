FROM golang:1.18-alpine

WORKDIR /app

COPY . ./
RUN go mod download

COPY *.go ./

RUN go build -o /frontend

EXPOSE 8080

CMD [ "/frontend" ]