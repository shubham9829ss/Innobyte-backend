### **Blog Application Backend - Project Overview**

This project is a RESTful API for a blog application that enables users to manage blog posts, comments, and user authentication. Built with a focus on modularity, the API handles essential CRUD operations, user authentication, and authorization using JWT (JSON Web Tokens). Below is a breakdown of the key features and routes:

### 1. **User Model**
The user model provides functionality for user management, including account creation, updating, and deletion. Users must be authenticated to access certain routes using a valid token.

- **Key Routes:**
  - `PUT /update/:userId`: Updates a user's information (requires authentication).
  - `DELETE /delete/:userId`: Deletes a user (requires authentication).
  - `POST /signout`: Logs the user out.
  - `GET /getusers`: Retrieves a list of users (requires authentication).
  - `GET /:userId`: Retrieves details of a specific user.

### 2. **Post Model**
Authenticated users can create, read, update, or delete blog posts. This model ensures that only authorized users can modify or delete their own posts.

- **Key Routes:**
  - `POST /create`: Allows an authenticated user to create a new blog post.
  - `GET /getposts`: Fetches all blog posts available on the platform.
  - `DELETE /deletepost/:postId/:userId`: Deletes a post (requires authentication and post ownership).
  - `PUT /updatepost/:postId/:userId`: Updates a post (requires authentication and post ownership).

### 3. **Comment Model**
The comment model allows users to interact with blog posts through comments. It includes functionality for creating, editing, deleting, and liking comments. Users must be authenticated to perform specific actions.

- **Key Routes:**
  - `POST /create`: Authenticated users can create a comment on a post.
  - `GET /getPostComments/:postId`: Retrieves all comments for a particular post.
  - `PUT /likeComment/:commentId`: Authenticated users can like a comment.
  - `PUT /editComment/:commentId`: Edits a comment (requires authentication).
  - `DELETE /deleteComment/:commentId`: Deletes a comment (requires authentication).
  - `GET /getcomments`: Retrieves all comments (requires authentication).

### 4. **Authentication Routes**
The authentication module handles user sign-up, sign-in, and authentication through third-party services like Google. JWT is used for token-based authentication.

- **Key Routes:**
  - `POST /signup`: Registers a new user.
  - `POST /signin`: Authenticates a user and returns a JWT.
  - `POST /google`: Authenticates a user via Google OAuth.

### **Additional Features:**
- **User Authorization:** Ensures that only authenticated users can create, update, or delete posts and comments.
- **Error Handling and Validation:** The API incorporates robust input validation and error handling to ensure reliability.

This API forms the core backend of a blog platform, supporting secure user interactions, content creation, and community engagement.
