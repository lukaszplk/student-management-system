# Student Management System

A comprehensive Java Swing application for managing students, courses, grades, and attendance with client-server architecture.

![Java](https://img.shields.io/badge/Java-17+-blue)
![Maven](https://img.shields.io/badge/Maven-3.x-orange)
![Swing](https://img.shields.io/badge/GUI-Swing-green)

## Features

### Student Management
- Add and remove students
- Browse through student records
- Track student's field of study (kierunek)

### Course Management
- Create and delete courses
- Assign courses to students
- Track course hours

### Grade Management
- Add grades for students per course
- View all grades for a student

### Attendance Tracking
- Record attendance for each course
- View attendance history

### Reporting
- Generate student reports
- Export data

### Client-Server Architecture
- TCP socket communication
- Real-time server status monitoring

## Project Structure

```
student-management-system/
├── zaliczenie_main/          # Client application
│   └── src/main/java/
│       ├── Klasy/            # Domain models & GUI windows
│       │   ├── Student.java
│       │   ├── Kurs.java (Course)
│       │   ├── Wykladowca.java (Lecturer)
│       │   ├── Osoba.java (Person - base class)
│       │   ├── MainWindow.java
│       │   └── *Okno.java (Dialog windows)
│       ├── Listeners/        # Event handlers
│       └── Threads/          # Background tasks
│
└── zaliczenie_serwer/        # Server application
    └── src/main/java/
        └── Klasy/
            └── Serwer.java
```

## Class Hierarchy

```
Osoba (Person)
├── Student
│   ├── kierunekStudenta (field of study)
│   ├── listaKursow (courses)
│   └── listaZadan (tasks)
└── Wykladowca (Lecturer)

Kurs (Course)
├── nazwaKursu (name)
├── iloscGodzin (hours)
├── listaOcen (grades)
└── listaObecnosci (attendance)
```

## Build & Run

### Prerequisites
- Java 17 or higher
- Maven 3.x

### Build

```bash
# Build client
cd zaliczenie_main
mvn clean package

# Build server
cd ../zaliczenie_serwer
mvn clean package
```

### Run

```bash
# Start server first
cd zaliczenie_serwer
mvn exec:java

# Then start client
cd ../zaliczenie_main
mvn exec:java
```

## GUI Features

| Window | Function |
|--------|----------|
| MainWindow | Main dashboard with all controls |
| nowyStudentOkno | Add new student dialog |
| UsunStudentaOkno | Remove student dialog |
| UtworzKursOkno | Create course dialog |
| UsunKursOkno | Delete course dialog |
| DodajOceneOkno | Add grade dialog |
| PokazOcenyOkno | View grades dialog |
| DodajObecnoscOkno | Add attendance dialog |
| PokazObecnosciOkno | View attendance dialog |

## Technologies

- **Java Swing** - GUI framework
- **Java Sockets** - Client-server communication
- **Maven** - Build management
- **NetBeans** - IDE (form designer)

## Screenshots

Main window features:
- Student details display (name, surname, field of study)
- Navigation through students
- Buttons for all CRUD operations
- Server communication panel
- Report generation

## License

MIT License
