# Migration `20200625105952-added-username`

This migration has been generated by rushi444 at 6/25/2020, 10:59:52 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
ALTER TABLE "public"."User" ADD COLUMN "username" text  NOT NULL ;

CREATE UNIQUE INDEX "User.username" ON "public"."User"("username")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration 20200624113345-inital..20200625105952-added-username
--- datamodel.dml
+++ datamodel.dml
@@ -2,17 +2,18 @@
 // learn more about it in the docs: https://pris.ly/d/prisma-schema
 datasource db {
   provider = "postgresql"
-  url = "***"
+  url = "***"
 }
 generator client {
   provider = "prisma-client-js"
 }
 model User {
   id           Int       @default(autoincrement()) @id
+  username     String    @unique
   email        String    @unique
   name         String?
   password     String
 }
```


