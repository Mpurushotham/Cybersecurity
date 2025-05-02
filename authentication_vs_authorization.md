# Authentication vs Authorization: How It Works

In the context of application security, **Authentication** and **Authorization** are two critical concepts that are often used together but are distinct in their roles. Understanding the difference between these two is crucial for securing applications and services.

---

## Authentication vs Authorization

- **Authentication** is the process of verifying the identity of a user, device, or service. It answers the question: *Who are you?*
- **Authorization** is the process of determining what an authenticated user is allowed to do. It answers the question: *What are you allowed to do?*

### Authentication:
Authentication ensures that the user is who they claim to be. For example, when you log in to an application with a username and password, the system authenticates your identity by checking if the credentials match the stored data.

### Authorization:
Authorization occurs after authentication, and it defines the level of access or permissions a user has within the system. After a successful authentication, the system grants or denies access to specific resources based on the user's roles or permissions.

---

## How Authentication Works (Step-by-Step)

1. **User Login**:
   - The user enters their **username** and **password** on the login screen.
   
2. **Verification**:
   - The server checks the credentials against the stored data (e.g., in a database or Identity Provider).
   
3. **Generate Token** (Optional for APIs):
   - If the credentials are correct, the server issues a **JWT (JSON Web Token)** or **session cookie** to authenticate the user for future requests without needing to log in again.

4. **Authentication Success**:
   - The user is successfully authenticated, and a session or token is established.

---

## How Authorization Works (Step-by-Step)

1. **Accessing Resources**:
   - Once authenticated, the user attempts to access a protected resource (e.g., a page or API endpoint).
   
2. **Authorization Check**:
   - The system checks the user's roles and permissions to see if they have access to the requested resource.
   
3. **Grant or Deny Access**:
   - If the user has the necessary permissions (e.g., *admin* role), access is granted. Otherwise, the user is denied access or shown an access control error message.

---

## Sample Code: Authentication and Authorization in Node.js

Here’s a simple example of **authentication** and **authorization** using **JWT tokens** in a **Node.js** environment.

### 1. Setup Dependencies

```bash
npm install express jsonwebtoken bcryptjs
```

## 2. Sample Code for Authentication (JWT) and Authorization (Roles)

```javascript
const express = require('express');
const jwt = require('jsonwebtoken');
const bcrypt = require('bcryptjs');
const app = express();
app.use(express.json());

const users = []; // In-memory user storage (for demo purposes)

// Authentication Endpoint
app.post('/login', (req, res) => {
  const { username, password } = req.body;
  
  // Find the user in the database (here, we use the in-memory array)
  const user = users.find(user => user.username === username);
  
  if (!user) {
    return res.status(400).send('User not found');
  }

  // Compare the password with the stored hashed password
  bcrypt.compare(password, user.password, (err, isMatch) => {
    if (!isMatch) {
      return res.status(401).send('Invalid password');
    }

    // Generate a JWT token with a payload containing the user info and role
    const token = jwt.sign({ username: user.username, role: user.role }, 'secretKey', { expiresIn: '1h' });

    // Send token in the response
    res.json({ token });
  });
});

// Authorization Middleware
function authorize(roles) {
  return (req, res, next) => {
    const token = req.header('Authorization')?.split(' ')[1]; // Bearer token
    
    if (!token) {
      return res.status(403).send('Access denied');
    }

    jwt.verify(token, 'secretKey', (err, decoded) => {
      if (err) {
        return res.status(403).send('Invalid token');
      }

      // Check if the user role is allowed
      if (!roles.includes(decoded.role)) {
        return res.status(403).send('Forbidden: You do not have access');
      }

      // Attach user data to the request object
      req.user = decoded;
      next();
    });
  };
}

// Protected Route (Authorization)
app.get('/admin', authorize(['admin']), (req, res) => {
  res.send('Welcome Admin!');
});

app.get('/user', authorize(['user', 'admin']), (req, res) => {
  res.send('Welcome User!');
});

// Sample Route to Register Users
app.post('/register', (req, res) => {
  const { username, password, role } = req.body;
  
  // Hash password before storing
  bcrypt.hash(password, 10, (err, hashedPassword) => {
    users.push({ username, password: hashedPassword, role });
    res.status(201).send('User registered');
  });
});

// Start Server
app.listen(3000, () => {
  console.log('Server started on http://localhost:3000');
});
```

# Explanation:
	
 * 1.	Authentication: The /login endpoint receives a username and password, checks them against the stored user data, and if valid, returns a JWT token. The token contains a payload with user info (such as role).
 * 2.	Authorization: The authorize middleware verifies the JWT token and checks if the user has the appropriate role to access the requested resource (e.g., only admin users can access /admin).

# Authentication vs Authorization

## Authentication

- **Definition**: Verifies the **identity** of a user.
- **Method**: Typically uses **username and password** or **biometrics** to authenticate the user.
- **Order of Occurrence**: Happens **first**, before the user can access any resource.
- **Example**: Login page where users input their username and password.

## Authorization

- **Definition**: Determines the **permissions** of an authenticated user.
- **Method**: Typically uses **roles** or **permissions** tied to the user to grant or deny access.
- **Order of Occurrence**: Occurs **after** successful authentication to control access to resources.
- **Example**: Role-based access control (RBAC) to grant or deny access to certain pages or resources based on user roles.

---

## Key Differences Between Authentication and Authorization

| **Authentication** | **Authorization** |
|-------------------|-------------------|
| Verifies the **identity** of a user. | Determines the **permissions** of an authenticated user. |
| Typically uses **username** and **password** or **biometrics**. | Typically uses **roles** or **permissions** tied to the user. |
| Occurs **first**, before the user can access any resource. | Occurs **after** successful authentication to control access. |
| **Example**: Login page where users input their username and password. | **Example**: Role-based access control to grant or deny access to certain pages. |

---

## Conclusion

- **Authentication** is the process of validating the user's identity.
- **Authorization** follows authentication and determines what the authenticated user can do or access.

Both processes are fundamental to ensuring secure access to systems and resources.
