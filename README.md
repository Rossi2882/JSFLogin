# JSF Login Application

A Java web application built with **JavaServer Faces (JSF)** that implements a simple user login functionality with server-side validation and session management.

---

## ✨ Features

- Login form built using JSF (Facelets + Managed Beans)
- Server-side authentication (hardcoded users or Database-driven)
- Session management to track logged-in users
- Redirects to welcome dashboard upon successful login
- Error messages for incorrect credentials
- Basic logout functionality

---

## 🛠️ Prerequisites

- Java 8+ (JDK)
- Servlet container / application server (e.g., Tomcat 9+, WildFly, GlassFish)
- Maven (optional) or manual inclusion of:
  - JSF libraries (Mojarra or MyFaces)
  - JDBC driver (if using database-based authentication)

---

## 📦 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Rossi2882/JSFLogin.git
cd JSFLogin
```

### 2. Configure Authentication Source

#### Option A: In‑Memory (Hardcoded)
Edit the managed bean (e.g., `LoginBean`) to update valid usernames and passwords.

#### Option B: Database‑Driven
1. Create a table in your DB (e.g., `users` with `username`, `password`).
2. Update `LoginBean` or DAO to query the DB using JDBC.
3. Adjust connection settings accordingly.

### 3. Set Up JSF Libraries

Ensure your `pom.xml` (if using Maven) includes:
```xml
<dependency>
  <groupId>javax.faces</groupId>
  <artifactId>javax.faces-api</artifactId>
  <version>2.3</version>
</dependency>
<dependency>
  <groupId>org.glassfish</groupId>
  <artifactId>javax.faces</artifactId>
  <version>2.3.0</version>
</dependency>
```

Or manually place JSF `.jar` files into `WEB-INF/lib`.

### 4. Build & Deploy

- Maven:
  ```bash
  mvn clean package
  ```
  Deploy the generated `.war` to your server (`webapps/` in Tomcat).

- Manual:
  - Compile `.java` files
  - Copy `.class`, `.xhtml`, and library files into your server’s `webapps/JSFLogin/WEB-INF/`

### 5. Run the Application

- Start your server.
- Visit `http://localhost:8080/JSFLogin/`
- Log in using the configured credentials.
- You should be redirected to a welcome page.
- Use the “Logout” button to end the session.

---

## 🧭 Project Structure

```
src/
├── main/
│   ├── java/
│   │   ├── beans/         # LoginBean, UserBean, etc.
│   │   └── dao/           # (Optional) database logic
│   └── webapp/
│       ├── WEB-INF/
│       │   └── web.xml
│       └── *.xhtml        # login.xhtml, welcome.xhtml, error.xhtml
└── pom.xml (if Maven)
```
