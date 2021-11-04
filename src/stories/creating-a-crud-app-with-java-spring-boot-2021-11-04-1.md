---
title: Creating a CRUD app with Java Spring Boot
shortDesc: Java is a multi-platform, object-oriented, and network-centric
  language. Spring Boot is an open-source Java-based framework used to create a
  microservice. It provides a good platform for Java developers to develop
  stand-alone and production-grade spring applications.
badge: "Technology "
author: "Omomurewa George-Ashiru "
authorImage: /assets/images/murewa-1-.jpg
authorBio: Omomurewa is an IT business analyst, software developer, technical
  writer and chartered accountant in training. She has experience in supporting
  business solution software and delivery of process innovation in the financial
  services industry
timeRead: 10 min
date: 2021-11-04T11:36:37.907Z
tags:
  - hero
image: /assets/images/nuddle.jpg
imageAlt: Spring Boot
---
### Introduction

Java is a multi-platform, object-oriented, and network-centric language. Spring Boot is an open-source Java-based framework used to create a microservice. It provides a good platform for Java developers to develop stand-alone and production-grade spring applications.

This tutorial aims to walk through building a **Spring Boot REST CRUD API** using **Java Spring Boot** with **REST APIs** serving as a middleman between the backend server and the frontend/mobile application.

### Learning Objectives

At the end of this tutorial, you should be able to understand and independently carry out the following:

* Initialize a new Spring Boot application with the relevant dependencies
* Implement business logic
* Work with test/mock data
* Use Postman to test your application



