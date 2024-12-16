# Multer File Uploading

This is a Node.js application demonstrating how to implement file uploads using [Multer](https://github.com/expressjs/multer), a middleware for handling `multipart/form-data`, primarily used for uploading files.

## Features

- File upload functionality with Multer middleware.
- Simple and efficient way to handle form data.
- Supports single and multiple file uploads.

## Requirements

- Node.js (version 14 or higher)
- npm or yarn package manager

## Installation

Follow these steps to get started:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/multer-file-upload.git
   cd multer-file-upload

2. Install dependencies:
    ```bash
    npm install

3. Start the application:
    ```bash
    npm start

## Usage

- Run the application and navigate to the specified route where file upload functionality is implemented (e.g., /upload).

- Use an API testing tool like Postman or a frontend form to test the file upload functionality. Example routes:
    Single file upload: POST /upload-single
    Multiple file uploads: POST /upload-multiple

-Files will be stored in the directory you configured in Multer.


# Configuration

## Multer Setup Example

Here's an example of how Multer is configured in the project:

```javascript

    const multer = require('multer');
    const path = require('path');

    const storage = multer.diskStorage({
    destination: (req, file, cb) => {
        cb(null, 'uploads/');
    },
    filename: (req, file, cb) => {
        cb(null, `${Date.now()}-${file.originalname}`);
    },
    });

    const upload = multer({ storage: storage });
    module.exports = upload;
