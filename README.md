# DBMSAssignment5
PostgreSQL_DBMS Assignment Requirements:

Create database name users_management
Add 3 tables 
users, roles, user-roles
create table 
    roles - 
        id should be uuid
        name enum (values - admin, guest, customer)
        active - boolean
        deleted - boolean 
        created_on - date & time
    users -
        id  should be uuid
        name - string  cant be null
        email - string cant be null
        verified - boolean default false
        verified_on - date & time
        active - boolean  default true
        created_on - date & time
        created_by - same table id reference, can be null for admin role
        deleted - boolean default false
        deleted_on - date & time
        deleted_by - same table id reference
    user_roles
       id  should be uuid
       user_id - foreign key reference from users table
       role_id - foreign key reference from roles table 
       deleted - boolean default false
Trigger
    create trigger if record deleted from users table then user_role row should also be set as deleted

 Insert script 
        roles table 
            3 type of roles 
                admin
                guest
                customer
        add sample 10 users in user table
 
Temp backup table
    write query to copy all data from table user to table user_backup ( create new table user_backup as part of backup script )

View data
    Query to show complete user data including role name ( use joins ), & it should be verified, active , not deleted & created in last 5 days
        columns required to show 
        id  
        name 
        email 
        role
        created_on - date & time
