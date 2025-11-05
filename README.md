# 🧩 Restful Booker API Testing Project

This repository contains a complete **API testing project** for the RESTful **Booker API** using **Postman** and **Newman**. It demonstrates automated API testing, dynamic data generation, environment management, and HTML reporting for professional-level test documentation.

## 📋 Project Overview

The Booker API project showcases professional **API testing skills**, including:

- Designing and executing CRUD operations (Create, Read, Update, Partial Update, Delete).  
- Using **environment variables** for dynamic and reusable test data.  
- Writing **pre-request scripts** to generate random data (first name, last name, total price, deposit status, booking dates, additional needs).  
- Creating **test scripts** for validation of response data, status codes, and business logic.  
- Automating tests with **Newman CLI** and generating HTML reports to visualize results.  
- Handling multiple HTTP response codes such as `200`, `400`,`401`, `403`, `404`, `405`,`500` and unexpected codes.

## 🧠 Test Scope

### 🔹 Covered Endpoints

#### **1. Authentication**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/auth` | **POST** | Generates an authentication token using valid credentials. The token is saved as `{{token}}` for subsequent requests. |

**Test Includes:**
- Valid token creation validation.  
- Invalid credentials handling.  
- Token environment variable storage.

#### **2. View All Bookings**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking` | **GET** | Retrieves all existing booking IDs from the server. |

**Test Includes:**
- Verifies successful 200 OK response.  
- Ensures returned data structure is valid.  
- Handles 404 or 405 responses gracefully.

#### **3. Create Booking**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking` | **POST** | Creates a new booking using dynamically generated data. |

**Pre-Request Script:**
- Randomizes values for name, total price, and booking dates using `{{$randomFirstName}}`, `{{$randomLastName}}`, and `moment.js`.  
- Stores data as environment variables for later verification.

**Test Includes:**
- Confirms booking creation success and saves `booking_id`.  
- Validates all booking field values against expected environment data.  
- Handles 400 (Invalid Input), 404 (Endpoint Not Found), and unexpected status codes.

#### **4. Get Booking by ID**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking/{{booking_id}}` | **GET** | Retrieves booking details for the specified `booking_id`. |

**Test Includes:**
- Confirms booking details match expected data.  
- Verifies correct response structure and types.  
- Handles invalid or non-existent IDs.

#### **5. Update Booking (Full Update)**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking/{{booking_id}}` | **PUT** | Performs a full update on an existing booking. Requires valid token authentication. |

**Test Includes:**
- Confirms successful update (200 OK).  
- Verifies all updated fields in response.  
- Updates environment variables accordingly.  
- Handles 400,401, 403, 404,405 error codes.

#### **6. Partial Update Booking**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking/{{booking_id}}` | **PATCH** | Partially updates selected fields (e.g., first name, last name). Requires authentication. |

**Test Includes:**
- Validates partial update success and correct field modification.  
- Ensures non-updated fields remain unchanged.  
- Handles invalid token or missing authorization cases.

#### **7. Delete Booking**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/booking/{{booking_id}}` | **DELETE** | Deletes an existing booking using the stored booking ID. Requires authentication. |

**Test Includes:**
- Confirms booking deletion (status 201 or 200 depending on API).  
- Verifies subsequent GET request returns “Not Found”.  
- Handles invalid token, missing token, or non-existent booking ID.

#### **8. Health Check**
| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/ping` | **GET** | Validates if the RESTful Booker API is up and responding. |

**Test Includes:**
- Confirms a `201` response for successful health check.  
- Returns a descriptive message for 404 (invalid endpoint).  
- Displays custom message for any unexpected status code.

## 📊 HTML Report

After running the tests with Newman, a detailed HTML report is generated in the `/Report/` directory.  
The report includes:
- Test execution results (passed/failed)  
- Response times  
- Assertions summary  
- Error logs (if any)

### 🔹 Key Testing Areas

- ✅ Request & Response validation  
- ✅ Status code verification (`200`, `400`, `403`, `404`, `405`)  
- ✅ Dynamic data generation using environment variables  
- ✅ Pre-request scripts for random data  
- ✅ Test scripts/assertions for data & business logic  
- ✅ Automated HTML reporting with Newman

## 📂 Folder Structure

| Folder / File | Description |
|---------------|-------------|
| `Collection/restfulbookercollection.json` | Postman collection containing all API requests |
| `Environment/test_booking.postman_environment.json` | Postman environment file with variables |
| `Report/restful-booker-api-testing-2025-11-05-18-45-02-920-0.html` | Newman HTML test execution report |
| `README.md` | Project documentation |

## 🧪 Test Deliverables

- ✅ Postman Collection  
- ✅ Postman Environment File  
- ✅ Newman HTML Report  
- ✅ Automated Test Scripts (Pre-request & Test Scripts)

## 📈 Key Highlights

- Designed and automated **CRUD operations** with Postman  
- Generated dynamic test data (names, prices, booking dates, additional needs)  
- Verified responses with **assertions** on data, status codes, and logic  
- Executed automated tests using **Newman CLI**  
- Generated **HTML reports** for professional visualization of test results  
- Handled multiple HTTP response codes and error scenarios

## 👤 Author / Contact

**A.B.M. Mahmudul Hasan (Soumik)**  
📧 Email: [soumikhasan000@gmail.com](mailto:soumikhasan000@gmail.com)  
🔗 LinkedIn: [https://www.linkedin.com/in/a-b-m-mahmudul-hasan-37907133b/](https://www.linkedin.com/in/a-b-m-mahmudul-hasan-37907133b/)
