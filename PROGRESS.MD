# Development Progress — Paused Sept 20, 2026

## ✅ Completed (Phase 1 — Front-End Design)
- Maven project setup (Java 21, Jakarta EE 11)
- Jetty 12 EE11 configuration
- JSF 4.1 + PrimeFaces 16 integration
- AdminLTE custom layout (sidebar, header, main, footer)
- 7 static pages:
    - Dashboard
    - Attendance
    - Employees
    - Attendance Report
    - Analytics (CSS-only charts)
    - Settings (CSS-only toggle switches)
    - Logout (standalone page)
- README.md
- Design system (12px base, color palette)

## 🚧 Next Tasks (Sept 25)

### Phase 2 — Backing Beans & Data Binding
1. **Create beans package** `src/main/java/sandbox/com/ph/bean/`
2. **DashboardBean** — KPI values, recent logs
3. **AttendanceBean** — Time in/out, today's log
4. **EmployeeBean** — Employee list, CRUD actions
5. **ReportBean** — Filter params, report data
6. **AnalyticsBean** — Chart data
7. **SettingsBean** — Company info, preferences

### Phase 3 — Persistence (When Ready)
1. JPA entities (Employee, AttendanceLog, Department)
2. persistence.xml config
3. Database setup (MariaDB / MySQL)
4. JPA repositories / DAOs

## 📝 Notes
- PrimeFaces components are not yet integrated (still pure HTML/CSS)
- SweetAlert2 WebJar is in pom.xml but not yet used
- AI plugin in IntelliJ — not yet set up (Ollama or LM Studio)

## 🔗 Quick Links
- Local URL: http://localhost:8090/admin-template/
- Context path: /admin-template
- Port: 8090
- Maven command: `mvn jetty-ee11:run`

## 🎯 First Task on Sept 25
Create `DashboardBean.java` and bind the KPI values
in `dashboard.xhtml` using `#{dashboardBean.totalEmployees}`.