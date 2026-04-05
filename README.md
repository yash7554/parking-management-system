# Parking Management System

A Spring Boot REST API for managing real-time parking slot assignments.

Setup Instructions
1. Database: Create a MySQL database named `parking_db`.
2. Table: Run the following SQL:
sql
CREATE TABLE parking_slot (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    slot_number VARCHAR(10),
    is_occupied BOOLEAN DEFAULT FALSE,
    vehicle_number VARCHAR(20),
    entry_time DATETIME
);
INSERT INTO parking_slot (slot_number, is_occupied) VALUES ('A1', false), ('A2', false), ('A3', false);

1.To Park a Vehicle
URL: /api/parking/park

Method: POST

Params: vehicleNumber (String)

Example: http://localhost:8080/api/parking/park?vehicleNumber=MH12AB1234

2.To Unpark a Vehicle
URL: /api/parking/unpark/{vehicleNumber}

Method: POST

Example: http://localhost:8080/api/parking/unpark/MH12AB1234
