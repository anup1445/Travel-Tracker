
# Travelist - Travel Tracker Application

Travelist is a web application designed to help users track the countries they have visited. Built with EJS, CSS, Node.js, and PostgreSQL, this project provides an interactive and user-friendly interface for managing travel records.


## Documentation



## Features

- **Dynamic Interface**: EJS templates render a responsive and intuitive UI.
- **Efficient Backend**: Node.js handles server-side operations and routing.
- **Reliable Database**: PostgreSQL manages the storage of country data and user inputs.
- **Real-Time Updates**: Visited countries list and count update dynamically.
- **Error Handling**: Provides user feedback for invalid or duplicate entries.

## Technologies Used

- **Frontend**: EJS, CSS
- **Backend**: Node.js, Express.js
- **Database**: PostgreSQL
- **Middleware**: body-parser

## Prerequisites

- **Node.js**: Make sure Node.js is installed on your system.
- **PostgreSQL**: Ensure PostgreSQL is installed and running.

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/anup1445/Travel-Tracker.git
    cd travelist
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Setup PostgreSQL**:
    - Create a PostgreSQL database named `world`.
    - Create the necessary tables:
      ```sql
      CREATE TABLE countries (
          country_code VARCHAR(3) PRIMARY KEY,
          country_name VARCHAR(50) NOT NULL
      );
      
      CREATE TABLE visited_countries (
          country_code VARCHAR(3) REFERENCES countries(country_code)
      );
      ```
    - Populate the `countries` table with country data.

4. **Configure the database connection**:
    - Update the database configuration in `index.js`:
      ```javascript
      const db = new pg.Client({
        user: "your_postgres_user",
        host: "localhost",
        database: "world",
        password: "your_postgres_password",
        port: 5432, // Default PostgreSQL port
      });
      ```

## Running the Application

1. **Start the server**:
    ```bash
    npm start
    ```
2. **Access the application**:
    Open your browser and go to `http://localhost:3000`.

## Usage

- **Homepage**:
  - Displays a list of visited countries and the total count.
- **Add Country**:
  - Enter the name of a country you have visited and submit.
  - If the country exists in the database and hasn’t been added yet, it will be added to your visited list.
- **Error Feedback**:
  - If the country does not exist in the database, an error message will be displayed.
  - If the country has already been added, a duplicate entry error message will be shown.

## Project Structure

- **public/**: Contains static files (CSS, images, etc.).
- **views/**: Contains EJS templates.
- **index.js**: Main server file.

## Contributing

1. **Fork the repository**.
2. **Create a new branch** (`git checkout -b feature-branch`).
3. **Commit your changes** (`git commit -m 'Add some feature'`).
4. **Push to the branch** (`git push origin feature-branch`).
5. **Create a new Pull Request**.



---




