# `<Login />` and `<Auth />`

## Auth + Role Based Auth

- problems to solve
  - valid user?
  - Authorization of user?
    - What parts of the app care?
    - How to determine?
      - Token data?
      - UI and API contact


## Proposal

- `<Auth />` component
- from perms and login, shows or hides sections
- can NOT use `Redux` to do this (we want to prevent specific implementations from being mandated)

```javascript
// The div only shows if you are logged in
  <Auth>
    <div />
  </Auth>

// The div only shows if you are logged in AND have read permissions
  <Auth capability="read">
    <div />
  </Auth>
```

## Resources

### Articles

- [what is rbac?](https://digitalguardian.com/blog/what-role-based-access-control-rbac-examples-benefits-and-more)
  - `role based access control`
  - manage role scope, role group, role, role assignment
  - network access auditing
- [react-cookies component](https://www.npmjs.com/package/react-cookies)
- [react-cookie library](https://www.npmjs.com/package/react-cookie)