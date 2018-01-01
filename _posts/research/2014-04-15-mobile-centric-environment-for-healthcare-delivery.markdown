---
layout: post
title: "iCHS"
modified:
categories: research
excerpt: An Open Exchange for Healthcare Data.
tags: [mHealth, Spring, Sensors]
img: iCHS-logo.png
image:
  feature:
date: 2014-04-15T18:18:43+05:30
---

## Background

Availability of  healthcare  data  allows  governments to  analyze  effectiveness  of  their  policies,  monitor  spread  of a  disease,  etc.  Data  collection  for  public  healthcare  is  still  a big challenge, especially in developing countries where most of the  data  collection  is  still  done  on  paper.  Therefore,  recently many  tools,  e.g.  ODK,  Commcare,  have  become  available  that allow  data  collection  on  mobile  devices.  Similarly, during  data collection, use of health sensors to measure some of the health parameters, e.g. ECG, Oxygen Saturation, is increasing, but then the data measured by sensors is often entered manually to the mobile  device.  Finally,  the  data  collected  on  a  mobile  device is  then  entered  into  a  database  (either  an  EMR  or  a  general database)  manually,  which  is  time  consuming  and  introduces error due to manual input. While partial solutions that enable connectivity  of  sensors  to  mobile  device  or  mobile  device  to  a speciﬁc EMR are available, there is a lack of a comprehensive end-to-end solution.

The exchange of data collected at the hospital EMR's can play  an  important  role  in  public healthcare. Having timely access to right data can allow detection of  the  spread  of  a  disease,  assess  effectiveness  of  government schemes, etc. In order to improve policies and provide awareness, various government healthcare schemes are run which generate a  huge  amount  of  data.  This  data  is  collected  by  number  of ﬁeld workers and is then transferred to central repositories for further  analysis.  While  the  data  eventually  reaches  researchers and scientist for analysis, the delay (usually in months) hampers timely actions that can be taken.

## System Design

We can broadly classify the projects into two phases :-

1. In  the first phase of the project  we  developed a  framework  which  works  on mobile  devices  to  allow  collection  of  sensor  data  at  one  end and  stores data into  an  EMR  on  the  other  end,  thus  provides a comprehensive solution for data collection.
	<hr>
	<figure align="middle">
		<a href="{{ site.url }}/images/r_desg.jpg"><img src="{{ site.url }}/images/r_desg.jpg" height="300" width="300" ></a>
		<figcaption> Architecture Overview of the Android Framework</figcaption>
	</figure>
The requirements of the  framework  were  derived  after  interviewing  healthcare workers who conduct regular ﬁeld studies. We have tested our framework with a publicly available standard health sensors and OpenMRS.


2. In second phase of the project, we developed a Publish/Subscribe based Architecture moderated through a web service that can enable an early exchange of  healthcare  data  among  different  interested  parties e.g.  doctors,  researchers,  and  policy  makers.  
	<hr>
	<figure align="middle">
		<a href="{{ site.url }}/images/r_pubsubdes.jpg"><img src="{{ site.url }}/images/r_pubsubdes.jpg" height="500" width="500" ></a>
		<figcaption> Architecture Overview of the Collaborative Healthcare Framework</figcaption>
	</figure>
Our  architecture handles  the  privacy  and  security  requirements,  and  also  provides  interoperability  support  for  data  exchange.  We  have  also highlighted  how  the  architecture  deals  with  the  key  challenges involved in public health information exchange.

## Technologies Used

### Web Service

* Web Framework : [Spring MVC](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html)
* Frontend : [HTML, CSS, JavaScript, JQuery, Bootstrap](http://www.w3schools.com/)
* Database : [Hibernate](http://docs.jboss.org/hibernate/orm/4.3/manual/en-US/html_single/), [MySQL](https://www.mysql.com/)
* Project  : [Maven](https://maven.apache.org/)
* Data Exchange : [XML](http://www.w3schools.com/), [HL7](http://camel.apache.org/hl7.html)
* Security : [Spring Security](http://projects.spring.io/spring-security/)
* Pub/Sub Service :  [RabbitMQ - Java](https://www.rabbitmq.com/getstarted.html), [Spring AMQP](http://projects.spring.io/spring-amqp/)

### MySQL Connector
* Front End : [Java Swing](http://docs.oracle.com/javase/tutorial/uiswing/)
* Back End : [JDBC](http://docs.oracle.com/javase/tutorial/jdbc/)

### Android Connector
* [Android SDK](https://developer.android.com/training/index.html)
* [Android AMQP](https://www.cloudamqp.com/blog/2014-10-28-rabbitmq-on-android.html)

## Set Up

The following steps list the steps to setup the development environment on a Windows 8.1 Machine.

Prerequisites

1. Install JDK 1.8
2. Install Apache Tomcat v8 from [here](http://tomcat.apache.org/). I tested it with 32-bit Windows version.
3. Download and Extract Eclipse JEE Edition from [here](http://eclipse.org/downloads/)
	1. Install Spring Tool Suite 4.4 from the eclipse marketplace 
	2. Setup Eclipse to use Apache Server for deployment
4. Install RabbitMQ Server following instructions from [here](https://www.rabbitmq.com/install-windows.html). The server setup will require Erlang installation.

Once we have installed all the dependencies we can now get the source code to deploy the web service as well as Mobile Application on Android Phones.

1. Download the project source from [Github](https://github.com/am2990/chs-iiitd)
2. Import the code into Eclipse as *'Existing Maven Project'*.
3. Import [chs.sql]() MySQL dump to configure the basic schema for the project
4. Enable the RabbitMQ Management Plugin by running the command *rabbitmq-plugins enable rabbitmq_management* on RabbitMQ Console 
5. Access the RabbitMQ Management Console from *http://server-name:15672/* (default username: guest, password:guest) and create a new user (username:chs password:chs123)
6. RabbitMQ Logs are located in *C:\Users\<username>\AppData\Roaming\RabbitMQ\log*. 

### Publications 
1. Wadhwa, R., Singh, P., Singh, M., & Kumar, S. (2015, January). **An EMR-enabled medical sensor data collection framework.** In Communication Systems and Networks (COMSNETS), 2015 7th International Conference on (pp. 1-6). IEEE.
2. Wadhwa, R., *Mehra, A.*, Singh, P., & Singh, M. (2015, January). **A pub/sub based architecture to support public healthcare data exchange.** In Communication Systems and Networks (COMSNETS), 2015 7th International Conference on (pp. 1-6). IEEE.