### Table of contents
* [Dependencies](#dependencies)
* [Generating a New Spring Boot Gradle Project with Spring Initializer](#generating-a-new-spring-boot-gradle-project-with-pring-initializer)
* [Creating the Movie model](#creating-the-movie-model)
* [Creating the Movie service](#creating-the-movie-service)
* [Creating the Movie Controller](#creating-the-movie-controller)
* [Run and test the app using Postman](#run-and-test-the-app-using-postman)

### Dependencies

* Java Development Kit (JDK) 8 or higher 
* Gradle
* Spring Boot
* Spring Initializer
* An IDE (e.g. IntelliJ, Eclipse). I’ll be using IntelliJ
* Terminal or cmd
* Postman installed

### Generate a New Spring Boot Gradle Project with Spring Initializer

Spring Initializer is an easy way to get started with your spring boot application. We will use it to generate a new Spring Boot Gradle project. To generate a new project, open up your browser and load [Spring](https://start.spring.io/) and 
choose **Gradle project**

![### Spring Initialize](/assets/images/image1.png "### Spring Initialize")

1. Choose Java as the language
2. Add Spring Web as a dependency
3. Choose the Java you have installed on your system
   Leave other configurations as they are.
4. Click on the Generate button to download the project as a zipped file
5. Extract the zip file and open the project in an IDE
6. Sync the dependencies with Gradle. Although, this might happen automatically.



### Creating the Movie Model

 the Data model is represented as Java classes and as database tables. The business logic of the system is done by the Java objects while the database provides permanent storage for the objects. You can learn more about data modeling here or here.

We will start by creating a models package in our root project package `com.example.demo.` 

```
`public class Movie {`
    private Integer id;
    private String name;
    private String description;
    private String genre;
}
```

Within the model's package created above, create a Java class with the name Movie with the fields as shown below.

```
package com.example.demo.models;

public class Movie {
    private Integer id;
    private String name;
    private String description;
    private String genre;

    public Movie(Integer id, String name, String description, String genre) {
        this.id = id;
        this.name = name;
        this.description = description;
        this.genre = genre;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getGenre() {
        return genre;
    }

    public void setGenre(String genre) {
        this.genre = genre;
    }

    @Override
    public String toString() {
        return "Movie{" +
                "id=" + id +
                ", name='" + name + '\'' +
                ", description='" + description + '\'' +
                ", genre='" + genre + '\'' +
                '}';
    }
}
```

### Creating the Movie Service

A service contains an interface or abstract class that defines the functionalities it provides. We, however, won’t be creating an interface, we’ll go straight to define the functionalities.

In the root package of our application create a package with the name services. In the services package created above, create a called MovieService.
As opposed to setting up a database, we’ll be using dummy data which we’ll store in an ArrayList.

```
package com.example.demo.services;

import com.example.demo.models.Movie;
import java.util.ArrayList;
import java.util.List;

public class MovieService {
    //list of movies
    private List<Movie> movies;

    private static MovieService instance = null;
    public static MovieService getInstance(){
        if(instance == null){
            instance = new MovieService();
        }
        return instance;
    }


    public MovieService(){
        movies = new ArrayList<Movie>();
        movies.add(new Movie(1, "Avengers: End game", "A team of super heroes try to restore the world after half its population was wiped off.", "Science Fiction"));
        movies.add(new Movie(2, "Mr & Mrs Smith", "A couple paired to kill each other", "Action"));
        movies.add(new Movie(3, "Black is King", "A musical movie compiled from songs from The Lion King Movie", "Motion Picture"));
        movies.add(new Movie(4, "Reign", "The life of Mary, Queen of Scot", "History"));
        movies.add(new Movie(5, "Enola Holmes", "Enola Holmes goes on a journey to find her missing mother", "Adventure"));
    }

    // return all Movies
    public List<Movie> fetchMovies() {
        return movies;
    }

    // return Movie by id
    public Movie getMovieById(int id) {
        for(Movie m: movies) {
            if(m.getId() == id) {
                return m;
            }
        }
        return null;
    }

    // create Movie
    public Movie createMovie(Integer id, String name, String description, String genre) {
        Movie newMovie = new Movie(id, name, description, genre);
        movies.add(newMovie);
        return newMovie;
    }

    // update Movie
    public Movie updateMovie(Integer id, String name, String description, String genre) {
        for(Movie m: movies) {
            if(m.getId() == id) {
                int movieIndex = movies.indexOf(m);
                m.setName(name);
                m.setDescription(description);
                m.setGenre(genre);
                movies.set(movieIndex, m);
                return m;
            }
        }
        return null;
    }

    // delete movie by id
    public boolean delete(int id){
        int movieIndex = -1;
        for(Movie m: movies) {
            if(m.getId() == id) {
                movieIndex = movies.indexOf(m);
                continue;
            }
        }
        if(movieIndex > -1){
            movies.remove(movieIndex);
        }
        return true;
    }
}
```

### Creating the Movie Controller

The controller is where the main business logic is implemented.
In the root package of our project create a package with the name controllers. In the **controller's** package, we created above, create a Java class with the name **MovieController**.

```
package com.example.demo.controllers;

import com.example.demo.models.Movie;
import com.example.demo.services.MovieService;
import org.springframework.web.bind.annotation.*;

import java.util.List;
import java.util.Map;

@RestController
@RequestMapping("api/movies")
public class MovieController {
    MovieService movieService = MovieService.getInstance();

    @GetMapping("")
    public List<Movie> getMovie() {
        return movieService.fetchMovies();
    }

    @GetMapping("/{id}")
    public Movie getMovieById(@PathVariable String id){
        int movieId = Integer.parseInt(id);
        return movieService.getMovieById(movieId);
    }

    @PostMapping("")
    public Movie create(@RequestBody Map<String, String> body){
        int noOfMovies = movieService.fetchMovies().size();
        int movieId = noOfMovies + 1;
        String name = body.get("name");
        String description = body.get("description");
        String genre = body.get("genre");
        return movieService.createMovie(movieId, name, description, genre);
    }

    @PutMapping("/{id}")
    public Movie update(@PathVariable String id, @RequestBody Map<String, String> body){
        int movieId = Integer.parseInt(id);
        String name = body.get("name");
        String description = body.get("description");
        String genre = body.get("genre");
        return movieService.updateMovie(movieId, name, description, genre);
    }

    @DeleteMapping("/{id}")
    public boolean delete(@PathVariable String id){
        int movieId = Integer.parseInt(id);
        return movieService.delete(movieId);
    }
}
```

All words prefixed with **@** are called **Annotations**. An annotation is a form of metadata that provides data about a program. In other words, annotations are used to provide supplemental information about a program. 

* **@RequestController** indicates that the class can process **HTTP** requests.
* **@RequestMapping(“api/movies”)** sets the base path/route for all request endpoints within the controller
* **@GetMapping** indicates the method can process **GET** requests
* **@PostMapping** indicates the method can process **POST** requests
* **@PutMapping** indicates the method can process **PUT** requests
* **@DeleteMapping** indicates the method can process **DELETE** requests

### Run and test the app using Postman

Let’s run our application. Go to the **DemoApplication** in the root folder and click on the play button to the left.
Launch Postman and let’s start testing

### Get all movies

Make a GET request to http://localhost:8080/api/movies 


![### Spring boot Get request](/assets/images/image3.png "Get request")

### Create a new movie

Make a POST request to http://localhost:8080/api/movies 

![Spring Boot PUST request](/assets/images/image2.png "Making a POST request")

### Get a movie by ID movie

Make a GET request to http://localhost:8080/api/movies/{id}

 

![Spring Boot GET request.](/assets/images/image5.png " Getting  a movie by movie ID")

### Update a movie by ID movie

Make a PUT request to http://localhost:8080/api/movies/{id}


![Spring boot Put request](/assets/images/image4.png " Adding a movie PUT request")

### Delete a movie by ID movie

Make a PUT request to http://localhost:8080/api/movies/{id}


![Spring Boot PUT request ](/assets/images/image6.png "Deleting a  movie usibg PUT request.")

### Further reading

* [Spring Boot - Introduction](https://www.tutorialspoint.com/spring_boot/spring_boot_introduction.htm)
* [Getter and Setter Methods in Dart](https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/)
* [How to create CRUD API using Spring Boot](https://www.section.io/engineering-education/spring-boot-crud-api/)

Thank you for reading my article, you can connect with me on [Twitter](http://twitter.com/Rachael_xx) and [Linkedin](https://www.linkedin.com/in/murewageorge-ashiru/). You can also check my [blog](https://blog.murewaashiru.com/) for interesting articles.