# spring-eureka-server
Spring Eureka Server adalah aplikasi yang menampung seluruh informasi mengenai client yang connect ke dirinya. Semua Micro service akan meng-register dirinya ke server eureka ini. 

# dependencies
Karena kita mau agar server eureka ini juga konfigurasinya di handle oleh config server maka, dependencies untuk config client juga masuk, tapi apabila tidak, maka tidak perlu di masukan</br>

Eureka Server</br>
Actuator</br>
Config Client</br>

# how to
1. Tambahkan @EnableEurekaServer pada SpringBootApplication class, dgn konfigursi ini menandakan bila server ini akan di gunakan sebagi eureka server
2.Buatlah bootstrap.properties selevel dengan application.properties. 
```
spring.application.name=spring-eureka-server
spring.profiles.active=dev
spring.cloud.config.uri=http://localhost:9080
spring.cloud.config.failFast=false	
```
Snippet di atas menjelaskan, server eurika ini bernama ```spring-eureka-server``` dan memiliki profile ```dev```, serta mengacu pada config server ```http://localhost:9080```.

# note
Untuk konfigurasi app ini please refer to ```https://github.com/elvinotan/config/application.yml``` lalu cari berdasarkan application name</br>
Apabila konfigurasi sudah di buat di sisi config server lalukan testing berdasarkan ```http:{url-config-server}:{port-config-server}/{app-name}/{app-profile}```
