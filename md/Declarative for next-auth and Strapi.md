# Declarative for next-auth and Strapi

```typescript
import NextAuth from "next-auth"
import { JWT } from "next-auth/jwt"

declare module "next-auth" {
    interface Session {
        id: string,
        jwt: string
    }

    interface User {
        id: string,
        jwt: string
    }
}

declare module "next-auth/jwt" {
    interface JWT {
        /** OpenID ID Token */
        id: string,
        jwt: string,
    }
}
```

> types/next-auth.d.ts


