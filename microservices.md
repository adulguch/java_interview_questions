Microservices vs Monoliths

What are the key differences between TLS and mTLS, and when would you use each?

When to go for microservices and when to go for monolith. Wanted some practical examples.

Having a shared DB between microservices, is it good or workable?

How to scale a DB?

How do you scale a microservice?

AWS Autoscaling how it works. Scenario based questions

Elastic Load Balancers - its use and working

Message Queue - AWS SQS and SNS, How you implemented them in your previous project and for what purpose.

Optimization of Application - Cacheing , Cron-Jobs (Scheduling)

Difference between Spring Data JPA and Hibernate.

What's saga pattern? why you are using it? Give an example (e-commerce, or any example)

Explain API Gateway

Advantages of feign client

Asked about Circuit Breaker design
pattern, how to implement using resilience4j?

Hystrix - I mentioned that I am using Hystrix for fallBackMethods and we have to add the dependency  Spring-cloud-starter-hystrix and we have to do some stuffs in yml file
	    Spring:
		  cloud:
		     gateway: 
			    filters:
				   - name : CircuitBreaker
				     args : name : Order_Service (suppose)
					 fallbackUri: forward: /orderFallBack
		
Suppose any service is down so we have to send fall-back response to client 


Spring cloud Config Server - It is used to storing and serving, distributed configuration across Multiple Application. 
     So rather then defining common properties in each individual application, we will keep it one single place.
				 To enable it we have to add dependency ConfigServer
				 Changes in yml file like
				 
				 Spring: 
				   application:
				      name : CONFIG_SERVER
				   cloud:
				      config:
					    server: 
						   git:
						     url: "provide git repo url"

What to do if microservice becomes slow and how to remeidate it ?

ELK Stack- We are using centralize ELK Stack for centralise logging machanism.
E stand for Elastic Search (No SQL database), L stands for Log Stash (log pipeline tool) and k stands for Kibana (Visualization)
			   
how to use Spring Sleuth + Zipkin ?

Can you explain the concepts of VPC and DNS in AWS, and their roles in cloud infrastructure?

What strategies would you use to test a third-party service that is located outside of a VPC?

In token-based REST authentication, how does the mechanism for token exchange work, and what are its security considerations?

Write a Rest API endpoint for PUT mapping and think of a scenario where you will use PUT mapping so implement the Model and service classes.
			   
Spring cloud gateway- It enable single entry point to access our application. we can define predicates to redirect client request to different microservices. 
To enable it, we have to add dependency Spring-cloud-gateway
Spring: 
	cloud:
	gateway:
	 routes:
	    -id : Order_Service
	     url:
	     predicates:
	       path=/order/**
