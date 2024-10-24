# UserStack
UserStack is a full-stack web application for creating, managing, and storing user data. The application assigns unique IDs to each user and displays the data in an interactive tile-based format. Built with a modern tech stack for scalability, consistency, and performance.

## Features
- Create, update, and delete users with ease.
- Display user data in dynamic, interactive tiles.
- Unique ID generation for each user.
- Real-time API interaction with a Go backend.
- Persistent data storage using PostgreSQL.
- Dockerized for consistent development and deployment environments.

## Tech Stack
- **Backend**: [Go](https://golang.org/) (for server-side logic)
- **Frontend**: [Next.js](https://nextjs.org/), [React](https://reactjs.org/), [TypeScript](https://www.typescriptlang.org/)
- **Database**: [PostgreSQL](https://www.postgresql.org/) (for relational data management)
- **API Communication**: [Axios](https://axios-http.com/) (for handling API requests)
- **Containerization**: [Docker](https://www.docker.com/) (for environment consistency)

## Project Structure
```bash
|-- backend
    |-- main.go             # Go server handling API requests
    |-- go.mod              # Go dependencies
    |-- go.sum              # Dependency versioning file
    |-- go.dockerfile       # Dockerfile for the Go server
|-- frontend
    |-- components
        |-- CardComponent.tsx   # Displays user data in interactive tile format
        |-- UserInterface.tsx   # User interface for managing user data
    |-- pages
        |-- index.tsx           # Main page of the application
    |-- public
        |-- [backendName]logo.svg  # Dynamic backend logos
```

## Installation
### Prerequisites
- Docker installed on your system.
- Go installed for local backend development.
- Node.js installed for frontend development.
- PostgreSQL for database setup.

### Backend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/U-Snap.git
   cd U-Snap
   ```
2. Build and run the backend using Docker:
   ```bash
   docker build -t u-snap-backend -f backend/go.dockerfile .
   docker run -p 8000:8000 u-snap-backend
   ```
### Frontend Setup
1. Navigate to the frontend folder:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create an `.env.local` file and add the following environment variables:
   ```bash
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```
4. Run the frontend:
   ```bash
   npm run dev
   ```
### Database Setup
1. Set up PostgreSQL and create a database:
   ```bash
   psql -U postgres
   CREATE DATABASE u_snap_db;
   ```
2. Update the connection string in the Go backend or use Docker with environment variables to point to the database.

## Usage

1. Start the backend server using Docker or `go run main.go`.
2. Start the frontend with `npm run dev`.
3. Visit [http://localhost:3000](http://localhost:3000) in your browser to interact with the app.
4. Create, update, and delete users using the form and buttons provided in the UI. User data is displayed in dynamic tiles.

## API Endpoints

- `GET /api/{backendName}/users`: Fetch all users.
- `POST /api/{backendName}/users`: Create a new user.
- `PUT /api/{backendName}/users/:id`: Update an existing user.
- `DELETE /api/{backendName}/users/:id`: Delete a user.

## Future Enhancements

- Add more backend options and dynamic support.
- Implement search and filtering for user data.
- Add pagination for large data sets.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

