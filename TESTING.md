# Testing Report

## Overview
This document outlines the testing process for the Group 2 Full-Stack Application. It includes test cases, expected vs. actual results, and any bugs or issues found during testing.

Therefore Charles, please follow the testing process documentation outlined below. 

---

## Test Cases

### API Testing
| **Test Case**              | **Endpoint**               | **Request**                                                                 | **Expected Result**                                                                 | **Actual Result**                                                                 | **Status**  |
|----------------------------|---------------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------|
| User Registration          | `POST /api/auth/register` | `{ "email": "user@example.com", "password": "password123" }`                | `201 Created` with message: "Registration successful. Please verify your email." | `201 Created` with message: "Registration successful. Please verify your email." | ✅ Passed   |
| User Login                 | `POST /api/auth/login`    | `{ "email": "user@example.com", "password": "password123" }`                | `200 OK` with JWT token                                                          | `200 OK` with JWT token                                                         | ✅ Passed   |
| Forgot Password            | `POST /api/auth/forgot-password` | `{ "email": "user@example.com" }`                                           | `200 OK` with message: "Password reset email sent."                              | `200 OK` with message: "Password reset email sent."                             | ✅ Passed   |
| Invalid Login              | `POST /api/auth/login`    | `{ "email": "invalid@example.com", "password": "wrongpassword" }`           | `401 Unauthorized` with error message                                           | `401 Unauthorized` with error message                                          | ✅ Passed   |
| Profile Retrieval          | `GET /api/users/profile`  | **JWT Token Required**                                                     | `200 OK` with user profile data                                                  | `200 OK` with user profile data                                                 | ✅ Passed   |

---

### Frontend Testing with Fake Backend
| **Feature**                | **Test Case**                                                                 | **Expected Result**                                                                 | **Actual Result**                                                                 | **Status**  |
|----------------------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------|
| Login Page                 | Enter valid credentials and click "Login".                                   | User is redirected to the dashboard.                                              | User is redirected to the dashboard.                                             | ✅ Passed   |
| Registration Page          | Enter valid details and click "Register".                                    | User sees a success message and is prompted to verify their email.                | User sees a success message and is prompted to verify their email.               | ✅ Passed   |
| Error Handling             | Enter invalid credentials on the login page.                                 | User sees an error message: "Invalid email or password."                          | User sees an error message: "Invalid email or password."                         | ✅ Passed   |
| Profile Update             | Update profile details and save.                                             | User sees a success message: "Profile updated successfully."                      | User sees a success message: "Profile updated successfully."                     | ✅ Passed   |

---

### Bugs or Issues Found
| **Bug ID** | **Description**                                                                 | **Steps to Reproduce**                                                                 | **Expected Result**                                                                 | **Actual Result**                                                                 | **Status**  |
|------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------|
| BUG-001    | Password reset email not sent for invalid email addresses.                     | 1. Send a password reset request with an invalid email.                              | Error message: "Email not found."                                                  | No response or error message.                                                    | ❌ Open     |
| BUG-002    | Profile update fails when no JWT token is provided.                            | 1. Attempt to update the profile without a valid JWT token.                          | Error message: "Unauthorized."                                                    | Error message: "Unauthorized."                                                   | ✅ Resolved |

---

## Steps to Reproduce Bugs
### BUG-001: Password Reset Email Not Sent
1. Open Postman and send a `POST` request to `/api/auth/forgot-password`.
2. Use an invalid email address in the request body.
3. Observe that no error message or response is returned.

---

## Notes
- All tests were conducted using **Postman** for API testing and the Angular development server for frontend testing.
- The fake backend was enabled during initial frontend testing, and the real API was used for final testing.

---

## Conclusion
The application passed most test cases successfully. A few minor bugs were identified and reported to the development team for resolution.
