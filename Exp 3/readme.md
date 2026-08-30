# Experiment 3 – Google App Engine Hello World

## Title
Install Google App Engine. Create Hello World app and other simple web applications using Python/Java.

## Aim
To install Google App Engine, create a Hello World web application, and run simple web applications using Java.

---

## Requirements
| Item | Details |
|------|---------|
| IDE | Eclipse IDE for Java EE Developers |
| Plugin | Google Plugin for Eclipse |
| SDK | Google App Engine Java SDK |
| Language | Java (Servlet) |
| JDK | Java 7 or above |

---

## Introduction
**Google App Engine (GAE)** is a Platform-as-a-Service (PaaS) cloud offering by Google that allows developers to build and host web applications on Google's infrastructure. It supports Java, Python, PHP, and Go. In this experiment, a simple Hello World Java Servlet is created and run on the local GAE development server.

---

## Setup Steps

### 1. Install Google Plugin for Eclipse
- Open Eclipse → **Help → Eclipse Marketplace**
- Search: `Google Plugin for Eclipse`
- Click Install → Accept terms → Finish

### 2. Install Google App Engine SDK
- Download **App Engine Java SDK** from Google Cloud.
- Extract the SDK to a local folder (e.g., `C:\appengine-sdk\`).
- In Eclipse: **Window → Preferences → Google → App Engine**
- Add the SDK location.

### 3. Create a Web Application Project
- **File → New → Web Application Project**
- Project Name: `HelloWorld`
- Package: `com.example`
- Uncheck "Use Google Web Toolkit" (if not needed)
- Click **Finish**

---

## Project Structure
```
HelloWorld/
├── src/
│   └── HelloWorldServlet.java
├── war/
│   ├── index.html
│   └── WEB-INF/
│       ├── appengine-web.xml
│       └── web.xml
```

---

## Source Files

### HelloWorldServlet.java
A Java Servlet that responds to HTTP GET requests and outputs "Hello, world".

### appengine-web.xml
Configures the App Engine application ID, version, and threading model.

### web.xml
Maps the URL pattern `/helloworld` to the `HelloWorldServlet` class.

### index.html
Landing page with a link to the Hello World servlet.

---

## Running Locally
1. Right-click the project → **Run As → Web Application**
2. Eclipse starts the local development server.

### Expected URLs:
- Home page: `http://localhost:8888/`
- Servlet: `http://localhost:8888/helloworld`

---

## Expected Output
When visiting `http://localhost:8888/helloworld` in a browser:
```
Hello, world
```

---

## Files
| File | Description |
|------|-------------|
| `HelloWorldServlet.java` | Java Servlet – outputs Hello World |
| `appengine-web.xml` | App Engine configuration |
| `web.xml` | Web application deployment descriptor |
| `index.html` | Landing page |
| `output.txt` | Simulated server/browser output |

---

## Result
Google App Engine Hello World web application was created using Eclipse and the Java Servlet, and executed successfully on the local development server.
