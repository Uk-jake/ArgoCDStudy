FROM golang:1.14-alpine3.11 as builder
COPY ./main.go ./                      
RUN go build -o /go-app ./main.go     

FROM alpine:3.11                      
EXPOSE 8000                          
COPY --from=builder /go-app .        
RUN chmod +x /go-app                
ENTRYPOINT ["./go-app"]                
