# Learning Spark and Curl 

## What is spark

*	Spark is a framework for creating web applications in java 

*	Lightweight and inspired by Ruby Sinatra

## What is Curl

*	Utility in *nix operating systems to interact with web services

* 	Important tool in a testers kitty to test web services

##	Trying the spark hello world application from google code 

I am going to try the code that is hosted on google 

### Setting up a maven project

I use eclipse as my ide and set up a simple maven project and added these dependencies for spark

```xml
    <dependency>
      <groupId>com.sparkjava</groupId>
      <artifactId>spark-core</artifactId>
      <version>1.1</version>
    </dependency>
```

This is the example that I copied and modified from the google code page

```java
package com.sk176h.rest.spark;
import static spark.Spark.get;
import spark.Request;
import spark.Response;
import spark.Route;

public class App 
{
	public static void main(String[] args) {
	      
	      get(new Route("/hello") {
	         @Override
	         public Object handle(Request request, Response response) {
	            return "Hello World!";
	         }
	      });

	   }

}
```

`get` comes from the static import from Sinatra and takes a Route object as a parameter

We then define a nested innerclass which extends Route and override the handle method which accepts `Request` and `Response` object as parameters 

In this simple example we just return the string Hello World 

Run this example by right clicking on your eclipse and running it as a **java application**  there is no complex xml setup or server setup needed to run this simple application unlike most other java frameworks 

![Run as java application](images/curlandsinatra/1.png)

This is what you will see in your eclipse when your application runs 

![Run as java application](images/curlandsinatra/2.png)

This is exactly how sinatra works. You write a simple code and execute it and you have a web application running

In this trial we have finally managed to get the ***spark ignited***

##	Testing our simple web application using curl 

* 	Make sure you have curl installed on your machine.  On your Ubuntu/Mint box you can simply say `sudo apt-get install curl` 

*	Fire up your terminal and type the command `curl http://localhost:4567/hello`  and you should get `"Hello World!"` in your output 
like this

![Curl output](images/curlandsinatra/3.png)
