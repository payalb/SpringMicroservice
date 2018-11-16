Spring has deprecated the Zipkin UI and Zipkin server from Spring Boot. You will need to setup external Zipkin server or add the pom as specified above.



Download the zipkin server from Java section : 
https://zipkin.io/pages/quickstart.html 

2. After downloading the jar file fire below command to start the zipkin server
java -jar zipkin.jar
This will start the zipkin server on http://localhost:9411

For client of zipkin:
  @Bean
    public AlwaysSampler alwaysSampler() {
        return new AlwaysSampler();
    }
 
 
 spring.zipkin.base-url=http://localhost:9411/
spring.sleuth.sampler.probability=1
NOTE: By default spring.sleuth.sampler.probability=0.1 which means only 10% of tracing information will be exported to Zipkin. Make it to your desired percentage.