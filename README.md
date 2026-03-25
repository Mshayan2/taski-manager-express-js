# Task Manager By Express

A simple file-based task manager built with **Node.js**, **Express**, and **EJS**. This project lets you create tasks, store them as local files, open task details, and rename existing task files through a basic web interface.

## Project Overview

This app uses the local `files/` directory as its storage layer instead of a database. Each task is saved as a text file, and the Express server reads those files to render the task list and detail pages.

It is a good beginner-friendly project for learning:

- Express routing
- EJS templating
- Handling form submissions
- Reading and writing files with Node.js `fs`
- Serving static assets in an Express app

## Features

- Create a new task from the homepage
- Save task details into a local text file
- Display all available task files on the main screen
- Open and read a single task
- Rename an existing task file
- Render pages with EJS templates

## Tech Stack

- Node.js
- Express
- EJS
- HTML
- Tailwind CSS
- Native Node.js `fs` module

## Folder Structure

```text
Task Manager By express/
|-- files/
|   |-- *.txt
|-- Public/
|   |-- stylesheet/
|       |-- styles.css
|-- views/
|   |-- index.ejs
|   |-- show.ejs
|   |-- edit.ejs
|-- index.js
|-- package.json
|-- package-lock.json
|-- README.md
```

## How It Works

### 1. Home Page

The `/` route reads all files inside the `files/` folder and sends them to the `index.ejs` view. The page shows a form for creating a task and a list of existing task files.

### 2. Create Task

The `/create` `POST` route accepts:

- `title`
- `details`

The title is converted into a filename and saved inside the `files/` folder. The task details become the content of that file.

### 3. View Task

The `/files/:filename` route reads the selected file and renders its contents on the task detail page.

### 4. Edit Task Name

The `/edit/:filename` route opens the rename form, and the `/edit` `POST` route renames the existing file.

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/Mshayan2/taski-manager-express-js.git
cd taski-manager-express-js
npm install
```

## Run Locally

Start the server with:

```bash
node index.js
```

Then open:

```text
http://localhost:3000
```

## Available Routes

| Method | Route | Description |
|---|---|---|
| `GET` | `/` | Show homepage with all tasks |
| `POST` | `/create` | Create a new task file |
| `GET` | `/files/:filename` | Open and read a task |
| `GET` | `/edit/:filename` | Open rename page |
| `POST` | `/edit` | Rename an existing task file |

## Dependencies

The project currently uses:

- `express`
- `ejs`

## Notes

- Tasks are stored locally in the `files/` folder.
- This project currently uses the filesystem instead of a database.
- It is best suited for learning Express and server-side rendering basics.

## Future Improvements

- Add task deletion
- Add validation for empty titles and details
- Prevent duplicate filenames
- Add edit support for task content, not only filename
- Add database integration with MongoDB or MySQL
- Improve error handling for file operations

## Author

Created by **Muhammad Shayan**.

## License

This project is licensed under the ISC License.
