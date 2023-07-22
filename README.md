
# ToDo API

The ToDo API is a simple RESTful API built using Flask and Flask-RESTful. It provides endpoints to manage ToDo tasks and their summaries. With this API, you can perform basic CRUD (Create, Read, Update, Delete) operations on ToDo tasks.

## Features

- **Create**: You can create a new ToDo task by providing a task description and a summary of the task.
- **Read**: You can retrieve a list of all existing ToDo tasks, as well as fetch a specific ToDo task by its unique ID.
- **Update**: You have the option to update the task description or summary of an existing ToDo task.
- **Delete**: You can delete a ToDo task by specifying its unique ID.

## Getting Started

To get started with the ToDo API, make sure you have the following prerequisites:

- Python 3.x: The API is built using Python, so you need to have Python installed on your system.
- Flask: Flask is a lightweight web framework for Python that enables building web applications, including APIs.
- Flask-RESTful: Flask-RESTful is an extension for Flask that simplifies building RESTful APIs.
- SQLAlchemy: SQLAlchemy is a powerful Object-Relational Mapping (ORM) library for Python, used for interacting with the SQLite database.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/todo-api.git
cd todo-api
```
2. Install the required dependencies:
```bash
pip install -r requirements.txt
```
3. Run the Flask development server:
```bash
python app.py
```
The API will be accessible at http://localhost:5000/todos

## Usage
The ToDo API can be interacted with using HTTP requests. Here are the available endpoints

Endpoints:

GET /todos: Retrieve a list of all ToDo tasks.

- **GET** /todos/<todo_id>: Retrieve a specific ToDo task by its unique ID.
- **POST** /todos/<todo_id>: Create a new ToDo task. Provide the task and summary as JSON data in the request body.
- **PUT** /todos/<todo_id>: Update an existing ToDo task. You can update the task or summary, or both, by providing the updated data as JSON.
- **DELETE** /todos/<todo_id>: Delete a ToDo task specified by its unique ID.

## Sample Requests and Responses
The API returns responses in JSON format. Here are some sample requests and responses:

### Get all ToDo tasks

#### Request
```http
GET /todos
```
#### Response
```json
{
  "1": {
    "task": "Buy groceries",
    "summary": "Get milk, eggs, and bread"
  },
  "2": {
    "task": "Finish project",
    "summary": "Complete documentation and testing"
  }
}
```

### Get a specific ToDo task
#### Request
```http
GET /todos/1
```
#### Response
```json
{
  "id": 1,
  "task": "Buy groceries",
  "summary": "Get milk, eggs, and bread"
}

```
### Create a new ToDo task
#### Request
```http
POST /todos/3
Content-Type: application/json

{
  "task": "Exercise",
  "summary": "Go for a morning run"
}

```
#### Response
```json
{
  "id": 3,
  "task": "Exercise",
  "summary": "Go for a morning run"
}
```
### Update a ToDo task
#### Request
```http
PUT /todos/2
Content-Type: application/json

{
  "summary": "Review code and submit"
}
```
#### Response
```json
{
  "id": 2,
  "task": "Finish project",
  "summary": "Review code and submit"
}
```
### Delete a ToDo task
#### Request
```http
DELETE /todos/1
```
#### Response
```bash
Status: 204 No Content
```

## Technologies Used
The ToDo API is built using the following technologies:

- **Python:** The primary programming language used to develop the API.
- **Flask:** Flask is a lightweight and flexible web framework for Python, enabling the creation of web applications and APIs.
- **Flask-RESTful:** This extension for Flask simplifies the process of building RESTful APIs.
- **SQLite:** The SQLite database is used to store ToDo tasks and summaries.
