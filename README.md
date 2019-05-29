# Spring-Eureka-Server
Spring Eureka Server adalah aplikasi yang menampung seluruh informasi mengenai client yang connect ke dirinya. Semua Micro service akan meng-register dirinya ke server eureka ini. 

# Dependencies
Karena kita mau agar server eureka ini juga konfigurasinya di handle oleh config server maka, dependencies untuk config client juga masuk, tapi apabila tidak, maka tidak perlu di masukan</br>

Eureka Server</br>
Actuator</br>
Config Client</br>

# How to
1. Tambahkan @EnableEurekaServer pada SpringBootApplication class, dgn konfigursi ini menandakan bila server ini akan di gunakan sebagi eureka server</br>
```
@SpringBootApplication
@EnableEurekaServer
public class SpringEurekaServerApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringEurekaServerApplication.class, args);
	}
}
```
2. Buatlah bootstrap.yml sebagai pengganti application.properties.</br> 
```
---
spring:
  application:
    name: SpringEurekaServer
  cloud:
    config:
      uri: http://localhost:9080
      failFast: false

```
Snippet di atas menjelaskan, server eureka ini bernama ```SpringEurekaServer``` , dan mengacu pada config server ```http://localhost:9080```.

# Note
Untuk konfigurasi app ini please refer to ```https://github.com/elvinotan/config/SpringEurekaServer.yml``` </br>
Apabila konfigurasi sudah di buat di sisi config server lalukan testing berdasarkan ```http:{url-config-server}:{port-config-server}/{app-name}/{app-profile}```</br>
Bila profile tidak di berikan maka secara otomatis akan megarah ke default
