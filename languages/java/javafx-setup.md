**Prerequisites**  
Download JavaFX SDK from https://openjfx.io/ or https://gluonhq.com/products/javafx/, extract to folder.

**Compilation**  
```sh
javac  --module-path "\openjfx-17.0.17_windows-x64_bin-sdk\javafx-sdk-17.0.17\lib" --add-modules javafx.controls Test.java
```

**Execution**
```sh
javac  --module-path "\openjfx-17.0.17_windows-x64_bin-sdk\javafx-sdk-17.0.17\lib" --add-modules javafx.controls Test
```

#### Setting up JavaFX in IntelliJ
1. Get JavaFX SDK
	1. Head to https://openjfx.io/openjfx-docs/
	2. "JavaFX and IntelliJ" > "Non-modular from IDE"
	3. Download JavaFX SDK. Extract to somewhere.
2. Add library in IntelliJ
	- Optional? If want template: Create a new JavaFX project, select appropriate Java SDK (Note: Template is only available with subscription)
	- File > Project Structures > Libraries > + > Java > Locate `lib/` folder in downloaded JavaFX SDK > OK > Apply
3. Add VM options - **Not** needed in newer versions (21) of IntelliJ

#### Issues and solutions  
These are some issues I faced during the JavaFX and IntelliJ setup. I'll put the solutions I used to resolve these issues here.  
  
##### Maven Error  
```  
Maven Error: Maven Project Configuration for Module isn't available`  
```  
Locate `pom.xml`, right click, "Add as Maven Project".  
  
##### -source 8  
```  
java: modules are not supported in -source 8`  
```  
Problems tab on the left > right click on error > show quick fix > apply change  
  
##### Class file has wrong version  
```  
java: cannot access javafx.application.Application  
  bad class file: /javafx-sdk-25.0.1/lib/javafx.graphics.jar!/javafx/application/Application.class    class file has wrong version 67.0, should be 65.0    Please remove or make sure it appears in the correct subdirectory of the classpath.```  
Update JDK to latest version. Setup IntelliJ to use latest JDK.  
```

##### JavaFX runtime components are missing  
```  
Error: JavaFX runtime components are missing  
```  
Separate `main` and `start` declarations into separate classes. [source](https://old.reddit.com/r/JavaFX/wiki/common-problems#wiki_how_do_i_fix_.27error.3A_javafx_runtime_components_are_missing.27.3F)  
  
Additionally, edit Run/Debug Configurations and set `App.java` as entry point for easier testing process.
