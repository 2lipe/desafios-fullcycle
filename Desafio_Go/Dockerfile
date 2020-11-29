FROM golang:alpine3.12 AS compilador
WORKDIR /usr/src/app
RUN mkdir /usr/compilados
COPY ./src /usr/src/app
RUN go build -ldflags "-w" -o /usr/compilados code_education_rocks.go

FROM scratch
COPY --from=compilador /usr/compilados .
CMD ["./code_education_rocks"]