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
Ok let's go through every option on this website.
If you’re wondering how to use start.spring.io or what features are available, this section is for you! You’ll find the various ways you can interact with the service and get a better insight at what you can do with it.

The service allows you to generate Spring Boot projects quickly. You can customize the project to generate: the build system and packaging, the language, the packaging, the coordinates, the platform version and, finally, the dependencies to add to the project. Most dependencies available on start.spring.io are Spring Boot starters which is the recommended way to add dependencies to a Spring Boot application.

**Getting Started**

Let’s create a project and discover the various options that you can use to tune it. Go to [start.spring.io](https://start.spring.io), change the Group field from "com.example" to "com.coronavirus", change the Artifact from demo to "tracker", change the Name to "Coronavirus tracker", for the description you can write whatever you want and put the focus in the Dependencies field below. Click on the "add dependency" in the top right corner and type and add the "Spring web", "ThymeLeaf" and "Spring boot devTools" dependencies.

Your browser should now be in this state:

![](springInitializr.png)

Now click on the Generate button and it will download the initial project files.
