# AWSXRaySpring6SampleApp
This sample application demonstrates how to instrument a [Spring 6](https://spring.io/blog/2022/11/16/spring-framework-6-0-goes-ga) application with [AWS X-Ray](https://github.com/aws/aws-xray-sdk-java).

Spring 6 usese the Jakarta namespace instead of Javax for many of its new classes. X-Ray made a parallel set of classes for Jakarta so you can continue using your favorite EE.

# How to run this project
1. Open the project in IntelliJ.
1. Click Run at the top -> "Run HelloApplication"
1. Run your X-Ray Daemon. I faked one by listening to the data with nc. "nc -lu 127.0.0.1 2000"
1. Go to http://127.0.0.1:8080/hello
1. You should see sgments sent to the daemon.
{"format": "json", "version": 1}
{"name":"MyTestSegment","id":"2f77a0ec21c7c77d","start_time":1.676588794852E9,"trace_id":"1-63eeb6fa-2a8b727c314baa634c2dd671","end_time":1.676588794905E9,"http":{"request":{"method":"GET","client_ip":"127.0.0.1","url":"http://127.0.0.1:8080/hello","runtime_version":"17.0.4.1"}}
