# University Management System - DFD Diagrams

This document summarizes the DFDs created for the University Management System. Images have been saved in the project directory under the `dfd diagrams` folder.

## Level 0: Context Diagram
A high-level view showing the Admin interacting with the University Management System.

![Level 0 PNG](dfd%20diagrams/Level_0_Context_Diagram.png)

```mermaid
graph TD
    A[Admin] -- "Student/Teacher Data" --> S[University System]
    A -- "Marks/Fees Info" --> S
    S -- "Confirmations" --> A
    S -- "Reports/Receipts" --> St[Student]
    S -- "Schedules/Leave" --> T[Teacher]
```

---

## Level 1: Functional DFD
Breaking down the system into core modules like Login, Student/Teacher Profiles, Academics, Fees, and Leave.

![Level 1 PNG](file:///d:/University-main/dfd%20diagrams/Level_1_Functional_DFD.png)

```mermaid
graph TD
    subgraph Stores
        D1[(Student DB)]
        D2[(Teacher DB)]
        D3[(Academic DB)]
        D4[(Fee DB)]
    end

    A[Admin] -- "Data" --> P1[1.0 Registration]
    P1 -- "Save" --> D1
    P1 -- "Save" --> D2

    A -- "Marks" --> P2[2.0 Exam Mgmt]
    P2 -- "Store" --> D3

    A -- "Apply Fee" --> P3[3.0 Fee Mgmt]
    P3 -- "Save" --> D4

    A -- "Process Leave" --> P4[4.0 Leave Mgmt]
```

---

## Level 2: Student Management
Detailed view of the student registration and update process.

![Level 2 PNG](file:///d:/University-main/dfd%20diagrams/Level_2_Student_Management_DFD.png)

```mermaid
graph TD
    A[Admin] -- "New Student" --> P1.1[1.1 Input Form]
    P1.1 -- "Generate ID" --> P1.2[1.2 Roll No Assignment]
    P1.2 -- "Write" --> D1[(Student DB)]
    A -- "Edit" --> P1.3[1.3 Update Record]
    P1.3 -- "Update" --> D1
```

> [!TIP]
> All diagrams are also available as PNG files in the project folder: [dfd diagrams](file:///d:/University-main/dfd%20diagrams)
