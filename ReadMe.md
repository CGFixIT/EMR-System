<h2>EMR-System – Dentist Office Medical Record & Appointment Simulator</h2>


[![Java](https://img.shields.io/badge/language-Java%208%20%7C%20JavaFX-blue)]()
![Build](https://img.shields.io/badge/build-Ant%20%7C%20NetBeans-orange)
<!-- ![Status](https://img.shields.io/badge/status-archived-lightgrey) -->

---


A compact, educational project that demonstrates the fundamentals of a **GUI-based login, patient record, and appointment-scheduling system for a dental office**.  
Originally written for **CS2340 &nbsp;Mini-Project 3** using **Java 8 + JavaFX** and the **NetBeans** build system.

---

## ✨ Features

| Domain | What it Does | Key Classes / Screens |
|--------|--------------|-----------------------|
| Authentication | Username/ID & password prompt that routes to the appropriate portal | `loginGUI.java` |
| Patient Portal | • View personal demographics<br>• See next appointment<br>• Review procedure details | `patientGUI.java`, `patAptGUI.java`, `Patient.java` |
| Dentist Portal | • View daily schedule<br>• Inspect individual appointments & patient info | `dentistGUI.java`, `denAptGUI.java`, `Dentist.java`, `AppointmentList.java` |
| Appointment Mgmt. | CRUD functions: create, list, look-up appointments; tie Dentist + Patient + Procedure | `Appointment.java`, `AppointmentList.java`, `Procedure.java` |
| Flat-File “DB” | All data stored in colon-delimited text files in `miniproject3/`: `Patients.txt`, `Dentists.txt`, `Appointments.txt`, `Procedures.txt` |

---

## 🏗️ Build & Run

### Prerequisites
* **JDK 8** (JavaFX bundled)
* **Apache Ant 1.9+** – or **NetBeans 8.x** (original IDE)

### Clone
```bash
git clone https://github.com/CGFixIT/EMR-System.git
cd EMR-System

Option A – NetBeans
File ▸ Open Project… → select the cloned folder.
Right-click project ➜ Run (NetBeans calls Ant targets automatically).
Option B – Ant (CLI)
bash/batch commands or scripting

# 1) Clean & compile
ant clean jar

# 2) Launch the app (opens the Login GUI)
java -jar dist/EMR-System.jar
If Ant cannot find the four renamed sources, add them to the <srcdir> include pattern inside nbproject/build-impl.xml or keep the original names but list them explicitly.
```
```
🗂 Folder Layout
EMR-System/
│
├── src/miniproject3/
│   ├── Appointment.java
│   ├── AppointmentList.java
│   ├── Dentist.java
│   ├── Patient.java
│   ├── Person.java
│   ├── Procedure.java
│   ├── loginGUI.java
│   ├── dentistGUI.java
│   ├── denAptGUI.java
│   ├── patientGUI.java
│   └── patAptGUI.java
│
├── build/classes/miniproject3/
│   ├── Patients.txt
│   ├── Dentists.txt
│   ├── Appointments.txt
│   └── Procedures.txt
│
├── build.xml                # Ant script (delegates to nbproject/build-impl.xml)
├── nbproject/               # NetBeans metadata
├── manifest.mf              # Populated by NetBeans; used in JAR assembly
└── README.md                # ← you’re reading it
```
<!--
📑 Data File Format
File	Columns (colon : separated)	Example
Patients.txt	PatientID : FirstName : LastName : City : Email : InsuranceCode	P321:Mike:Robbins:Atlanta:miker@example.com:AETNA
Dentists.txt	DentistID : Password : FirstName : LastName : Email : Office#	D201:frank:Frank:Martin:fm@gmail.com:539
Appointments.txt	ApptID : DateTime : DentistID : PatientID	A900:10/15/2016-9am:D201:P321
Procedures.txt	ProcCode : Name : Description : Cost	P114:CleaningExam:TeethCleaning:99.99
<-->
🏎️ Quick Demo
```
$ java -jar dist/EMR-System.jar

1. Login screen appears
2. Enter Dentist ID or Patient ID ➜ Press **Login**
3. Dentist sees a schedule grid (denAptGUI) and can click an appointment to open dentistGUI
4. Patient sees personal dashboard (patientGUI) with upcoming appointment from patAptGUI
```

$ java -jar dist/EMR-System.jar
```
1. Login screen appears
2. Enter Dentist ID or Patient ID ➜ Press **Login**
3. Dentist sees a schedule grid (denAptGUI) and can click an appointment to open dentistGUI
4. Patient sees personal dashboard (patientGUI) with upcoming appointment from patAptGUI
(Insert screenshots in docs/images and embed here for visual reference.)
```
---
⚠ Known Limitations - This was after all a school project but the only thing I spent more than an hour or 2 on learning Java
Hard-coded file paths inside several classes:
```
e.g., Appointment.java uses
C:/Users/Chris/Documents/NetBeansProjects/MiniProject2/build/classes/miniproject2/Appointments.txt
<b>➜ Fix:</B> Replace with a relative path such as ./data/Appointments.txt.
No concurrency control on flat-file writes (single-user demo only).
Tested on JDK 8; Java 11+ not verified (yet)
```
---
🛠 Contributing?
```
Fork → Create Feature Branch (git checkout -b feat/my-feature)
Commit changes with clear messages
Push → Open a Pull Request
Good First Issues
Migrate to SQLite via JDBC
Remove hard-coded absolute paths
Upgrade to Java 17 LTS with OpenJFX
Add JUnit tests & CI workflow
```

📜 License
MIT License – see LICENSE (pending)

<hr>

🙏 Acknowledgements
Developed by Chris Grady for an old school project
Inspired by typical electronic medical/dental record workflows.
Flat-file persistence idea adapted from course lecture examples.
This project is provided “as is” for educational purposes only. Do NOT use in production or for real patient data.
```
https://x.com/cgfixit
https://bit.ly/CGpsyclaw
```
