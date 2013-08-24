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

I set up a simple maven project and added these dependencies for spark

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

