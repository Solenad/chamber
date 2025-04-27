# Passport.js Auth Integration

Short self-guide for passport implementation and steps. Helpful for future use of passport as authentication support.

## Initial Project Use

**Leap 2025 Backend (Google Oauth20)**  
Repo: <https://github.com/dlsu-lscs/leap25-backend>

## Implementation steps

1. Organize passport module
   - Varies from OAuth to Auth use
2. Setup passport strategy
   - Base the strategy on Auth type
   - Setup verify callback
     - callback handles first-time login
     - finishes after successful authentication
3. Post session integration
   - After sessions:
     - Add serialization and deserialization for passport
     - serialization: stores user id for sessions, strengthens security and performance
     - deserialization: fetches full user object for subsequent requests

## Potential Issues

- Varying auth types (have only tried google oauth)
- Database issues may affect app authentication

## Resources

<https://github.com/jaredhanson/passport-google-oauth2>
<https://www.passportjs.org/concepts/authentication/downloads/html/>
<https://www.passportjs.org/packages/passport-google-oauth20/>
