
# Description:

The application must allow the users to:

- Create and manage projects.
- Assign tasks.
	
## Requirements:

### 1. Data model:
* User:
	* id:
    * name: (username)
    * email:
    * password: (Encrypted)
    * user_rol: (admin, user)
	
* Project:
    * id:
    * name:
    * description:
    * start_date: Project's starting date.
    * end_date:
    * user_id: ID of the responsible user.
		
* Task:
    * id:
    * name:
    * description:
    * status: (pending, in progress, finished)
    * project_id:
    * assigned_to (or user_id)
		
### 2. Endpoints:
* Projects:
	* `GET /projects`: Get all projects.
	* `GET /projects/{id}`: Get a specific project.
	* `POST /projects`: Create a new project.
	* `PUT /projects/{id}`: Update the information of a project. 
	* `DELETE /projects/{id}`: Delete a project
* Tasks:
	* `POST /tasks`: Create a new task.
	* `PATCH /tasks/{id}`: Update the status of a task.
	* `GET /tasks?project_id={id}`: Get tasks filtered by project.
		
### 3. Business rules:
* Implement a system permit that allows:
	- admins can manage all projects and tasks.
	- users can only manage their own tasks within the project assigned.
* When creating or updating tasks, make sure the status is updated correctly 
	and notify the user assigned to (you can use the console or the API response)
	
### 4. Data base:
* Use any SQL DB like PostgreSQL or MySQL to storage the info.
* Use H2??

### 5. Authentication:
* Implement authorization and authentication - JWT
		
