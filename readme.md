# Get ready for the coming Task

- completing this task successfully will insure you will be able to complete the coming task at the class with grade.

## Building Management

in the following task you will need to create a system to manage buildings issues.
the system capabilities:

1. create new issue.
2. watch all issues, filter by category, search by description free text.
3. delete an issue
   the system intended to the manager of the building and not for the tenants ( so it will be easier )

### Database

1. Create MySQL schema - name: building_management
2. Create the following tables:

- tenants (id, firstName, lastName, email, phone, apartmentNumber, floor) PK on id only.
- issues (id, tenantId , description, categoryId, createdAt)
- issues_categories (id, category) => data for example: Cleaning, Parking, Elevator Not Working ,

##### important

tables `tenants` & `issues_categories` need to be filled with the relevant data before starting to work in the system, otherwise you wont have categories and the user will not be able to create issues.

### Backend

Create Node.js API in TS with express, .env, zod validations, cors and the rest of packages we used.
crete the following entrypoints:

- GET /issues - return all the issues from the api ( ordered by date )
- GET /issue/search?description=poo - return all the issues from the api with the relevant description
- GET /issues/filter?category=parking - return all the issues from the api with the relevant filter
- POST /issues - create new issue ( pass the relevant info in the body: description, userId, categoryId )
- GET /categories - return all the categories from the relevant table
- GET /tenants - return all the tenants from the tenants table

### Frontend

Create react client with TS with routes + navigation bar

1. Page 1 - present all the issues in a page ( table ) + filtering & search capabilities
2. page 2 - create new issue page ( input text + dropdowns with values, for example categories should be taken from the categories table)

- hint, entrypoints 1-3 will need to be used in the first page.
- hint, entrypoints 4-6 will need to be used in the second page.
- feel free to change the API to support less entry points and reuse logic.
- recommend on creating script data that will insert initial data to your database, so you will be able to work without inserting manually data each time.
