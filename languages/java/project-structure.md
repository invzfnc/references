> You could follow maven's standard project layout. You don't have to actually use maven, but it would make the transition easier in the future, if necessary. Plus, other developers will be used to seeing that layout, since many open sources projects are laid out this way. [source](https://stackoverflow.com/questions/210567/package-structure-for-a-java-project)

> Apache Maven is a build tool for Java projects. Using a project object model (POM), Maven manages a project's compilation, testing, and documentation. [source](https://maven.apache.org/)

[Apache Maven's Standard Directory Layout](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)

```
myproject/
|_ src/
  |_ main/
    |_ java/
	  |_ com/
	    |_ example/
	      |_ myproject/
	        |_ Main.java
    |_ resources/
  |_ test/
    |_ java/
      |_ com/
        |_ example/
          |_ myproject/
            |_ MainTest.java
|_ target/ (or build/ for Gradle)
|_ pom.xml (for Maven)
|_ build.gradle (for Gradle)
|_ README.md
|_ .gitignore
```