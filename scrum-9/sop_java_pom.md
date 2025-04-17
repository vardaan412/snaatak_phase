```markdown
# 📘 SOP: Java | SOP's for pom.xml

![image](https://github.com/user-attachments/assets/890340a1-ed5e-4add-bdbb-3c49bd099890) 

| 🗓️ Created     | 🔖 Version | ✍️ Author         | 💬 Comment          | 👀 Reviewer |
|----------------|------------|------------------|---------------------|-------------|
| 17-04-2025     | V1         | Vardaan Saxena   | Internal Review     | Pritam      |

---

## 📚 Table of Contents

1. [📌 Intro](#intro)  
2. [❓ Why pom.xml?](#why-pomxml)  
3. [📖 What is pom.xml?](#what-is-pomxml)  
4. [🧰 Pre-requisites](#pre-requisites)  
5. [⚙️ Install Maven](#install-maven)  
6. [🚀 Create a Maven Project](#create-a-maven-project)  
7. [🛠️ Understand the pom.xml File](#understand-the-pomxml-file)  
8. [➕ Add Dependencies to pom.xml](#add-dependencies-to-pomxml)  
9. [⚙️ Build and Test the Project](#build-and-test-the-project)  
10. [📋 Best Practices](#best-practices)  
11. [🧯 Troubleshooting](#troubleshooting)  
12. [🔗 References](#references)  
13. [📇 Contacts](#contacts)  
14. [🧾 Conclusion](#conclusion)

---

## 📌 Intro <a id="intro"></a>

This SOP explains the **step-by-step process** of creating and managing a `pom.xml` file for Java projects using Maven.

---

## ❓ Why pom.xml? <a id="why-pomxml"></a>

- 🔹 Central configuration for Java projects  
- 🔹 Handles dependencies, plugins, builds, and reports  
- 🔹 Easy integration with CI/CD and IDEs like IntelliJ, Eclipse  

---

## 📖 What is pom.xml? <a id="what-is-pomxml"></a>

`pom.xml` (Project Object Model) is the **core configuration file for a Maven-based Java project**. It contains:

- Project metadata  
- Dependency declarations  
- Build plugins  
- Configuration settings

---

## 🧰 Pre-requisites <a id="pre-requisites"></a>

Ensure the following are installed:

- ✅ Java (JDK 11+)  
- ✅ Apache Maven  
- ✅ IDE (IntelliJ / VS Code / Eclipse - optional)

Install JDK:

```bash
sudo apt update
sudo apt install openjdk-11-jdk -y
java -version
```

Install Maven:

```bash
sudo apt install maven -y
mvn -version
```

---

## ⚙️ Install Maven <a id="install-maven"></a>

Already covered above. Confirm with:

```bash
mvn -version
```

---

## 🚀 Create a Maven Project <a id="create-a-maven-project"></a>

Use this command:

```bash
mvn archetype:generate -DgroupId=com.opstree.sample -DartifactId=demo-project -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

Navigate into project:

```bash
cd demo-project
```

It will auto-generate a `pom.xml` file.

---

## 🛠️ Understand the pom.xml File <a id="understand-the-pomxml-file"></a>

Basic structure:

```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.opstree.sample</groupId>
  <artifactId>demo-project</artifactId>
  <version>1.0-SNAPSHOT</version>
</project>
```

---

## ➕ Add Dependencies to pom.xml <a id="add-dependencies-to-pomxml"></a>

Example: Add JUnit for testing

```xml
<dependencies>
  <dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.13.2</version>
    <scope>test</scope>
  </dependency>
</dependencies>
```

---

## ⚙️ Build and Test the Project <a id="build-and-test-the-project"></a>

Build the project:

```bash
mvn clean install
```

Run tests:

```bash
mvn test
```

---

## 📋 Best Practices <a id="best-practices"></a>

- 🔸 Pin versions for all dependencies  
- 🔸 Use `properties` for common version control  
- 🔸 Use plugin management for consistent build lifecycle  
- 🔸 Keep the file organized and commented  

---

## 🧯 Troubleshooting <a id="troubleshooting"></a>

- 🔧 **Missing dependency** — Check groupId/artifactId/version  
- 🔧 **Plugin not executing** — Ensure correct phase and goal  
- 🔧 **Java version mismatch** — Set source/target versions in `build` tag

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.8.1</version>
      <configuration>
        <source>11</source>
        <target>11</target>
      </configuration>
    </plugin>
  </plugins>
</build>
```

---

## 🔗 References <a id="references"></a>

- 🌐 [Maven Docs](https://maven.apache.org/guides/index.html)  
- 🌐 [pom.xml Structure](https://maven.apache.org/pom.html)  
- 🌐 [Maven Repository](https://mvnrepository.com)

---

## 📇 Contacts <a id="contacts"></a>

| 👤 Name           | 📧 Email Address                                |
|------------------|--------------------------------------------------|
| Vardaan Saxena   | vardaan.saxena.snaatak@mygurukulam.co           |

---

## 🧾 Conclusion <a id="conclusion"></a>

With this SOP, developers can now efficiently set up a Java Maven project, manage dependencies using `pom.xml`, and confidently build/test their applications. Having a strong grip on `pom.xml` ensures scalable and maintainable project structures across teams and environments.
```
