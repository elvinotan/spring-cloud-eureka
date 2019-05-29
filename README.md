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
<code>
spring.application.name=spring-eureka-server</br>
spring.profiles.active=dev</br>
spring.cloud.config.uri=http://localhost:9080</br>
spring.cloud.config.failFast=false	
</code>
Snippet di atas menjelaskan, server eurika ini bernama ```spring-eureka-server``` dan memiliki profile, serta mengacu pada config server ```http://localhost:9080```.
