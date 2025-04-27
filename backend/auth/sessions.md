# Sessions Knowledge Bank

Small markdown file storing all I can muster about sessions. Taking note of common practices as well as ideal approaches. This should be my go-to file for implementing sessions in future projects.

## Tech Stack
| Component           | Common Choices                                                                 |
|---------------------|-------------------------------------------------------------------------------|
| **Platform**        | Node.js                                                                       |
| **Session Middleware** | [`express-session`](https://www.npmjs.com/package/express-session)           |
| **Server Storage**  | Redis (production), MongoDB/PostgreSQL (via `connect-mongo`/`connect-pg-simple`) |
| **Client Storage**  | Cookies (server-side), LocalStorage (JWT - careful with XSS)                  |
| **Auth Packages**   | Passport.js (traditional), JWT (stateless)                                    |

## Core Concepts
### What is a Session?
- A stateful interaction period between user and server
- Typically stores:
  - User ID (most common)
  - Authentication status
  - Temporary data (e.g., shopping cart)

### Stateful vs. Stateless
| Factor              | Server-Side                      | Client-Side                   |
|---------------------|---------------------------------------------|-------------------------------------------|
| **Storage Location** | Server memory                       | Client cookie/localStorage                |
| **Security**        | More secure (sensitive data server-side)    | Risk of XSS if misconfigured              |
| **Scalability**     | Requires shared session store               | Stateless - inherently scalable           |
| **Performance**     | Slightly slower (DB lookups)                | Faster (no server lookups)                |
| **Revocation**      | Immediate (delete session)                  | Difficult (requires short expiry/blacklist) |
| **Use Cases**       | Traditional web apps                        | APIs/SPAs                                 |

## Practices
**Base practice for web-apps**: Express-sessions with Redis for server-side storage  
**For APIs**: Use JWT with HTTPS + HttpOnly cookies (security)  
**Stateful and Stateless approach**: Integrate both Redis and JWT  
**Constants**: Set cookie flags: Secure, SameSite, HttpOnly
