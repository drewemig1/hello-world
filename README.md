# hello-world
my first repo

Do items 1–6 in order and build one small project through all of them. Use Git, write a Java program, build it with Maven, turn it into a Spring Boot REST service, and add JUnit/Mockito tests. A single project you keep extending teaches more than six separate tutorials.

Recommended Order and Why It Changed
Rank
Technology
Change from your list
Why
1
Command line & Git/GitHub
—
You need it to clone the monorepo
2
Java fundamentals
—
The language of the whole codebase
3
Maven
—
Needed to build anything
4
Spring Framework & Spring Boot
—
The main framework
5
REST APIs, HTTP & JSON/Jackson
— (study alongside #4)
Spring's REST guides teach both together
6
JUnit 5 & Mockito
—
Merge requests need tests; start writing them early
7
SQL + MongoDB
—
The main data store
8
Docker
Moved up from 9
Lets you run Mongo, Kafka and Elasticsearch locally
9
Kafka
Moved down from 8
Much easier with a local Docker-based broker
10
Kubernetes & Helm
—
Deployment target; 300+ charts
11
GitLab CI/CD
Moved up from 16
Your pipelines build images and deploy Helm charts; you'll read pipeline logs from your first merge request
12
Elasticsearch
Moved down from 11
Used by only some services
13
Redis
Moved down from 12
Used by only some services
14
Protocol Buffers
Moved up from 15
Small, self-contained topic
15
Spring Cloud, Resilience4j & microservice patterns
Moved down from 14
Ties the system together; makes sense once you've seen several services
16
Project Reactor / Spring WebFlux
Moved down from 13
Hardest mental shift; used in only some services
Details: Free Resources for Each Technology
1. Command Line Basics & Git/GitHub
The Missing Semester of Your CS Education (MIT) — https://missing.csail.mit.edu/
A free MIT course on the practical tools most programmers are never formally taught: the shell, the command-line environment, editors, debugging, and version control with Git.\[1\] The current edition is "nine 1-hour lectures" taught January 12–23, 2026, during MIT's IAP term, including "Version Control and Git" and "Agentic Coding", with exercises and free YouTube recordings. Instead of making you memorize commands, it builds mental models, such as Git's underlying data model, so you can work out what to do when something breaks.\[2\]
Pro Git book (Scott Chacon & Ben Straub) — https://git-scm.com/book/en/v2
The full book, free online from Git's official site and licensed CC BY-NC-SA 3.0.\[3\]\[4\]\[5\] For a beginner, chapters 1–3 are the core: Getting Started, Git Basics, and Git Branching.\[3\] Later chapters cover remote workflows and internals; come back to them once you're making commits on a team.\[6\]
Git – Learn (git-scm.com) — https://git-scm.com/learn
The official Git learning hub. It links the Pro Git book, short videos for total beginners, and a cheat sheet of the most common commands with diagrams comparing merge and rebase.\[4\] Keep the cheat sheet open while you practise.
GitHub Skills — https://skills.github.com
Free, interactive, hands-on courses run inside real GitHub repositories, recommended in GitHub's own community forum.\[7\] They're useful for practising branches and pull requests. Your repo is on GitLab, where these are called "merge requests", but the concepts carry over directly.


2. Java Programming Language Fundamentals
Java Programming MOOC (University of Helsinki) — https://java-programming.mooc.fi/
A free university course that needs no previous programming knowledge. It runs in two halves, Java Programming I and II, with 7 parts each. Each part takes about 5–20 hours, and every exercise is checked automatically by the "Test My Code" service.\[8\] It covers programming basics, algorithms and object-oriented programming, and later parts introduce Maven and third-party libraries.\[9\] Caveat: the course is now labelled legacy: its content is "no longer updated or maintained" and ECTS credits are no longer offered.\[10\] The fundamentals are still excellent, but it doesn't teach newer features such as var, records or pattern matching. Use dev.java for those.
Learn Java – Dev.java (Oracle's official, current tutorials) — https://dev.java/learn/
Oracle's up-to-date learning path. It's organized as First Steps → Language Basics → Object Oriented Programming → Generics, Lambda, and Pattern Matching → Annotations and Exceptions → Collections and Streams, then moves on to the JVM, virtual threads and JDK tools.\[11\] Those sections line up with exactly what you listed (OOP, generics, collections, streams, exceptions), and they cover modern Java, which matters because the repo runs on both Java 11 and Java 21.
Getting Started with Java – Dev.java — https://dev.java/learn/first-steps/first-java-code/getting-started/
Shows how to install the JDK, write your first class, and understand the compile-and-run cycle. It also points to the in-browser Java Playground, so you can run code before installing anything.\[12\]
The Java™ Tutorials – Learning the Java Language trail (Oracle) — https://docs.oracle.com/javase/tutorial/java/index.html
The classic reference trail covering OOP concepts, language basics, classes and objects, annotations, interfaces and inheritance, and generics. Caveat: Oracle states it was "written for JDK 8" and may not reflect newer releases.\[13\] Use it as a second explanation of OOP topics, not as your main course.


3. Build Tools: Apache Maven
Maven in 5 Minutes (Apache Maven official) — https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html
The official quick start. You install Maven, generate a project with mvn archetype:generate, and build it with mvn package.\[14\] Along the way it explains the standard src/main/java and src/test/java layout, the POM, and how lifecycle phases work: running compile also runs validate, generate-sources and so on.\[14\]\[15\] That's the exact model behind the repo's many pom.xml files.
Maven Getting Started Guide (Apache Maven official) — https://maven.apache.org/guides/getting-started/
A longer, step-by-step guide that Apache describes as both an introduction and a cookbook for first-time users. It answers "How do I make my first Maven project?", "How do I compile my sources?" and similar questions in order.\[16\] Work through it after the 5-minute guide to understand dependencies, plugins and multi-module builds, which are central to a monorepo.


4. Spring Framework & Spring Boot Fundamentals
Spring Academy (official, by the Spring team) — https://spring.academy
Hands-on courses from the team that maintains Spring, with a browser-based lab environment.\[17\] The Spring Blog announced on April 10, 2024 that "Spring Academy Pro will no longer require a paid subscription. It will be available here to everyone who registers a work, vocational, or educational email address." That includes the Spring Framework Essentials and Spring Boot courses. Start with "Building a REST API with Spring Boot" and then take the Spring Certified Professional learning path.\[18\] That path covers dependency injection, configuration, auto-configuration, Spring Data and testing. The courses are free but certification is not: in his newsletter after the change, Spring developer advocate Dan Vega wrote, "If you want to get certified you can still pay the $299."
Spring Guides index (spring.io) — https://spring.io/guides/
Official getting-started guides, most of which take 15–30 minutes, each covering one topic: REST services, consuming REST, data access, messaging, reactive and more. They're current with the latest Spring releases and work as quick building blocks once you know Java.\[19\]
Building a RESTful Web Service (spring.io guide) — https://spring.io/guides/gs/rest-service/
Your first Spring Boot application. In about 15 minutes you generate a project from start.spring.io with Maven, write a @RestController, and return JSON from /greeting. Java 17+ and Maven 3.5+ are required.\[20\]\[21\] It's the quickest way to see dependency injection, auto-configuration and @RestController working together.


5. REST APIs & JSON (with Jackson)
Overview of HTTP – MDN Web Docs — https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview
Mozilla's clear explanation of the HTTP client-server model, proxies, the protocol's basic features, and how requests and responses flow.\[22\] Learn this before REST design so that methods, status codes and headers make sense. (MDN recently moved this page; the URL above is the current one.)
Working with JSON – MDN Learn web development — https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/JSON
Covers JSON's structure and syntax rules.\[23\] The examples are in JavaScript, but the format is the same one Jackson reads and writes in Java services. (This page also moved; use the URL above.)
Intro to the Jackson ObjectMapper (Baeldung) — https://www.baeldung.com/jackson-object-mapper-tutorial
Shows how to turn Java objects into JSON and back with ObjectMapper.writeValue/readValue, and how to configure serialization.\[24\] This is what Spring Boot does automatically behind every @RestController.\[25\] Note that the article now targets jackson-databind 3.x, while older services in the repo probably use Jackson 2.x.\[24\] The concepts are the same but the package names differ.
Consuming a RESTful Web Service (spring.io guide) — https://spring.io/guides/gs/consuming-rest/
The reverse of the REST service guide: your application calls another REST API and maps the JSON response into Java objects.\[26\] Microservices make this kind of service-to-service call constantly.


6. Testing in Java: JUnit 5 and Mockito
JUnit User Guide (official) — https://docs.junit.org/6.1.3/overview.html
The official, comprehensive documentation for annotations (@Test, @BeforeEach, @ParameterizedTest, @Nested), assertions, and running tests from Maven.\[27\] Note: the current release is JUnit 6.1.3, which requires Java 17+ at runtime.\[28\] The repo's JUnit 5 ("Jupiter") tests use the same programming model, so the "Writing Tests" chapters apply directly. If a module is pinned to an older version, check the version-specific guide under docs.junit.org (for example, 5.x).\[29\]
Mockito Series (Baeldung) — https://www.baeldung.com/mockito-series
A free series of articles running from basics (@Mock, @Spy, @Captor, @InjectMocks, when/then, verify, argument matchers, throwing exceptions) to advanced topics (void, final and static methods, ArgumentCaptor).\[30\] Each article is short and example-driven, which makes it a good next step after the JUnit guide. Baeldung also sells a paid "Learn Mockito" course; you don't need it.\[31\]
Mockito and JUnit 5 – Using ExtendWith (Baeldung) — https://www.baeldung.com/mockito-junit-5-extension
Shows exactly how to wire Mockito into JUnit 5 with @ExtendWith(MockitoExtension.class).\[32\] That's the pattern you'll see at the top of many unit-test classes in a Spring codebase.
