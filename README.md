
# Flask App with MySQL Docker Setup

This is a simple Flask app that interacts with a MySQL database. The app allows users to submit messages, which are then stored in the database and displayed on the frontend.
This flask app runs on the Flask development web server

## Setup

1. Clone this repository (if you haven't already):

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```

2. Navigate to the project directory:

   ```bash
   cd your-repo-name
   ```

3. Create a `.env` file in the project directory to store your MySQL environment variables:

   ```bash
   touch .env
   ```

4. Open the `.env` file and add your MySQL configuration:

   ```
   MYSQL_HOST=mysql
   MYSQL_USER=your_username
   MYSQL_PASSWORD=your_password
   MYSQL_DB=your_database
   ```

## Usage

1. Start the containers using Docker Compose:

   ```bash
   docker-compose up -d --build
   ```
   <img width="488" alt="Screenshot 2023-10-20 150523" src="https://github.com/sshuen30/flask-project-db/assets/40738215/4c8ebd6a-db50-4ec6-b5cc-25a49077b9bf">

2. Access the Flask app in your web browser:

   - Frontend Webpage: http://localhost:5000
   - phpmyadmin: http://localhost:8080

3. Create the `messages` table in your MySQL database:

   - Login to phpmyadmin webpage @ http://localhost:8080 using credentials: root, test@123
   - Alternatively, docker exec into the phpmyadmin container and login in to sql to execute this command
     
    ``` bash
    docker exec -it <container_id> /bin/bash
    ```
   - Login to mySQL using root user
     
    ``` bash
    mysql -u root -p
    ```
     ```sql
     CREATE TABLE messages (
         id INT AUTO_INCREMENT PRIMARY KEY,
         message TEXT
     );
     ```

## Cleaning Up

To stop and remove the Docker containers, press `Ctrl+C` in the terminal where the containers are running, or use the following command:

```bash
docker-compose down
```

## Notes

- Make sure to replace placeholders (e.g., `your_username`, `your_password`, `your_database`) with your actual MySQL configuration.

- This is a basic setup for demonstration purposes. In a production environment, you should follow best practices for security and performance.

- Be cautious when executing SQL queries directly. Validate and sanitize user inputs to prevent vulnerabilities like SQL injection.

- If you encounter issues, check Docker logs and error messages for troubleshooting.

```

# two-tier-architecture-flask-application-with-database
# two-tier-flask-app-with-database
