# Restaurant Finder

Restaurant Finder is a web application built using the PERN stack (PostgreSQL, Express, React, Node.js) and Bootstrap. It allows users to view, and review restaurants. This project demonstrates the core concepts of full-stack web development, including CRUD operations, relational database management, and modern front-end design.

## Features

- **Restaurant Listings**: View a list of restaurants with their ratings and reviews.
- **Add a Restaurant**: Add new restaurants to the list.
- **Update a Restaurant**: Edit restaurant details.
- **Delete a Restaurant**: Remove restaurants from the list.
- **Review a Restaurant**: Add and view reviews for each restaurant.

## Technologies Used

- **Frontend**:
  - React
  - Bootstrap
  - Axios

- **Backend**:
  - Node.js
  - Express.js
  - PostgreSQL
  - pg (node-postgres)

## Getting Started

Follow these instructions to set up and run the project on your local machine.

### Prerequisites

- Node.js (v14 or above)
- PostgreSQL
- npm or yarn

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-username/restaurant-finder.git
cd restaurant-finder
```

2. **Set up the backend:**

   - Navigate to the server directory:

   ```bash
   cd server
   ```

   - Install the dependencies:

   ```bash
   npm install
   ```

   - Create a `.env` file in the `server` directory and add your database configuration:

   ```env
   DB_USER=your_db_user
   DB_PASSWORD=your_db_password
   DB_HOST=localhost
   DB_PORT=5432
   DB_DATABASE=restaurant_finder
   PORT=3001
   ```

   - Set up the PostgreSQL database:

   ```sql
   CREATE DATABASE restaurant_finder;
   ```

   - Run the database schema setup (create tables and relationships):

   ```sql
   CREATE TABLE restaurants (
       id SERIAL PRIMARY KEY,
       name VARCHAR(50) NOT NULL,
       location VARCHAR(50) NOT NULL,
       price_range INTEGER NOT NULL CHECK (price_range >= 1 AND price_range <= 5)
   );

   CREATE TABLE reviews (
       id SERIAL PRIMARY KEY,
       restaurant_id INTEGER REFERENCES restaurants(id) ON DELETE CASCADE,
       name VARCHAR(50) NOT NULL,
       review TEXT NOT NULL,
       rating INTEGER NOT NULL CHECK (rating >= 1 AND rating <= 5)
   );
   ```

   - Start the backend server:

   ```bash
   npm start
   ```

3. **Set up the frontend:**

   - Navigate to the client directory:

   ```bash
   cd ../client
   ```

   - Install the dependencies:

   ```bash
   npm install
   ```

   - Start the frontend development server:

   ```bash
   npm start
   ```

4. **Open the application:**

   - Visit `http://localhost:3000` in your browser to see the application in action.

## Usage

- **View Restaurants**: The home page displays a list of restaurants with their ratings.
- **Add a Restaurant**: Click on "Add Restaurant" to fill out and submit a form for a new restaurant.
- **Edit a Restaurant**: Click on the edit icon next to a restaurant to update its details.
- **Delete a Restaurant**: Click on the delete icon to remove a restaurant from the list.
- **Add a Review**: View the details of a restaurant and submit a review.

## Project Structure

- **client**: Contains the React frontend code.
- **server**: Contains the Express backend code.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [PostgreSQL](https://www.postgresql.org/)
- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [React](https://reactjs.org/)
- [Bootstrap](https://getbootstrap.com/)

---

Feel free to customize the content as per your project's specifics and requirements.