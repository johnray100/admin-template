# Admin Template — JSF + PrimeFaces

A modern **AdminLTE-inspired** admin dashboard template built with **Jakarta EE 11**, **Jakarta Faces 4.1**, **PrimeFaces 16**, and **Java 21**. Designed for rapid development of enterprise-grade admin panels, dashboards, and CRUD-heavy applications.

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Java](https://img.shields.io/badge/Java-21-blue)
![Jakarta EE](https://img.shields.io/badge/Jakarta%20EE-11-orange)
![JSF](https://img.shields.io/badge/JSF-4.1-blue)
![PrimeFaces](https://img.shields.io/badge/PrimeFaces-16.0.0-green)
![Jetty](https://img.shields.io/badge/Jetty-12.0.38-red)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Tech Stack](#-tech-stack)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [Pages & Routes](#-pages--routes)
- [Design System](#-design-system)
- [Development Workflow](#-development-workflow)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

This template provides a **ready-to-use foundation** for building Jakarta EE web applications with a modern admin UI. It combines:

- **Jakarta Faces (JSF) 4.1** for server-side UI rendering
- **PrimeFaces 16** for rich UI components
- **Custom AdminLTE-style CSS** for the layout (sidebar, header, main, footer)
- **Jetty 12 EE11** embedded server for development
- **CDI (Weld)** for dependency injection
- **JPA (EclipseLink / Hibernate)** for persistence

**Current phase:** Front-end design (static layouts, no backing beans yet).

---

## 🛠 Tech Stack

| Layer | Technology | Version |
|-------|-----------|---------|
| **Language** | Java | 21 |
| **Platform** | Jakarta EE | 11 |
| **Web Framework** | Jakarta Faces (JSF) | 4.1 |
| **UI Library** | PrimeFaces | 16.0.0 |
| **UI Theme** | Custom AdminLTE (hand-written CSS) | — |
| **CDI** | Weld | 6.0.2.Final |
| **Persistence** | JPA + EclipseLink | 3.2.0 / 4.0.2 |
| **Servlet Container** | Jetty (EE11) | 12.0.38 |
| **Build Tool** | Apache Maven | 3.9+ |
| **Logging** | SLF4J + Logback | 2.0.17 / 1.5.18 |
| **Testing** | JUnit 5 | 5.11.0 |
| **Boilerplate** | Project Lombok | 1.18.36 |

---

## ✨ Features

### 🎨 UI / UX
- ✅ **AdminLTE-inspired layout** — fixed sidebar, top navbar, main content, footer
- ✅ **Responsive design** — mobile-friendly (grid collapses gracefully)
- ✅ **Consistent design system** — 12px base font, unified colors, spacing
- ✅ **7 pre-built pages** — Dashboard, Attendance, Employees, Report, Analytics, Settings, Logout
- ✅ **PrimeFaces icons** (`pi pi-*`) integrated
- ✅ **Custom scrollbar** styling (WebKit)
- ✅ **CSS-only charts** — bar chart, donut chart (no external JS library)

### ⚙️ Backend / Runtime
- ✅ **Jakarta EE 11** compatible
- ✅ **CDI-based** architecture (Weld servlet)
- ✅ **JPA ready** — EclipseLink / Hibernate providers
- ✅ **Jetty 12 EE11** embedded development server
- ✅ **Maven WAR packaging** for deployment
- ✅ **WebJar support** for static assets

### 📄 Pages Included
| Page | Route | Status |
|------|-------|--------|
| Dashboard | `/pages/dashboard/dashboard.xhtml` | ✅ Static |
| Attendance | `/pages/attendance/attendance.xhtml` | ✅ Static |
| Employees | `/pages/employee/employee.xhtml` | ✅ Static |
| Attendance Report | `/pages/report/attendance-report.xhtml` | ✅ Static |
| Analytics | `/pages/analytics/analytics.xhtml` | ✅ Static |
| Settings | `/pages/settings/settings.xhtml` | ✅ Static |
| Logout | `/pages/logout.xhtml` | ✅ Static |

---

## 📁 Project Structure

```
admin-template/
├── pom.xml                                    # Maven configuration
├── README.md                                  # This file
├── .gitignore
├── mvnw, mvnw.cmd                             # Maven wrapper
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── sandbox/com/ph/                # Java source (beans, services)
│   │   │
│   │   ├── resources/
│   │   │   ├── META-INF/
│   │   │   │   └── persistence.xml            # (future) JPA config
│   │   │   ├── logback.xml                    # Logging config
│   │   │   └── messages.properties            # i18n messages
│   │   │
│   │   └── webapp/
│   │       ├── WEB-INF/
│   │       │   ├── web.xml                    # JSF + CDI + PrimeFaces config
│   │       │   └── beans.xml                  # CDI activation
│   │       │
│   │       ├── resources/
│   │       │   └── admin/
│   │       │       ├── css/
│   │       │       │   ├── adminlte.min.css
│   │       │       │   ├── customStyle.css
│   │       │       │   └── style.css
│   │       │       └── js/
│   │       │           ├── jquery/
│   │       │           ├── bootstrap/
│   │       │           ├── adminlte.min.js
│   │       │           └── settings.js
│   │       │
│   │       ├── index.xhtml                    # Entry point
│   │       └── pages/
│   │           ├── dashboard/
│   │           │   └── dashboard.xhtml
│   │           ├── attendance/
│   │           │   └── attendance.xhtml
│   │           ├── employee/
│   │           │   └── employee.xhtml
│   │           ├── report/
│   │           │   └── attendance-report.xhtml
│   │           ├── analytics/
│   │           │   └── analytics.xhtml
│   │           ├── settings/
│   │           │   └── settings.xhtml
│   │           └── logout.xhtml
│   │
│   └── test/
│       └── java/                              # Unit tests
│
└── target/                                    # Build output (gitignored)
```

---

## 📋 Prerequisites

Bago mo patakbuhin ang proyekto, siguraduhing mayroon ka ng mga sumusunod:

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| **JDK** | Java 21 | Java 21 (LTS) |
| **Maven** | 3.8+ | 3.9+ |
| **Disk Space** | 500 MB | 1 GB |
| **RAM** | 4 GB | 8 GB |
| **IDE** | IntelliJ IDEA / Eclipse | IntelliJ IDEA Ultimate |
| **Browser** | Chrome / Edge / Firefox | Latest version |

**Optional (para sa AI-assisted development):**
- **Ollama** o **LM Studio** — para sa local AI coding assistance

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/admin-template.git
cd admin-template
```

### 2️⃣ Verify Java Version

```bash
java -version
# Expected output: openjdk version "21.x.x"
```

### 3️⃣ Build the Project

```bash
mvn clean install
```

### 4️⃣ Run with Jetty

```bash
mvn jetty-ee11:run
```

**Note:** Ang plugin prefix ay **`jetty-ee11`** (hindi `jetty`) dahil sa Jetty 12 EE11.

### 5️⃣ Open in Browser

```
http://localhost:8090/admin-template/
```

Dapat kang makakita ng **redirect** patungo sa dashboard page.

### 6️⃣ Stop the Server

Pindutin ang **`Ctrl + C`** sa terminal.

---

## ⚙️ Configuration

### `pom.xml` — Key Configurations

**Jetty plugin (development):**
```xml
<plugin>
    <groupId>org.eclipse.jetty.ee11</groupId>
    <artifactId>jetty-ee11-maven-plugin</artifactId>
    <version>12.0.38</version>
    <configuration>
        <httpConnector>
            <port>8090</port>
        </httpConnector>
        <webApp>
            <contextPath>/admin-template</contextPath>
        </webApp>
    </configuration>
</plugin>
```

**Change the port:** Palitan ang `<port>8090</port>` ng gusto mong port (hal. `8080`).

**Change context path:** Palitan ang `<contextPath>/admin-template</contextPath>`.

### `web.xml` — Key Configurations

| Context Param | Value | Purpose |
|---------------|-------|---------|
| `jakarta.faces.PROJECT_STAGE` | `Development` | Show detailed errors |
| `jakarta.faces.FACELETS_REFRESH_PERIOD` | `2` | Hot reload XHTML (2 sec) |
| `jakarta.faces.STATE_SAVING_METHOD` | `server` | Server-side state |
| `primefaces.THEME` | `saga` | PrimeFaces theme |

### Hot Reload During Development

Ang **Facelets** ay awtomatikong nag-reload kada 2 segundo (dahil sa `FACELETS_REFRESH_PERIOD=2`). Kaya:

1. I-edit ang anumang `.xhtml` file
2. I-save
3. I-refresh ang browser (`Ctrl + F5`)

**Walang kailangang i-restart** ang Jetty.

Para sa **Java code changes**, kailangan mong i-restart ang Jetty (o gumamit ng **JRebel** / **DevTools**).

---

## 🗺 Pages & Routes

Lahat ng pages ay accessible sa ilalim ng `/admin-template/`:

| Page | URL |
|------|-----|
| **Dashboard** | `http://localhost:8090/admin-template/pages/dashboard/dashboard.xhtml` |
| **Attendance** | `http://localhost:8090/admin-template/pages/attendance/attendance.xhtml` |
| **Employees** | `http://localhost:8090/admin-template/pages/employee/employee.xhtml` |
| **Attendance Report** | `http://localhost:8090/admin-template/pages/report/attendance-report.xhtml` |
| **Analytics** | `http://localhost:8090/admin-template/pages/analytics/analytics.xhtml` |
| **Settings** | `http://localhost:8090/admin-template/pages/settings/settings.xhtml` |
| **Logout** | `http://localhost:8090/admin-template/pages/logout.xhtml` |

Ang **sidebar navigation** ay naka-link na sa lahat ng pages.

---

## 🎨 Design System

### Color Palette

| Purpose | Color | Hex |
|---------|-------|-----|
| **Primary** | Blue | `#3b82f6` |
| **Success** | Green | `#28a745` |
| **Warning** | Amber | `#ffc107` |
| **Danger** | Red | `#dc3545` |
| **Info** | Cyan | `#17a2b8` |
| **Sidebar** | Dark Slate | `#343a40` |
| **Background** | Light Gray | `#ecf0f5` |
| **Text Primary** | Dark Slate | `#1f2937` |
| **Text Muted** | Gray | `#6b7280` |

### Typography

| Element | Size | Weight |
|---------|------|--------|
| Base body | `12px` | 400 |
| Page title (h1) | `16px` | 600 |
| Card header | `13px` | 600 |
| Sidebar menu | `12px` | 400 |
| KPI value | `24px` | 700 |
| KPI label | `11px` | 400 (uppercase) |
| Footer | `11px` | 400 |

### Layout Dimensions

| Element | Size |
|---------|------|
| Header height | `50px` |
| Sidebar width | `220px` |
| Footer height | `40px` |
| Content padding | `18px` |

### CSS Class Naming

Sinusunod natin ang **BEM-like** convention:

- **Block:** `.main-header`, `.main-sidebar`, `.card`, `.kpi`
- **Element:** `.card-header`, `.card-body`, `.kpi-label`, `.kpi-value`
- **Modifier:** `.kpi-success`, `.kpi-warning`, `.kpi-danger`, `.btn-primary`

---

## 🔄 Development Workflow

### Adding a New Page

1. **Create the XHTML file** sa `src/main/webapp/pages/<module>/<page>.xhtml`
2. **Copy the layout** mula sa existing page (hal. `dashboard.xhtml`)
3. **Baguhin ang content** sa loob ng `.content-wrapper`
4. **I-update ang sidebar link** sa lahat ng pages (para mag-link sa bagong page)
5. **I-save** at i-refresh ang browser

### Adding a Backing Bean (Future)

```java
package sandbox.com.ph.bean;

import jakarta.enterprise.context.SessionScoped;
import jakarta.inject.Named;
import lombok.Getter;
import lombok.Setter;
import java.io.Serializable;

@Named("dashboardBean")
@SessionScoped
@Getter @Setter
public class DashboardBean implements Serializable {
    private int totalEmployees = 128;
    private int currentlyInside = 42;
    private int lateToday = 6;
    private int absentToday = 9;
}
```

Gamitin sa XHTML:
```xml
<div class="kpi-value">#{dashboardBean.totalEmployees}</div>
```

### Adding PrimeFaces Components

```xml
<p:dataTable value="#{dashboardBean.logs}" var="log">
    <p:column headerText="Employee">#{log.employeeName}</p:column>
    <p:column headerText="Time">#{log.timeStamp}</p:column>
</p:dataTable>
```

### Adding a JPA Entity (Future)

```java
@Entity
@Table(name = "employees")
@Getter @Setter
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    private String employeeId;
    private String firstName;
    private String lastName;
    private String department;
}
```

---

## 🗓 Roadmap

### ✅ Phase 1 — Front-End Design (Current)
- [x] Maven project setup
- [x] Jetty 12 EE11 configuration
- [x] JSF + PrimeFaces integration
- [x] AdminLTE layout (sidebar, header, main, footer)
- [x] 7 static pages (Dashboard, Attendance, Employees, Report, Analytics, Settings, Logout)
- [x] Design system (colors, typography, spacing)

### 🚧 Phase 2 — Backing Beans & Data Binding (In Progress)
- [ ] Create `@Named @ViewScoped` beans for each page
- [ ] Wire static data to beans
- [ ] Form validation with Jakarta Validation
- [ ] PrimeFaces components integration (`p:dataTable`, `p:commandButton`)

### 📋 Phase 3 — Persistence Layer
- [ ] JPA entities (Employee, AttendanceLog, Department)
- [ ] JPA repositories / DAOs
- [ ] Database configuration (MariaDB / MySQL)
- [ ] Schema generation / migration

### 📋 Phase 4 — Business Logic
- [ ] Service layer (`@ApplicationScoped`)
- [ ] Time In / Time Out logic
- [ ] Attendance computation (hours worked, late, overtime)
- [ ] Employee CRUD operations

### 📋 Phase 5 — Reporting & Analytics
- [ ] JasperReports integration for PDF export
- [ ] Excel export (Apache POI)
- [ ] Real chart library (Chart.js or PrimeFaces Charts)
- [ ] Scheduled reports (email)

### 📋 Phase 6 — Security & Auth
- [ ] Login page (custom or Jakarta Security)
- [ ] Role-based access control (Admin, HR, Employee)
- [ ] Session management
- [ ] Password hashing (BCrypt)

### 📋 Phase 7 — Production Ready
- [ ] Logging configuration (Logback)
- [ ] Error pages (404, 500)
- [ ] i18n (English + Filipino)
- [ ] Docker container
- [ ] CI/CD pipeline (GitHub Actions)
- [ ] Deployment documentation (WildFly, Payara)

---

## 🐛 Troubleshooting

### HTTP 503 Service Unavailable

**Sanhi:** FacesServlet hindi nag-initialize.

**Solusyon:**
1. I-check kung may `beans.xml` sa `src/main/webapp/WEB-INF/`
2. I-verify ang JSF implementation (Mojarra) sa `pom.xml`
3. Tingnan ang Jetty logs para sa `ClassNotFoundException`

### NoClassDefFoundError: jakarta/faces/component/NamingContainer

**Sanhi:** JSF API hindi available sa runtime.

**Solusyon:** Palitan ang scope ng `jakarta.faces-api` mula `provided` papuntang `compile`.

### Maven plugin not found: jetty-ee11

**Sanhi:** Maling plugin prefix.

**Solusyon:** Gamitin ang:
```bash
mvn org.eclipse.jetty.ee11:jetty-ee11-maven-plugin:12.0.38:run
```
o i-verify ang plugin sa `pom.xml`:
```xml
<groupId>org.eclipse.jetty.ee11</groupId>
<artifactId>jetty-ee11-maven-plugin</artifactId>
```

### Port 8090 already in use

**Solusyon:** Palitan ang port sa `pom.xml`:
```xml
<httpConnector>
    <port>8091</port>  <!-- bagong port -->
</httpConnector>
```

---

## 🤝 Contributing

Kung gusto mong mag-contribute:

1. **Fork** ang repository
2. **Create a feature branch:** `git checkout -b feature/your-feature`
3. **Commit your changes:** `git commit -m "Add: your feature"`
4. **Push to the branch:** `git push origin feature/your-feature`
5. **Open a Pull Request**

### Commit Message Convention

| Prefix | Purpose |
|--------|---------|
| `feat:` | Bagong feature |
| `fix:` | Bug fix |
| `docs:` | Documentation |
| `style:` | CSS / formatting |
| `refactor:` | Code restructuring |
| `chore:` | Maintenance |

**Halimbawa:**
```
feat: add employee CRUD backing bean
fix: correct sidebar active state on attendance page
docs: update README with Jetty 12 setup
```

---

## 📚 Resources

### Official Documentation
- [Jakarta Faces 4.1 Spec](https://jakarta.ee/specifications/faces/4.1/)
- [PrimeFaces 16 Documentation](https://primefaces.org/showcase/)
- [Jetty 12 Documentation](https://jetty.org/docs/jetty/12/index.html)
- [Jakarta EE 11 Platform](https://jakarta.ee/release/11/)
- [Weld CDI Documentation](https://weld.cdi-spec.org/documentation/)

### Tutorials & References
- [AdminLTE 3 Documentation](https://adminlte.io/docs/3.2/)
- [Baeldung JSF Tutorials](https://www.baeldung.com/jsf)
- [Maven War Plugin](https://maven.apache.org/plugins/maven-war-plugin/)

### Tools
- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- [Ollama (Local AI)](https://ollama.com/)
- [LM Studio (Local AI GUI)](https://lmstudio.ai/)

---

## 📝 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 Admin Template

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 👤 Author

**Admin Template Team**

- 📧 Email: admin@sandbox.com.ph
- 🌐 Website: https://sandbox.com.ph
- 📍 Location: Makati City, Philippines

---

## ⭐ Acknowledgments

- **PrimeFaces** team for the excellent JSF component library
- **AdminLTE** for the design inspiration
- **JetBrains** for IntelliJ IDEA
- **Jakarta EE** community for the platform

---

**Last Updated:** 2026-09-20 · **Version:** 1.0.0 · **Status:** Front-End Design Phase
