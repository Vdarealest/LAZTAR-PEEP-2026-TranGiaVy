+++
title = "Day 04 - 01/10/2026 (On-site)"
weight = 4
+++

## User Management, Role Assignment & Warehouse List

Continued implementation based on the approved UI design, building the admin screens for users, roles, and warehouses.

- **User Management**: Built the user list screen (search, filter by status/role, pagination) and the create/edit user form (name, email, status, assigned warehouse).
- **Role Assignment**: Implemented the role assignment screen mapping users to the roles defined during Sprint 0 (Admin, Manager, Supervisor, Receiver, Picker, Inspector, Viewer), with a permission matrix view per role.
- **Warehouse List**: Built the warehouse list screen (code, name, address, status, number of locations) with create/edit/deactivate actions, following the BR-B rules from Domain B (e.g. only Admin can create/deactivate warehouses).
- Connected all three screens to their respective API endpoints and handled loading/empty/error states.
- Tested the flow end-to-end: create a user, assign a role, and verify the role's permissions are reflected when that user logs in.
