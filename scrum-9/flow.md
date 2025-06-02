# 🔐 VPC Security Group Communication Flow

```mermaid
graph TD
    OpenVPN["OpenVPN SG<br>Allows: 22, 80, 443 (All Traffic)"]
    ALB["Application Load Balancer SG<br>Allows: 80 (All Traffic)"]

    Frontend["Frontend SG<br>Allows: 22 from OpenVPN<br>3000 from ALB"]
    Attendance["Attendance SG<br>Allows: 22 from OpenVPN<br>8080 from ALB"]
    Employee["Employee SG<br>Allows: 22 from OpenVPN<br>8080 from ALB"]
    Salary["Salary SG<br>Allows: 22 from OpenVPN<br>8080 from ALB"]

    Redis["Redis SG<br>Allows: 22 from OpenVPN<br>6379 from Attendance, Employee, Salary"]
    Postgres["Postgres SG<br>Allows: 22, 5432 from Redis<br>5432 from Attendance"]
    Scylla["Scylla SG<br>Allows: 22 from Redis<br>9042 from Employee<br>9043 from Salary"]

    OpenVPN --> Frontend
    OpenVPN --> Attendance
    OpenVPN --> Employee
    OpenVPN --> Salary
    OpenVPN --> Redis

    ALB --> Frontend
    ALB --> Attendance
    ALB --> Employee
    ALB --> Salary

    Attendance --> Redis
    Employee --> Redis
    Salary --> Redis

    Redis --> Postgres
    Attendance --> Postgres

    Redis --> Scylla
    Employee --> Scylla
    Salary --> Scylla
