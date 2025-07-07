---

### **Module: `Frontend (Vue/Ionic)`**

**1. High-Level Summary:**

*   **Purpose:** This document outlines the architecture of the modern, standalone frontend application for the HRMS. This application is built as a Single Page Application (SPA) using Vue.js and the Ionic framework, designed to provide a mobile-first, native-like user experience. It communicates with the Frappe backend via a REST API.
*   **Key Technologies:**
    *   **Vue.js:** The core JavaScript framework for building the user interface.
    *   **Ionic Framework:** A UI toolkit for building high-quality, cross-platform native and web app experiences.
    *   **Vite:** The build tool used for development and production builds.
    *   **Vue Router:** The official router for Vue.js, used for client-side navigation.
    *   **Frappe UI:** A component library and set of utilities for interacting with the Frappe backend.
    *   **Tailwind CSS:** A utility-first CSS framework for styling.

**2. Application Architecture:**

*   **Initialization (`src/main.js`):**
    *   The application is bootstrapped as a standard Vue 3 application.
    *   It initializes and configures the `frappe-ui` library, setting `frappeRequest` as the default resource fetcher. This is the primary mechanism for making API calls to the Frappe backend.
    *   A WebSocket connection is established via `src/socket.js` for real-time communication.
    *   Global state and utilities (like session data, user info, employee data, and date formatting) are made available to all components using Vue's `provide`/`inject` API.
    *   A service worker is registered to handle push notifications and provide offline capabilities, enhancing the PWA (Progressive Web App) experience.
*   **Routing (`src/router/index.js`):**
    *   The application uses `vue-router` to manage all client-side navigation.
    *   Routes are modularized by feature, with separate route files for `attendance`, `leaves`, `claims`, `advances`, and `salary_slips`. This keeps the routing configuration clean and maintainable.
    *   The base path for the application is `/hrms`.
    *   A global navigation guard (`router.beforeEach`) is implemented to handle authentication and authorization. It ensures that only logged-in users who are also registered as `Employee`s can access the application's views.
*   **State Management & Data (`src/data/`):**
    *   The application does not use a formal state management library like Vuex or Pinia. Instead, it uses a "resource" pattern provided by `frappe-ui`.
    *   Files in the `src/data` directory (e.g., `leaves.js`, `claims.js`) define these resources. Each resource is responsible for fetching and caching its own data from the backend.
    *   This approach localizes state management to the feature level, making the application more modular.

**3. Feature-Based Analysis:**

*   **Feature: Leave Management**
    *   **Views:**
        *   `src/views/leave/Dashboard.vue`: The main dashboard for leave-related information.
        *   `src/views/leave/List.vue`: Displays a list of the user's leave applications.
        *   `src/views/leave/Form.vue`: The form for creating and editing leave applications.
    *   **Components:**
        *   `src/components/LeaveRequestItem.vue`: A component for displaying a single leave application in a list.
        *   `src/components/LeaveBalance.vue`: A component for displaying the user's leave balances.
    *   **Data:**
        *   `src/data/leaves.js`: Contains the logic for fetching and managing leave application data from the backend.

*   **Feature: Time and Attendance**
    *   **Views:**
        *   `src/views/attendance/Dashboard.vue`: The main dashboard for attendance-related information.
        *   `src/views/attendance/EmployeeCheckinList.vue`: Displays a list of the user's check-ins.
        *   `src/views/attendance/ShiftRequestForm.vue`: The form for requesting shift changes.
    *   **Components:**
        *   `src/components/AttendanceCalendar.vue`: A calendar view for displaying attendance data.
        *   `src/components/CheckInPanel.vue`: A component for handling employee check-ins.
    *   **Data:**
        *   `src/data/attendance.js`: Contains the logic for fetching and managing attendance data.

*   **Feature: Expense Claims**
    *   **Views:**
        *   `src/views/expense_claim/Dashboard.vue`: The main dashboard for expense claims.
        *   `src/views/expense_claim/List.vue`: Displays a list of the user's expense claims.
        *   `src/views/expense_claim/Form.vue`: The form for creating and editing expense claims.
    *   **Components:**
        *   `src/components/ExpenseClaimItem.vue`: A component for displaying a single expense claim in a list.
        *   `src/components/ExpenseItems.vue`: A component for managing the individual items within an expense claim.
    *   **Data:**
        *   `src/data/claims.js`: Contains the logic for fetching and managing expense claim data.

---
*   **API Interactions:**
        *   **Data Fetching (`src/data/leaves.js`):**
            *   `myLeaves`: Fetches the current user's leave applications by calling `hrms.api.get_leave_applications`.
            *   `teamLeaves`: Fetches leave applications pending the user's approval by calling `hrms.api.get_leave_applications` with the `for_approval=1` parameter.
            *   `leaveBalance`: Fetches the user's leave balances by calling `hrms.api.get_leave_balance_map`.
        *   **Form Handling (`src/views/leave/Form.vue`):**
            *   The form's structure is dynamically fetched using `hrms.api.get_doctype_fields`.
            *   The list of available leave types is fetched via `hrms.api.get_leave_types`.
            *   The designated leave approver and mandatory status are fetched using `hrms.api.get_leave_approval_details`.
            *   Real-time calculation of leave days and balances is performed by calling `hrms.hr.doctype.leave_application.leave_application.get_number_of_leave_days` and `hrms.hr.doctype.leave_application.leave_application.get_leave_balance_on` respectively.
*   **API Interactions:**
        *   **Data Fetching (`src/data/attendance.js`):**
            *   `myAttendanceRequests`: Fetches the current user's attendance requests by calling `hrms.api.get_attendance_requests`.
            *   `myShiftRequests`: Fetches the current user's shift requests by calling `hrms.api.get_shift_requests`.
            *   `teamShiftRequests`: Fetches shift requests pending the user's approval by calling `hrms.api.get_shift_requests` with the `for_approval=1` parameter.
            *   `teamAttendanceRequests`: Fetches attendance requests pending the user's approval by calling `hrms.api.get_attendance_requests` with the `for_approval=1` parameter.
        *   **Dashboard (`src/views/attendance/Dashboard.vue`):**
            *   The dashboard fetches the user's upcoming shifts by calling `hrms.api.get_shifts`.
*   **API Interactions:**
        *   **Data Fetching (`src/data/claims.js`):**
            *   `expenseClaimSummary`: Fetches a summary of the user's claims by calling `hrms.api.get_expense_claim_summary`.
            *   `myClaims`: Fetches the current user's expense claims by calling `hrms.api.get_expense_claims`.
            *   `teamClaims`: Fetches claims pending the user's approval by calling `hrms.api.get_expense_claims` with the `for_approval=1` parameter.
            *   `claimTypesResource`: Fetches the available expense claim types using `hrms.api.get_expense_claim_types`.
        *   **Form Handling (`src/views/expense_claim/Form.vue`):**
            *   The form's structure is dynamically fetched using `hrms.api.get_doctype_fields`.
            *   Open employee advances are fetched using `hrms.hr.doctype.expense_claim.expense_claim.get_advances`.
            *   The designated expense approver and mandatory status are fetched using `hrms.api.get_expense_approval_details`.
            *   Default company accounts (cost center, payable account) are fetched via `hrms.api.get_company_cost_center_and_expense_account`.