[!IMPORTANT]
This document unifies user stories for Admin, Doctor, and Patient roles.
Each story defines a specific functional goal within the Smart Clinic system.
Ensure all workflows maintain data integrity, security, and usability consistency across roles.

🧩 Role: Admin

As an administrator
I need core capabilities to manage users and monitor operations
So that I can ensure system reliability, user control, and compliance.

User Story 1 – Admin Login

As an admin, I want to log into the portal with my credentials, so that I can securely manage the system.

Given I am on the login page  
When I enter valid admin credentials  
Then I should be redirected to the admin dashboard  
And my session should be authenticated securely

User Story 2 – Admin Logout

As an admin, I want to log out of the portal, so that I can end my session securely.

Given I am logged in as an admin  
When I click the logout button  
Then I should be logged out and redirected to the login screen  
And my session should be terminated

User Story 3 – Add Doctor

As an admin, I want to add doctors to the system, so that they can manage appointments.

Given I am on the "Add Doctor" form  
When I submit valid doctor information  
Then the doctor profile should be saved to MySQL  
And be visible in the doctor list

User Story 4 – Delete Doctor Profile

As an admin, I want to delete a doctor's profile, so that I can manage active practitioners.

Given a doctor has no future appointments  
When I click "Delete" on their profile  
Then the record should be removed from the system  
And no appointments should reference that doctor

User Story 5 – View Monthly Appointments

As an admin, I want to run a MySQL stored procedure to get monthly appointment counts, so that I can track platform usage.

Given I have access to the MySQL CLI  
When I run the appointment_stats procedure  
Then I should receive a list of appointment counts grouped by month

🩺 Role: Doctor

As a doctor
I need access to my appointment calendar and patient information
So that I can deliver efficient care and manage my availability.

User Story 1 – Doctor Login

As a doctor, I want to log into the portal, so that I can manage my appointments.

Given I am registered as a doctor  
When I enter valid credentials on the login page  
Then I should be redirected to the doctor dashboard  
And I should see my upcoming schedule

User Story 2 – Doctor Logout

As a doctor, I want to log out of the portal, so that I can protect my session and personal data.

Given I am logged in as a doctor  
When I click the logout button  
Then I should be logged out and redirected to the homepage  
And my session should be terminated

User Story 3 – View Appointment Calendar

As a doctor, I want to view my appointment calendar, so that I can organize my work schedule.

Given I am logged in  
When I navigate to the calendar  
Then I should see a visual representation of my appointments for the day/week/month

User Story 4 – Mark Unavailability

As a doctor, I want to mark specific times as unavailable, so that patients cannot book during those periods.

Given I am logged in  
When I mark certain time slots as unavailable  
Then the system should block those slots from being booked by patients

User Story 5 – View Patient Details

As a doctor, I want to view patient details for each appointment, so that I can be better prepared for consultations.

Given I have scheduled appointments  
When I click on a specific appointment  
Then I should see the patient's name, reason for visit, and basic history

🧍‍♀️ Role: Patient

As a patient
I need the ability to explore, book, and manage appointments
So that I can receive medical care efficiently and securely.

User Story 1 – View Doctors Without Logging In

As a patient, I want to view a list of doctors without logging in, so that I can explore my options before registering.

Given I access the doctor listing page  
When I am not logged in  
Then I should see names, specialties, and contact info of available doctors

User Story 2 – Patient Sign-Up

As a patient, I want to sign up using my email and password, so that I can book appointments.

Given I am on the signup page  
When I submit valid registration details  
Then my account should be created  
And I should be redirected to the login page

User Story 3 – Patient Login

As a patient, I want to log into the portal, so that I can manage my bookings.

Given I have a registered account  
When I enter valid credentials  
Then I should be redirected to my dashboard  
And gain access to appointment management features

User Story 4 – Book Appointment

As a patient, I want to book an hour-long appointment, so that I can consult with a doctor.

Given I am logged in  
When I select a doctor, date, and time  
Then the system should verify availability  
And confirm the booking

User Story 5 – View Upcoming Appointments

As a patient, I want to view my upcoming appointments, so that I can prepare in advance.

Given I am logged in  
When I visit the "My Appointments" section  
Then I should see a list of all upcoming appointments with relevant details
