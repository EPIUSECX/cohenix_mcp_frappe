---

### **Module: `Frontend (Vue)`**

**1. High-Level Summary:**

*   **Purpose:** This document outlines the architecture of the modern, standalone frontend application for the Helpdesk. This application is built as a Single Page Application (SPA) using Vue.js, providing a rich, interactive user experience for both helpdesk agents and customers. It communicates with the Frappe backend via a REST API.
*   **Key Technologies:**
    *   **Vue.js:** The core JavaScript framework for building the user interface.
    *   **Vite:** The build tool used for development and production builds.
    *   **Vue Router:** The official router for Vue.js, used for client-side navigation.
    *   **Pinia:** A state management library for Vue.js.
    *   **Frappe UI:** A component library and set of utilities for interacting with the Frappe backend.
    *   **Tailwind CSS:** A utility-first CSS framework for styling.

**2. Application Architecture:**

*   **Initialization (`src/main.js`):**
    *   The application is bootstrapped as a standard Vue 3 application.
    *   It initializes and configures the `frappe-ui` library, setting `frappeRequest` as the default resource fetcher. This is the primary mechanism for making API calls to the Frappe backend.
    *   It sets up a Pinia store for state management.
    *   A WebSocket connection is established via `socket.io-client` for real-time communication.
*   **Routing (`src/router/index.ts`):**
    *   The application uses `vue-router` to manage all client-side navigation.
    *   Routes are defined for two main sections: the agent-facing desk (e.g., `/tickets`, `/customers`) and the public-facing customer portal (e.g., `/my-tickets`, `/kb-public`).
    *   A global navigation guard (`router.beforeEach`) is implemented to handle authentication and authorization. It checks if a user is logged in and has the appropriate permissions (e.g., agent, customer) before granting access to routes.
*   **State Management (`src/stores/`):**
    *   The application uses Pinia for state management. The `src/stores` directory likely contains stores for managing application-wide state, such as the currently logged-in user, tickets, and other data.

**3. Feature-Based Analysis:**

*   **Feature: Ticket Management**
    *   **Views:**
        *   `src/pages/ticket/Tickets.vue`: The main view for listing tickets, likely used for both agents and customers with different data scopes.
        *   `src/pages/ticket/TicketAgent.vue`: The detailed view for an agent to manage a ticket.
        *   `src/pages/ticket/TicketCustomer.vue`: The detailed view for a customer to view their ticket.
        *   `src/pages/ticket/TicketNew.vue`: The form for creating a new ticket.
    *   **Components:**
        *   The `src/components/ticket/` directory likely contains various components for displaying ticket details, such as the ticket timeline, attachments, and other information.
    *   **API Interactions:**
        *   The components in these views will make `frappeRequest` calls to the backend to fetch ticket data, post updates, and perform other actions. The specific API endpoints will be detailed in the next phase of the analysis.

---
*   **API Interactions:**
        *   **List View (`src/pages/ticket/Tickets.vue`):**
            *   The component uses the `ListViewBuilder` from `frappe-ui` to render the list of tickets. The API calls for fetching the list data are encapsulated within this component.
            *   The export functionality constructs a URL to `frappe.desk.reportview.export_query` to download the ticket data.
        *   **Detail View (`src/pages/ticket/TicketAgent.vue`):**
            *   The main ticket data is fetched using a `createResource` call to `helpdesk.helpdesk.doctype.hd_ticket.api.get_one`.
            *   Updates to the ticket (e.g., changing the status, priority) are sent to the backend using `frappe.client.set_value`.