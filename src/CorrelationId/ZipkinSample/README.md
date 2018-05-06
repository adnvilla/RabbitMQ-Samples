# RabbitMQ-Samples
Ejemplos con RabbitMQ



# Running the example
This example has two services: frontend and backend. They both report trace data to zipkin. To setup the demo, you need to start Frontend, Backend and Zipkin.

Once the services are started, open http://localhost:8081/
* This will call the backend (http://localhost:9000/api) and show the result, which defaults to printing the current date.

Next, you can view traces that went through the backend via http://localhost:9411/?serviceName=backend
* This is a locally run zipkin service which keeps traces in memory

## Starting the Services

In separate tabs or windows, start each of frontend and backend:
```bash
$ pwd
~/frontend
$ dotnet run http://*:8081
```
and
```bash
$ pwd
~/backend
$ dotnet run http://*:9000
```


Next, run [Zipkin](http://zipkin.io/), which stores and queries traces reported by the above services.

```bash
wget -O zipkin.jar 'https://search.maven.org/remote_content?g=io.zipkin.java&a=zipkin-server&v=LATEST&c=exec'
java -jar zipkin.jar
```
