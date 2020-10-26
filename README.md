# Title: Coronavirus tracker app with spring-boot
- Duration: `4 hours`
- Deployment strategy : Own PC
- Team challenge : `solo`
## Learning objectives
- To be able to install java
- Be able to work in java environment
- Gain more insight into the Spring-boot
- Be able to work with dependencies in spring boot
- Learn how to work with mvc patterns
- Be able to fetch data from csv file and be able to display it
- Be able to work with Thymeleaf template engine
## The Mission
Today we are going to make a coronavirus tracker application which tracks all the cases that occurs and updates it daily. 

#### Step 1: What is Java development kit or in short JDK ?
The Java Development Kit (JDK) is a software development environment that offers a collection of tools and libraries necessary for developing Java applications. You need the JDK to convert your source code into a format that the Java Runtime Environment (JRE) can execute.

The JDK includes the Java Runtime Environment (JRE), an interpreter (java), a compiler (javac), an archiver (jar), a documentation generator (javadoc), and some other development tools. The Java Runtime Environment itself consists of the Java Virtual Machine (JVM), supporting files, and core classes.

![JDK](jdk.png)

Typically, if you are only interested in running Java programs on your machine or browser, you only need to install JRE. However, if you would like to develop an application and do Java programming, you will need JDK.

**Since April 16, 2019, you have to create an account in order to be able to download [JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**


#### Step 2: Install Maven
Apache Maven is a cornerstone of Java development, and the most used build management tool for Java. Maven's streamlined, XML-based configuration model enables developers to rapidly describe or grasp the outlines of any Java-based project, which makes starting and sharing new projects a snap. Maven also supports test-driven development, long-term project maintenance, and its declarative configuration and wide range of plugins make it a popular option for CI/CD. This article is a quick introduction to Maven, including the Maven POM and directory structure, and commands for building your first Maven project.

You can install by pasting this command in your terminal:

` sudo apt-get install maven `


#### Step 3: Code editor for java development
In order to be able to code java, you need an editor. As I assume that you are already used to phpstorm to code PHP, Then I think you will love [Intellij](https://www.jetbrains.com/idea/download/#section=linux) because of it's full of features, simple, neat and clean from the same Brand as phpstorm.

On Ubuntu?
IntelliJ IDEA is also available as a snap package. If you’re on Ubuntu 16.04 or later, you can install IntelliJ IDEA from the command line.

` sudo snap install intellij-idea-community --classic `

or

` sudo snap install intellij-idea-ultimate --classic `

If Intellij is not for you then I have got you covered you can install [Eclipse](https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2020-09/R/eclipse-inst-jre-linux64.tar.gz) another great editor for java.


#### Step 4: Spring Initializr
If you’re wondering how to use start.spring.io or what features are available, this section is for you! You’ll find the various ways you can interact with the service and get a better insight at what you can do with it.

The service allows you to generate Spring Boot projects quickly. You can customize the project to generate: the build system and packaging, the language, the packaging, the coordinates, the platform version and, finally, the dependencies to add to the project. Most dependencies available on start.spring.io are Spring Boot starters which is the recommended way to add dependencies to a Spring Boot application.

**Getting Started**

Let’s create a project and discover the various options that you can use to tune it. Go to [start.spring.io](https://start.spring.io), change the Group field from "com.example" to "com.coronavirus", change the Artifact from demo to "tracker", change the Name to "Coronavirus tracker", for the description you can write whatever you want and put the focus in the Dependencies field below. Click on the "add dependency" in the top right corner and type and add the "Spring web", "ThymeLeaf" and "Spring boot devTools" dependencies.

**Your browser should now be in this state:**


![](springInitializr.png)

**Ok let's go through every option on this website.**

- Project: It defines the kind of project. We can create either Maven Project or Gradle Project. We will create a Maven Project throughout the exercise.

- Language: Spring Initializr provides the choice among three languages Java, Kotlin, and Groovy. Java is by default selected.

- Spring Boot: Which Spring Boot version to use. For this exercise we are going to use 2.3.4.

- Group: Group the root package name to use.

- Artifact: Artifact is the name of the project/application.

- Name: Display name of the project that also determines the name of your Spring Boot application. For instance, if the name of your project is my-app, the generated project will have a MyAppApplication class

- Description: description of the project

- Package Name: root package of the project. If not specified, the value of the Group attribute is used

- Packaging: project packaging (as referred by the concept of the same name in Apache Maven). start.spring.io can generate jar or war projects

- Spring boot: the spring boot version to use

- Java: We can select the JVM version which we want to use. We will use Java 11 version throughout the exercise.

- Add Dependencies: Dependencies are the collection of artifacts that we can add to our project.

**Now click on the Generate button and it will download the initial project files.**

#### Step 5: Getting started with exercise

After downloading the initial project files, Extract it and open it in Intellij. After opening it in Intellij, you will see that Maven is creating and downloading all the initial files and dependencies for you.

**It should look like this:**

![](initial-files.png)

**Make sure that your Project bytecode version is 11 in your editor settings and project's version is 11 and also in your pom.xml file**

Today we are going to build an application that fetches data from a source, maybe your thinking about API but no today I want it to do it a little different. We are going to fetch all our data from a github account from [Center for Systems Science and Engineering (CSSE) at Johns Hopkins University](https://github.com/CSSEGISandData/COVID-19). It is updated daily.

#### Step 6: Let's start with coding enough with theory and explanation
Create a package called "services" by right clicking on com.coronavirus.tracker. Now inside that package create a new class called "CoronaVirusService". It is the service that is going to fetch all the data and when our application loads it is going to send a call to this [URL](https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv).

Inside your CoronaVirusService class. Create two properties:

```
    private static String CORONA_VIRUS_DATA_URL = "https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv";

    private List<LocationStats> allStats = new ArrayList<>();
```

For the ArrayList create also the getter which returns the allStats.
