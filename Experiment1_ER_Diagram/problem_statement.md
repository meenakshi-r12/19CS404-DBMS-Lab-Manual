# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:

<img width="1536" height="1024" alt="86556b8e-c31c-4d1d-8c0e-42dd41f78176" src="https://github.com/user-attachments/assets/e53f503a-3d38-4f41-8439-f0310ddb4ba3" />


## Entities and Attributes:

- **Patient**: Patient_ID (PK), Name, Age, Gender, Address, Phone, Blood_Group, Date_of_Admission, Disease, Doctor_ID (FK)  
- **Doctor**: Doctor_ID (PK), Name, Specialization, Phone, Email, Department_ID (FK)  
- **Department**: Department_ID (PK), Department_Name, Location  
- **Appointment**: Appointment_ID (PK), Patient_ID (FK), Doctor_ID (FK), Date, Time, Status  
- **Room**: Room_ID (PK), Room_Number, Room_Type, Availability, Patient_ID (FK)  
- **Nurse**: Nurse_ID (PK), Name, Phone, Shift, Department_ID (FK)  
- **Treatment**: Treatment_ID (PK), Patient_ID (FK), Doctor_ID (FK), Diagnosis, Medication, Treatment_Date  
- **Bill**: Bill_ID (PK), Patient_ID (FK), Total_Amount, Payment_Status, Bill_Date

## Relationships and Constraints:

- **Department – Doctor**: One department can have many doctors (1:N), each doctor belongs to exactly one department (Total Participation).  
- **Department – Nurse**: One department can have many nurses (1:N), each nurse works in one department (Total Participation).  
- **Doctor – Patient**: One doctor can treat many patients (1:N), each patient is treated by one doctor (Total Participation).  
- **Patient – Appointment**: A patient can have multiple appointments (1:N), each appointment belongs to one patient (Partial Participation).  
- **Doctor – Appointment**: A doctor can attend multiple appointments (1:N), each appointment is assigned to one doctor (Partial Participation).  
- **Patient – Room**: One patient is admitted in one room (1:1), one room can accommodate one patient at a time (Total Participation).  
- **Patient – Treatment**: One patient can receive multiple treatments (1:N), each treatment is linked to one patient (Partial Participation).  
- **Patient – Bill**: One patient has exactly one bill (1:1), each bill corresponds to one patient (Total Participation).

## Extension (Prerequisite / Billing):

The **Billing** entity is included to manage hospital expenses and patient payments.  
Each **Bill** is uniquely identified by a *Bill_ID* and associated with a specific *Patient_ID*.  
It stores the total amount charged for treatments, room stays, and medical services, along with the payment status (Paid/Unpaid).  
This ensures accurate and traceable financial records for every admitted patient.

## Design Choices:

- The design follows a **centralized patient-centric model**, where the *Patient* entity connects to *Doctor*, *Appointment*, *Treatment*, and *Bill*.  
- **Department** acts as an organizational unit linking *Doctor* and *Nurse*.  
- **Room** is treated as a separate entity to handle hospital bed management efficiently.  
- All **primary keys (PK)** ensure unique identification of records, and **foreign keys (FK)** maintain referential integrity.  
- The model reduces redundancy and ensures smooth data retrieval for patient management, billing, and scheduling operations.

## RESULT

An ER diagram for the **Hospital Management System** was successfully designed.  
It clearly defines all necessary entities, attributes, and relationships required for hospital data management, ensuring efficient handling of patient care, staff organization, and billing operations.

