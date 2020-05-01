# Access Control (ACL)

## Access Controls

- selective restriction of resources
- for API, limit access to clients by credentials
  - admin > create, manage , run reports
  - editor > create, edit, delete, no user management
  - guest > user to access read content
  - user > logged in user with read and maybe comment
- need to handle on both back and frontend
- backend
  - manage login cycle
  - maintain user db
  - maintain each user
  - authenticate users
  - create/manage/apply role based controls
  - maintain and reference capabilities, based on role
  - restrict acc to features based on capabilties (such as routes)
    - middleware used to control routes
    - mongoose middleware/hooks to restrice access to business logic
- front end
  - login
  - store login token via cookie
  - manage login state/capabilities
  - control physical and visual access
  - alter behaviors on RBAC rules

## Additional 

- RBAC -> role based access control

### videos

- [rbac tutorial](https://www.youtube.com/watch?v=C4NP8Eon3cA)

### misc

- [5 steps to rbac](https://www.csoonline.com/article/3060780/security/5-steps-to-simple-role-based-access-control.html)
- [wiki - rbac](https://en.wikipedia.org/wiki/Role-based_access_control)