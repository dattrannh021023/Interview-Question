# • How do you create a new postgres user?

To create a new user in PostgreSQL, you can use the `CREATE USER` SQL command or the `CREATE ROLE` command, which can be used interchangeably. Here's how you can create a new PostgreSQL user:

Using `CREATE USER`:

```sql
CREATE USER username WITH PASSWORD 'password';

```

Using `CREATE ROLE`:

```sql
CREATE ROLE username WITH LOGIN PASSWORD 'password';

```

Replace `username` with the desired username for the new user and `password` with the user's password. You can also specify other attributes and privileges for the user as needed.

Here are some additional options you can use with the `CREATE USER` or `CREATE ROLE` command:

- To grant superuser privileges to the user:
    
    ```sql
    CREATE USER username WITH SUPERUSER;
    
    ```
    
- To specify the user's role memberships (groups):
    
    ```sql
    CREATE USER username IN ROLE rolename1, rolename2;
    
    ```
    
- To set other attributes like whether the user is allowed to create databases:
    
    ```sql
    CREATE USER username CREATEDB;
    
    ```
    
- To set the user's connection limitations, such as limiting the number of concurrent connections:
    
    ```sql
    CREATE USER username CONNECTION LIMIT 5;
    
    ```
    
- To set a user's password to expire and require a password change upon first login:
    
    ```sql
    CREATE USER username WITH PASSWORD 'password' VALID UNTIL '2024-12-31' PASSWORD EXPIRE;
    
    ```
    

After creating the user, don't forget to grant necessary privileges to the user on specific databases or objects using the `GRANT` command if needed.

Here's an example of granting a user the ability to create databases:

```sql
GRANT CREATEDB TO username;

```

Make sure to replace `username` with the actual username and adapt the commands to your specific requirements.