# microservices-netflix

Sample app using Netflix/spring-cloud microservices

This project contains:

* Spring-boot
* Eureka server
* Microservices spring-clod
* Ribbon balancer client
* Feign
* Google protocol buffers
* Configuration to aws.
* Configuration to gzip compression http messages with tomcat.


#Google protocol buffers

Firstly  you need install protoc in your unix system.If you have windows you can install cygwin.
(see https://github.com/google/protobuf ).
When you have installed protoc you can execute ms_a/genProtoBuffers.sh to generate MessageMetricProtos.java into src/main/java/test/microservices/a/bean/protos.
Note: You need to modify genProtoBuffers to add news dtos.

* messagemetric.proto

	package test.microservices.b.bean;

	option java_package = "test.microservices.a.bean.protos";
	option java_outer_classname = "MessageMetricProtos";

	message MessageMetric {
		required Message messages = 1;
		required int64 generatingTime = 2;

		message Message {
		required int64 id = 1;
		optional string content = 2;
		}
	}
	
This is protobuffers schema where:

* java_package is the package where java dto will generate.
* java_outer_classname is the final name of java dto wrapper.


For more info to .proto types see (https://developers.google.com/protocol-buffers/docs/proto)









