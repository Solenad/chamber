# Leap 2025 Website (Backend)

Worked backend on CSO's Leap 2025 website.  
**In charge of overall api integration with guidance of senior backend developer.**

## Techstack

| Technology   | Description              |
| ------------ | ------------------------ |
| Node.js (TS) | TypeScript-based backend |
| MySQL 5.7    | API database             |
| Redis        | Session storage          |
| Contentful   | CMS API Integration      |

## Features

### **Authentication**

| Stage            | Method                        | Description                                                                                                                                                  |
| ---------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Initial Proposal | `passport-google-oauth2.0`    | Uses Google Strategy with a `verify()` callback that:<br>1. Checks if the user has previously logged in<br>2. Fetches or stores user details in the database |
| Current Feature  | Google Auth via `accessToken` | Auth flow:<br>1. API receives accessToken<br>2. Fetches userInfo from Google<br>3. Signs payload as JWT if user exists<br>4. Returns JWT to frontend         |

### **Sessions**

- Sessions-based hosting
- User data is stored in Redis
- Sessions stores user details during authentication flow

### **Restful API [IN PROGRESS]**

| Status      | Endpoint       |
| ----------- | -------------- |
| Done        | Organizations  |
| Done        | Events         |
| Done        | Subthemes      |
| In Progress | Registration   |
| In Progress | Media Handling |
